<h1><p align="center">Hello there, Wellcome to my page 💭</p></h1>

<h2><p align="center">Always working in something new. I'm love discovery things from news views 👨🏿‍💻</p></h2>

- Today working as a BI Analytic 🧑🏻‍💼
- Studying Forecats and Time Series 🤓
- Learning about Databricks and TensorFlow
- Building Dashboards and making Analytics every day ✅
- Coding.... 💻

<p align="center">
  <img src="https://media.dev.to/cdn-cgi/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fe8nwc3rt8qk7k701vjg8.gif" width="auto" height="auto" alt="GIF">
</p>


#

- 🔭 I am currently working on Machine Learning and Data Analytics projects.

- 🔭 I bring my experience with Statistics and Machine Learning through mini-projects that aim to explore the complexity and variety of data in the world.

- 🤓 Among my key skills, I highlight Excel, Python, R, Power BI (storytelling and related), and SQL.

- ✅ I always strive to provide new and powerful insights, operating through the lens of business and root cause analysis.

- Having worked in the data field for 3 years with various projects, I am starting my repository here. The idea of this repository is to showcase my skills.

- 📘 Probability, Estimation, Hypothesis Testing, Regression, and Forecasting with Machine Learning will be some of the topics you'll find here today!

#

<div align="center">
<picture>
  <source
    srcset="https://github-readme-stats.vercel.app/api?username=velosoberti&show_icons=true&theme=dracula"
    media="(prefers-color-scheme: dark)"
  />
  <source
    srcset="https://github-readme-stats.vercel.app/api?username=velosoberti&show_icons=true"
    media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
  />
  <img src="https://github-readme-stats.vercel.app/api?username=velosoberti&show_icons=true" />
</picture>
</div>


# Technologies:

<div style="display: inline_block"><br>
  <img align="center" alt="Luis-R" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/rstudio/rstudio-original.svg" />
  <img align="center" alt="Luis-python" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" />
  <img align="center" alt="Luis-Postgr" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" />
  <img align="center" alt="Luis-SQL" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/azuresqldatabase/azuresqldatabase-original.svg" />
  <img align="center" alt="Rafa-CSS" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/matplotlib/matplotlib-original-wordmark.svg" />
  <img align="center" alt="Rafa-Python" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/numpy/numpy-original-wordmark.svg" />
  <img align="center" alt="Rafa-Csharp" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/scikitlearn/scikitlearn-original.svg" />
  <img align="center" alt="Rafa-Csharp" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pandas/pandas-original-wordmark.svg" />
</div>

  ##
 
<div> 
 <a href="https://velosoberti.github.io/luisveloso.github.io/" target="_blank"><img src="https://img.shields.io/badge/Blogger-FF5722?style=for-the-badge&logo=blogger&logoColor=white"></a> 
  <a href="https://www.linkedin.com/in/velosoberti/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
</div>


<?php

	function get_num_visitas(){
		//conectar
		$link = mysql_connect('localhost', 'root', '');
		if (!$link) {
			die('Não foi possível conectar: ' . mysql_error());
		}
		
		mysql_select_db("contador");
		$query = "SELECT total " .
				 "FROM `visitas` " .
				 "ORDER BY total ASC LIMIT 1";
		$result = mysql_query($query);
		if (!$result) {
			$message  = 'Invalid query: ' . mysql_error() . "\n";
			$message .= 'Whole query: ' . $query;
			die($message);
		}
		if (mysql_num_rows($result) == 0) {
			echo "No rows found, nothing to print so am exiting";
			exit;
		}
		$row = mysql_fetch_array($result);
		mysql_close($link);
		return $row["total"];
		//fazer consulta
		//retornar total
	}

	function imprime_visitas($contador){
		return "<h1>" . $contador . "</h1>";
	}
	
	function contar_visita(){
		//conectar
		$link = mysql_connect('localhost', 'root', '');
		if (!$link) {
			die('Não foi possível conectar: ' . mysql_error());
		}
		
		mysql_select_db("contador");
		$query = "UPDATE `visitas` " .
				 "SET total = total + 1";
		$result = mysql_query($query);
		if (!$result) {
			$message  = 'Invalid query: ' . mysql_error() . "\n";
			$message .= 'Whole query: ' . $query;
			die($message);
		}
		mysql_close($link);
	}

	contar_visita();
	$contador = get_num_visitas();
	echo imprime_visitas($contador);

?>

