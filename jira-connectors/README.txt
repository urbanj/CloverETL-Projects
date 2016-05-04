***** JIRA Connectors *****

This project contains connectors to JIRA, implemented primarily via subgraphs. All connectors
can be found in graph/subgraph directory.

Contents:
- jobflow/ - implementation of some connectors via jobflow. For comparison with subgraphs
- graph/
	- create_jira_report.grf - creates a report that calculated number of issues matching various JIRA queries
	- testing_search.grf - example call of one JQL search
	-  subgraph/ - connectors to JIRA implemented as subgraphs
		- jira_login.sgrf - performs login to JIRA, returns session
			- not intended to be called by users directly (it's used in other subgraphs)
		- jira_search.sgrf - calls one JQL query and returns matching issues
		- jira_search_multi.sgrf - calls multiple JQL queries (from its input) and returns matching issues and search metadata
		- jira_search_rest.sgrf - performs one REST call for search, needs to be called multiple times for results paging
			- not intended to be called by users directly (it's used in other subgraphs)
	- jobflow/ - graphs used from jobflows
- jira.prm - basic JIRA configuration (URL of your JIRA etc)
- jira_login.prm - set your login credentials here