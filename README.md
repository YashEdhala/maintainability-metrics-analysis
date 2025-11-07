Section 1: Goal, Question, and Metrics (GQM Approach)
Goal
The primary goal of this study is to evaluate the internal quality of open-source Java systems by analyzing their object-oriented design metrics. The study aims to identify patterns and relationships between various software metrics that may influence software maintainability, complexity, and coupling levels.
Questions
1. What are the average values and variations of key object-oriented metrics (LOC, WMC, CBO) across the selected Java projects?
2. How do software size metrics (e.g., Lines of Code) relate to complexity and coupling metrics (e.g., WMC, CBO)?
3. Can we have observable differences in metric patterns in projects with different domains?
Metrics
Metric	Description	Purpose
LOC (Lines of Code)	Total number of lines of code in a class	Measures software size
WMC (Weighted Methods per Class)	Number of methods and their complexity	Indicates class complexity
CBO (Coupling Between Objects)	Number of classes to which a class is coupled	Measures inter-class dependency
Section 2: Subject Programs (Dataset Description)
Five open-source Java projects were selected as the subjects of this empirical study. The projects vary in size, domain, and functionality, providing a diverse dataset for metric-based analysis. The CK tool was used to extract design-level metrics from these systems.
Project Name	Repository Link	Domain / Purpose	Language	LOC	Main Functionality	Contributors
Apache Dubbo	https://github.com/apache/dubbo	Distributed systems, RPC framework	Java	~600K	Provides a high-performance, Java-based RPC framework for building microservices.	612
Apache ShardingSphere	https://github.com/apache/shardingsphere	Database middleware	Java	~900K	Offers data sharding, distributed transactions, and database governance tools.	628
Bazel	https://github.com/bazelbuild/bazel	Build system	Java	~1.2M	Open-source build and test tool supporting large-scale, multi-language projects.	1066
Apache RocketMQ	https://github.com/apache/rocketmq	Messaging and streaming platform	Java	~500K	Provides a distributed messaging and streaming platform for event-driven systems.	557
Facebook Fresco	https://github.com/facebook/fresco	Image loading library	Java	~400K	Efficient image loading and display library for Android applications.	230
We cloned each of these JAVA projects from its public GitHub repository. The selected systems represent different categories (frameworks, middleware, libraries, and tools) to ensure variety in design and structure. The source code for each project was analyzed using the CK-metrics tool to extract class-level metrics like WMC, LOC and CBO. These metrics form the dataset used for our analysis in the next sections.
Section 3: Tool Description
We used the CK-metrics Tool (Chidamber and Kemerer Metrics Calculator) for extracting metrics. It is an open-source Java program developed by Maurício Aniche that calculates several well-known object-oriented design metrics like coupling(CBO), FANIN, FANOUT, WMC, DIT, RFC, LCOM, LOC, LoopQty and many more from Java source code that will help the developer to observe the maintainability of the program.
Tool Overview:
•	Tool Name: CK-Metrics Calculator
•	Version Used: 0.7.1-SNAPSHOT
•	 Repository: https://github.com/mauricioaniche/ck
•	 Language: Java
•	 Execution Command:
  java -jar target/ck-0.7.1-SNAPSHOT-jar-with-dependencies.jar <project_path> true 0
Output: CSV files containing class-, method-, and package-level metrics.
The metrics are calculated automatically for each Java class of the project as mentioned in the above command and stored in a CSV file in a read only type for further statistical analysis.
Reference:
Aniche, M. (2016). CK: Java Code Metrics Tool. Retrieved from https://github.com/mauricioaniche/ck
Section 4: Graphs, report and results
This section presents the results of the empirical study on the effect of class size on software maintainability.
Two relationships were analyzed for each of the five selected open-source Java projects:
LOC vs WMC (class size vs complexity)
LOC vs CBO (class size vs coupling)
Scatter plots were generated for each pair of metrics, and correlation values were calculated to measure the strength of the relationships
