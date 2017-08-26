# Statement

You have to extract, transform and load graph data from 200K local HTML files into a Neo4j database, by:
1. scraping data points from the files
2. analysing the data
3. transforming the data
4. importing the data into the Neo4j database
5. testing/checking every process

Please, answer the following questions:

What ratios of expected work time would you give to each phase?
What tools, frameworks and programming languages would you use to do this?
You have to repeat this chain for up to five sources with different origin data.
What and how would you try to standardize in order to have more reusable code/tools?
You have three people to work on this, what would you assign to them? How would you communicate with each other?

Note we don't expect code, but known tools that solve these situations or a description of how would you design the project code in modules for different tasks. Anything that you can provide from an architectural perspective is valid.

# Answer

### What ratios of expected work time would you give to each phase?

In my experience analyzing data is what takes more time, followed by transforming the data as I do not know which type of data we are talking about. Then I added the most time for testing and checking as it is the hardest and most important part of the process for working with data. 

1. 5%
2. 30%
3. 20%
4. 10%
5. 45%

### What tools, frameworks and programming languages would you use to do this?

I started writing down Scrapy, Jupyter and Pandas to do analysis and python scripts for the transformation BUT Apache Spark it is much better for processing large amounts of data. And looking at that I see that there is an Apache tool that can be used to do web crawl. I never used it but I see that it has plugins for other apache tools And relies on Apache Hadoop for the data structures. I never used this tools before in a project BUT if I would do it for large amount of data I would go with them.

1. Apache Nutch.
2. Jupyter, Pandas & Apache Spark.
3. Python, Apache Spark. 
    a. Get data from Hadoop
    b. Do the transformations
4. Use Cypher scripts to import data into Neo4j. There is a connector Neo4j-Spark-Connector to import data from Spark into Neo4j.
5. I do not know so much about testing strategies for this Apache tools BUT writing tests for all the code it is quite important. The spark applications can have unite testing and I'm sure mocking may be able to be done to be able to have integration testings there. 

### You have to repeat this chain for up to five sources with different origin data. What and how would you try to standardize in order to have more reusable code/tools?

The step on scraping and the one on transforming data has to be more flexible to accomodate different types of transformation for the data.


### You have three people to work on this, what would you assign to them? How would you communicate with each other?

* Person 1: Scraping & Checking every process.
* Person 2: Analyzing 
* Person 3: Transforming and importing data into Neo4j.

About communication I wonder if you mean between the applications? Hadoop can be used to store data during the process before Neo4J. There is a data model that needs to be decided by the Person 2. 