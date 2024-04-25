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
</ul><h5>Steps</h5><ul>
<li>1.DATA INGESTION-Ingesting Data from website to spark cluster using JSON API endpoint</li>
</ul><ul>
<li>2.DATA FILTERATION-Data is filtered from 2017 to 2022</li>
</ul><ul>
<li>3.DATA ANALYSIS- Develop Queries using SparkSql for each of the business use cases using Databricks Notebook</li>
</ul><ul>
<li>4.DATA VISUALIZATION-Create visuals from the results obtained from each query in Databricks Notebook</li>
</ul><h2>Usage</h2>
<hr><p><li>A decreasing trend in the crime rate is observed from 2017 to 2020, followed by an increasing trend thereafter.&nbsp;</li><li>
Brooklyn borough registers the highest number of crimes, followed by Manhattan.&nbsp;</li>
<li>More than 50% of crimes are committed by individuals aged 25-44.&nbsp;</li>
<li>Males account for a higher number of registered crime cases compared to females.&nbsp;</li>
<li>Dangerous Drug and Vehicle and Traffic Law offenses have shown significant decreases over the years.&nbsp;</li>
<li>Conversely, Criminal Mischief &amp; Related Offenses have peaked in recent years.&nbsp;</li></p><h5>Code Examples</h5><ul>
<li>The Dashboard can be found :-</li>
</ul><p><code>&lt;div class='tableauPlaceholder' id='viz1714068711134' style='position: relative'&gt;&lt;noscript&gt;&lt;a href='#'&gt;&lt;img alt='Dashboard 2 ' src='https:&amp;#47;&amp;#47;public.tableau.com&amp;#47;static&amp;#47;images&amp;#47;cr&amp;#47;crimedashboard_17140209658330&amp;#47;Dashboard2&amp;#47;1_rss.png' style='border: none' /&gt;&lt;/a&gt;&lt;/noscript&gt;&lt;object class='tableauViz'  style='display:none;'&gt;&lt;param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /&gt; &lt;param name='embed_code_version' value='3' /&gt; &lt;param name='site_root' value='' /&gt;&lt;param name='name' value='crimedashboard_17140209658330&amp;#47;Dashboard2' /&gt;&lt;param name='tabs' value='no' /&gt;&lt;param name='toolbar' value='yes' /&gt;&lt;param name='static_image' value='https:&amp;#47;&amp;#47;public.tableau.com&amp;#47;static&amp;#47;images&amp;#47;cr&amp;#47;crimedashboard_17140209658330&amp;#47;Dashboard2&amp;#47;1.png' /&gt; &lt;param name='animate_transition' value='yes' /&gt;&lt;param name='display_static_image' value='yes' /&gt;&lt;param name='display_spinner' value='yes' /&gt;&lt;param name='display_overlay' value='yes' /&gt;&lt;param name='display_count' value='yes' /&gt;&lt;param name='language' value='en-US' /&gt;&lt;/object&gt;&lt;/div&gt;                &lt;script type='text/javascript'&gt;                    var divElement = document.getElementById('viz1714068711134');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth &gt; 800 ) { vizElement.style.width='1600px';vizElement.style.height='927px';} else if ( divElement.offsetWidth &gt; 500 ) { vizElement.style.width='1600px';vizElement.style.height='927px';} else { vizElement.style.width='100%';vizElement.style.height='2627px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                &lt;/script&gt;</code></p><h2>References</h2>
<hr><ul>
<li>Tutorial: Query data with notebooks. (n.d.). Docs.databricks.com. Retrieved February 12, 2024, from https://docs.databricks.com/en/getting-started/quick-start.html</li>
</ul><ul>
<li>•	Ojas, B. (2023, March 14). Data Ingestion in Apache Spark. Medium. https://medium.com/@badwaik.ojas/data-ingestion-in-apache-spark-7041ab46d8f3</li>
</ul>
