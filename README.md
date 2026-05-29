# Process Writeup – Is Happiness Quantifiable?
By Judi Hernandez, Urunna Anyanwu, and Eliram Reyes-Powell

## Project Overview
Our project, Is Happiness Quantifiable?, explored the methodology and assumptions behind the World Happiness Report and questioned whether human happiness can truly be reduced to measurable structural indicators. We approached the topic curious on what makes a nation “happy,” and sought to explore the validity of the World Happiness Report (WHR)’s methods in quantifying happiness. Initially, we conducted exploratory analysis via graphing and the WHR’s website to understand the different categories and trends existing amongst countries. As we grew to understand the model’s categories like generosity, GDP, or corruption, we became increasingly interested in the model’s “Dystopia + residual” metric and what it revealed about the model’s limitations.

Our project sought to explore how this metric works and how it creates biases in the model’s categorization of happy countries. We questioned whether structural factors alone could quantify a country’s happiness, and the harm that comes in not exploring cultural or personal factors.

Our final deliverable is a data story, combining our .csv/.xlsx data sets with the following tools: Python (data cleaning, regional grouping), Tableau (visualization creation), and Inkscape (editing and design). Ultimately, we dedicated ourselves to delivering an effective story while employing Color Theory, Gestalt Principles, Typography, and additional Data Visualization best practices.

## Data Cleaning
The datasource (https://www.worldhappiness.report/data-sharing/) was relatively simple (2117 rows x 13 columns). Likely because it’s a collaborative project across several academic and research institutions, limited cleaning was necessary for the well-maintained dataset. Our cleaning focused on using Python’s Pandas library to edit the dataset to be more useful for our needs, such as:

### Excluding Incomplete Data
From 2011 - 2019, our dataset only includes information for the columns Year, Rank, Country name, and Life evaluation. Though some of our visualizations utilized these years, much of our research included finding trends across the different categories in the model. Rows describing rankings from 2011 - 2019 were thus removed. Since our data only covered 7 years, we also removed any countries that had less than 7 occurrences as the researchers had occasions where inconsistently stopped/started surveying certain countries.

### Mapping Countries to Regions
1. Name Standardization: The raw dataset uses variable formatting for certain regions (e.g., "Taiwan Province of China" or "Hong Kong SAR of China"). To ensure Tableau's native geographic mapping tool recognizes these locations seamlessly, the script standardizes names into their globally recognized baseline equivalents:
* "Taiwan Province of China" becomes "Taiwan"
* "Hong Kong SAR of China" becomes "Hong Kong"
* "State of Palestine" becomes "Palestine"
* "Russian Federation" becomes "Russia"
* "DR Congo" / "Congo" are standardized to full formal titles.
2. Feature Engineering: Grouping by Macro-Regions
To move away from chaotic, country-level "data webs" and analyze macro-trends, the pipeline maps every unique country to its official World Happiness Report Macro-Region. The script uses a hard-coded mapping dictionary (LLM assisted) to inject a new structural column: WHR Global Region.
This categorizes the 140+ countries into 10 distinct regional sandboxes:
* Western Europe
* North America and ANZ
* Latin America and Caribbean
* Central and Eastern Europe
* Commonwealth of Independent States (CIS)
* East Asia
* Southeast Asia
* South Asia
* Middle East and North Africa (MENA)
* Sub-Saharan Africa
## Exploratory Data Analysis
Once the data was cleaned, we sought to explore its behavior by graphing plots in Tableau. Though our final project included 6 key charts, our time in Tableau yielded several more as we developed the story we wanted to tell. This early stage prioritized quantity over quality of charts across each group member.

Many of our initial hypotheses were confirmed: Nordic countries consistently ranked high, most non-Western countries ranked low, and most countries’ scores were incredibly similar. Our research revealed interesting outliers, too. Certain countries greatly outperformed others in certain categories, yet still ranked heavily below them. For example, Costa Rica initially scored a full point below Singapore on the main 6 metrics, yet ended up ranking 32 places ahead due to its ‘Dystopia + residual’ score. This phenomenon occurring throughout the dataset set us on a path to our final project concept.

After independent study on the meaning of the ‘Dystopia + residual’ score, we found flaws in how it excuses the model to forgo research in cultural differences that influence happiness. We found patterns such as larger residuals typically belonging to happier countries, that there’s a global downturn in residuals, and a hidden bias towards Latin American/Carribean countries having larger residuals.

We found these patterns odd, and what was more odd was that the model delegates this important data to a metric that describes “unexplained happiness.” This directed our project’s focus to be a critique of the World Happiness Report as a, hopefully unintentionally, biased, flawed, and potentially problematic representation of global happiness.

## Final Design

### Design Principles & Color Selection
The presentation applied several design principles to enhance clarity and cohesion. Warm colors like oranges and yellows were chosen to visually reinforce the theme of happiness, with sequential yellow-to-red schemes in charts to aid data readability. Gestalt principles also guided the layout: proximity grouped related information together, similarity was maintained through consistent colors and fonts across slides, and continuity was achieved by keeping a uniform visual style throughout, guiding the viewer's eye naturally from one element to the next.

### Chart Selection and Design
In creating our final presentation, each group member made various graphs that we planned to curate into a final selection that delivered a clear story. Some important choices in our final selection of charts include:
* Simplifying the amount of countries in each chart: 100+ countries are ranked annually, leading to far too many points for some of our line charts. Using a calculated field, a global average was created and overlaid on a graph that showed the specific behavior for a select few countries.
* Minimize redundancy: There are several variables available to be graphed and analyzed, yet most had very similar patterns. Rather than repeatedly showing that happier countries have higher scores across each category, charts were designed to show a wide array of behaviors hidden in the data.
* Storytelling: We aimed to showcase the dataset at a high level before critiquing its accuracy via the ‘Dystopia + residual’ metric. We intentionally ordered our graphs to project a neutral view in the beginning and a more critical attitude by the end. This process of being particular in our order further finetuned our conclusions from the project, that the WHR’s methodology is flawed.

### Inkscape
Due to limitations in Tableau, we selected a few charts to be cleaned up in Inkscape for clarity and consistency. For example, we altered the colors in our boxplot to boost contrast that was initially lost due to our limited color palette. 

## Limitations
A major limitation of the project was understanding WHR’s ‘Dystopia + residual’ metric. Fully understanding its purpose in the dataset required each group member, along with some LLMs, to follow WHR’s documentation. WHR’s description and methodology of combining both categories into a single metric caused confusion and conceptual challenges in understanding our project’s direction early on.

Additionally, while residuals suggest the presence of unmeasured factors influencing wellbeing, they do not identify specific causes. As a result, our analysis cannot conclusively determine which cultural, social, or psychological variables contribute to unexplained happiness differences between countries.

The project also makes generalized claims across different countries. Happiness is subjective, as are some metrics from the WHR, leading to happiness being difficult to measure with one method. With more time, introducing other datasets that account for cultural differences in what constitutes happiness could contribute to a more accurate analysis of global well-being. 

## Use of LLMs
LLMs were used as a supplementary tool throughout the project process. Examples of its use include:
* Better understand ‘Dystopia + residual’ column
* Brainstorming potential visualizations for final presentation
* Assist with Tableau calculated fields logic
All final analyses, critiques, and conclusions were developed by ourselves.
