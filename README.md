<h1>NYPD Arrests: An Exploratory Data Analysis (2017-2022)</h1>
<hr><p>The aim of this project is to utilize Big Data tools, such as SparkSQL, within the Databricks Intelligence platform, to conduct data analysis on the NYPD arrest dataset.</p><h2>General Information</h2>
<hr><ul>
<li>Data for this presentation is sourced from the NYPD Arrests Data (Historic) provided by the Police Department (NYPD) and hosted by NYC OpenData at</li>
</ul>
<p>https://data.cityofnewyork.us/Public-Safety/NYPD-Arrests-Data-Historic-/8h9b-rp9u/about_data.</p><ul>
<li>We are going to derive insights on below scenarios: -</li>
</ul>
<ol>
<li>Number of Arrests made per year and month in NYC.</li>
<li>Which Borough is most dangerous to live in NYC.</li>
<li>Which Community is committing most crimes in New York.</li>
<li>Which Age groups is committing most crimes in New York City.</li>
<li>Trend of Crimes in NYC.</li>
<li>Top 10 types of crimes that are prevalent in New York.</li>
</ol><ul>
<li>Our analysis encompasses a yearly, monthly, and geographical examination, alongside a demographic study categorizing arrests by age, race, and crime type.</li>
</ul><h2>Technologies Used</h2>
<hr><ul>
<li>Databricks</li>
</ul><ul>
<li>Apache Spark</li>
</ul><ul>
<li>SparkSql</li>
</ul><ul>
<li>Tableau</li>
</ul><h2>Screenshots</h2>
<div class='tableauPlaceholder' id='viz1714103495077' style='position: relative'><noscript><a href='#'><img alt='Dashboard 2 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;cr&#47;crimedashboard_17140209658330&#47;Dashboard2&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='path' value='views&#47;crimedashboard_17140209658330&#47;Dashboard2?:language=en-US&amp;:embed=true&amp;:sid=' /> <param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;cr&#47;crimedashboard_17140209658330&#47;Dashboard2&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1714103495077');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1600px';vizElement.style.height='927px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1600px';vizElement.style.height='927px';} else { vizElement.style.width='100%';vizElement.style.height='2627px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>
<h2>Steps</h2><ul>
<li>1.DATA INGESTION-Ingesting Data from website to spark cluster using JSON API endpoint</li>
</ul><ul>
<li>2.DATA FILTERATION-Data is filtered from 2017 to 2022</li>
</ul><ul>
<li>3.DATA ANALYSIS- Develop Queries using SparkSql for each of the business use cases using Databricks Notebook</li>
</ul><ul>
<li>4.DATA VISUALIZATION-Create visuals from the results obtained from each query in Databricks Notebook</li>
</ul><h2>Usage</h2>
<hr><p>A decreasing trend in the crime rate is observed from 2017 to 2020, followed by an increasing trend thereafter.&nbsp;
Brooklyn borough registers the highest number of crimes, followed by Manhattan.&nbsp;
More than 50% of crimes are committed by individuals aged 25-44.&nbsp;
Males account for a higher number of registered crime cases compared to females.&nbsp;
Dangerous Drug and Vehicle and Traffic Law offenses have shown significant decreases over the years.&nbsp;
Conversely, Criminal Mischief &amp; Related Offenses have peaked in recent years.&nbsp;</p><h5>Code Examples</h5><ul>
<li>Checking the number of Observation in the table</li>
</ul><p><code>%sql select count(*) FROM `nypd_historical_data2`;</code></p><ul>
<li>Checking Unique offense values for treatment</li>
</ul><p><code>%sql select distinct ofns_desc  FROM `nypd_historical_data2`; </code></p><ul>
<li>Checking the trend of Crime over years</li>
</ul><p><code>%sql SELECT EXTRACT(YEAR FROM ARREST_DATE) AS arrest_year, COUNT(*) AS num_arrests FROM nypd_historical_data2 GROUP BY arrest_year ORDER BY arrest_year;</code></p><ul>
<li>Checking the trend of Crime over years and months</li>
</ul><p><code>%sql SELECT      EXTRACT(YEAR FROM ARREST_DATE) AS arrest_year,     EXTRACT(MONTH FROM ARREST_DATE) AS arrest_month,     COUNT(*) AS num_arrests FROM      nypd_historical_data2 WHERE     EXTRACT(YEAR FROM ARREST_DATE) BETWEEN 2017 AND 2022 GROUP BY     arrest_year,     arrest_month ORDER BY     arrest_year,     arrest_month;</code></p><ul>
<li>Checking the Distribution  of Crimes in Borough</li>
</ul><p><code>%sql SELECT      CASE          WHEN ARREST_BORO = 'K' THEN 'Brooklyn'         WHEN ARREST_BORO = 'Q' THEN 'Queens'         WHEN ARREST_BORO = 'B' THEN 'Bronx'         WHEN ARREST_BORO = 'M' THEN 'Manhattan'         WHEN ARREST_BORO = 'S' THEN 'Staten Island'         ELSE ARREST_BORO -- If none of the above conditions match, keep the original value     END AS Borough,     COUNT(*) AS num_arrests FROM nypd_historical_data2 GROUP BY ARREST_BORO ORDER BY num_arrests DESC ;</code></p><h2>References</h2>
<hr><ul>
<li>Tutorial: Query data with notebooks. (n.d.). Docs.databricks.com. Retrieved February 12, 2024, from https://docs.databricks.com/en/getting-started/quick-start.html</li>
</ul><ul>
<li>Ojas, B. (2023, March 14). Data Ingestion in Apache Spark. Medium. https://medium.com/@badwaik.ojas/data-ingestion-in-apache-spark-7041ab46d8f3</li>
</ul>
