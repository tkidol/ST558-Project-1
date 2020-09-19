NHL Analysis
================
Todd Idol
9/18/2020

-   [Link to Project Repo](#link-to-project-repo)
-   [Packages](#packages)
    -   [Tidyverse](#tidyverse)
    -   [Rmarkdown](#rmarkdown)
    -   [JSONLite](#jsonlite)
    -   [HTTR](#httr)
-   [NHL API Wrapper](#nhl-api-wrapper)
    -   [Franchise Wrapper](#franchise-wrapper)
    -   [Stats Wrapper](#stats-wrapper)
-   [NHL Franchise APIs](#nhl-franchise-apis)
-   [2017 - 2019 Presidents Cup Teams vs. Low Points Teams
    Analysis](#presidents-cup-teams-vs.-low-points-teams-analysis)
    -   [Data](#data)
-   [Categorical Analysis](#categorical-analysis)
    -   [Total Summaries](#total-summaries)
    -   [Categorical Visuals](#categorical-visuals)
-   [Quantitative Analysis](#quantitative-analysis)
    -   [Summaries](#summaries)
    -   [Visuals](#visuals)

Link to Project Repo
====================

Link to
repo\[<a href="https://github.com/tkidol/ST558-Project-1" class="uri">https://github.com/tkidol/ST558-Project-1</a>\]

Packages
========

Tidyverse
---------

The workhorse of this project for 3 main core packages: DPLYR -
manipulated all of my data (selects, joins, filter, new variables… ),
Tibble for rendering Data Frames more effectively, & () ggplot2 for
discrete & continuous data plots

Rmarkdown
---------

Key to the project for the Rmd file itself including the knitr::
functions for consumable object output (kable) & README.md github doc
output through render()

JSONLite
--------

PUsed to converting API pulled JSON data into R objects

HTTR
----

Per R documentation site: Functions for the most important http verbs:
GET(), HEAD(), PATCH(), PUT(), DELETE() and POST().

NHL API Wrapper
===============

Created 2 wrapper functions to call APIs. One for the Franchise
endpoints taking in endpoint names, team names & franchise ID’s & 1 for
the Team stats taking in modifier names, team names & team ID’s.

Franchise Wrapper
-----------------

    # Franchise Wrapper takes in an API Endpoint (from a list) & Team (either Franchise ID or Common Team name (e.g. "Hurricanes)) & returns distinct API data for analysis.

    # Lists to validate incoming arguments
    FR_Wrapper <- function(endpoint, team = NULL, ...) {
      menu <- FranchiseAPI()
      records <- c("franchise", "totals", "drilldown", "goalie", "skater")
      teamlist <- list(menu[5])
      frIDs <- list(menu[1])
      
    # Validation tests
      if(!(is.character(endpoint))) stop("Invalid Input")
      if(is.character(team)) {
        if ((team %in% teamlist)) stop ("Invalid Input")
      }
       if(is.numeric(team)) {
        if((team %in% frIDs)) stop ("Invalid Input")
      }

      # Conditional logic to pull correct API data
        if(endpoint == "franchise") {
        return(FranchiseAPI())
        
      } else if(endpoint == "totals") { 
         return(TeamTotalsAPI()) 
        
      } else if(endpoint == "drilldown") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Franchise ID`)
          return(TeamDDAPI(team1))
        } else if(is.numeric(team)) {
          return(TeamDDAPI(team))
        }
          
      } else if(endpoint == "goalie") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Franchise ID`)
          return(GoalieAPI(team1))
        } else if(is.numeric(team)) {
          return(GoalieAPI(team))
        }
            
      } else if(endpoint == "skater") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Franchise ID`)
          return(SkaterAPI(team1))
        } else if(is.numeric(team)) {
          return(SkaterAPI(team))
        }
      
      } else {
        return(NULL)
      }
    }

Stats Wrapper
-------------

    # Stat API Wrapper takes API Modifier (from a list) & team (Team ID or Common Team name (e.g. "Hurricanes)), & Season (for the 'roster & season' endpoint) & returns distinct API data. Note: using 'people' API for analysis but not directly accessible through Wrapper. MultiAPI works directly with multiple 'id' input but not through the Wrapper

    # Lists for comparison to validate incoming arguments
    ST_Wrapper <- function(mod, team = NULL, season = 00000000, ...) {
      menu <- FranchiseAPI()
      modifyer <- c("stats", "roster", "person", "nextgame", "priorgame", "expanded", "season")
      teamlist <- list(menu[5])
      teamIDs <- list(menu[4])
     
    # Validation tests 
      if((!is.character(mod) & (mod %in% modifyer))) stop("Invalid Input")
      if(is.character(team)) {
          if ((team %in% teamlist)) stop("Invalid Input")
      }
      if(is.numeric(team)) {
        if((team %in% teamIDs)) stop("Invalid Input")
      }
      if(!length(season) != 8) stop("Invalid Input")
      
    # Conitional logic to pull correct API data
      if(mod == "stats") {
       return(TeamStatsAPI())
        
      } else if(mod == "roster") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Team ID`)
          return(RosterAPI(team1))
        } else if(is.numeric(team)) {
          return(RosterAPI(team))
        }
          
      } else if(mod == "person") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Team ID`)
          return(PersonAPI(team1))
        } else if(is.numeric(team)) {
          return(PersonAPI(team))
        }
            
      } else if(mod == "nextgame") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Team ID`)
          return(NextGAPI(team1))
        } else if(is.numeric(team)) {
          return(NextGAPI(team))
        }
     
      } else if(mod == "priorgame") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Team ID`)
          return(PriorGAPI(team1))
        } else if(is.numeric(team)) {
          return(PriorGAPI(team))
        }  
        
      } else if(mod == "expanded") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Team ID`)
          return(ExpStatsAPI(team1))
        } else if(is.numeric(team)) {
          return(ExpStatsAPI(team))
        }
      
      } else if(mod == "season") {
        if(is.character(team)) { 
          team1 <- filter(menu,`Name` == team) %>% select(`Team ID`)
          return(SeasonAPI(team1))
        } else if(is.numeric(team, season)) {
          return(SeasonAPI(team, season))
        }  

      } else {
        return(NULL)
      }
    }

NHL Franchise APIs
==================

Here are the GET chunks to return APIs associated to the Franchise end
points.

### Main API

    # GET pull for NHL franchise
    FranchiseAPI <- function() {
    franchise <- GET("https://records.nhl.com/site/api/franchise")

    ## As JSON text
    franchise <- content(franchise, "text")

    ## As JSON List
    franchise <- fromJSON(franchise, flatten = TRUE)

    franchise <- franchise[[1]] %>% rename("Franchise ID" = id, "First Season" = firstSeasonId, "Last Season" = lastSeasonId, "Team ID" = mostRecentTeamId, "Name" = teamCommonName, "Location" = teamPlaceName)
    return(franchise)
    }

### Wrapper Test

| Franchise ID | First Season | Last Season | Team ID | Name        | Location  |
|-------------:|-------------:|------------:|--------:|:------------|:----------|
|            1 |     19171918 |          NA |       8 | Canadiens   | Montréal  |
|            2 |     19171918 |    19171918 |      41 | Wanderers   | Montreal  |
|            3 |     19171918 |    19341935 |      45 | Eagles      | St. Louis |
|            4 |     19191920 |    19241925 |      37 | Tigers      | Hamilton  |
|            5 |     19171918 |          NA |      10 | Maple Leafs | Toronto   |
|            6 |     19241925 |          NA |       6 | Bruins      | Boston    |

### Team Totals API

    # GET pull for NHL Team Totals
    TeamTotalsAPI<- function() {
    totals <- GET("https://records.nhl.com/site/api/franchise-team-totals")

    ## As JSON text
    totals <- content(totals, "text")

    ## As JSON List
    totals <- fromJSON(totals, flatten = TRUE)
    return(totals[[1]])
    }

|  id | activeFranchise | firstSeasonId | franchiseId | gameTypeId | gamesPlayed | goalsAgainst | goalsFor | homeLosses | homeOvertimeLosses | homeTies | homeWins | lastSeasonId | losses | overtimeLosses | penaltyMinutes | pointPctg | points | roadLosses | roadOvertimeLosses | roadTies | roadWins | shootoutLosses | shootoutWins | shutouts | teamId | teamName           | ties | triCode | wins |
|----:|----------------:|--------------:|------------:|-----------:|------------:|-------------:|---------:|-----------:|-------------------:|---------:|---------:|-------------:|-------:|---------------:|---------------:|----------:|-------:|-----------:|-------------------:|---------:|---------:|---------------:|-------------:|---------:|-------:|:-------------------|-----:|:--------|-----:|
|   1 |               1 |      19821983 |          23 |          2 |        2937 |         8708 |     8647 |        507 |                 82 |       96 |      783 |           NA |   1181 |            162 |          44397 |    0.5330 |   3131 |        674 |                 80 |      123 |      592 |             79 |           78 |      193 |      1 | New Jersey Devils  |  219 | NJD     | 1375 |
|   2 |               1 |      19821983 |          23 |          3 |         257 |          634 |      697 |         53 |                  0 |       NA |       74 |           NA |    120 |              0 |           4266 |    0.0039 |      2 |         67 |                  0 |       NA |       63 |              0 |            0 |       25 |      1 | New Jersey Devils  |   NA | NJD     |  137 |
|   3 |               1 |      19721973 |          22 |          2 |        3732 |        11779 |    11889 |        674 |                 81 |      170 |      942 |           NA |   1570 |            159 |          57422 |    0.5115 |   3818 |        896 |                 78 |      177 |      714 |             67 |           82 |      167 |      2 | New York Islanders |  347 | NYI     | 1656 |
|   4 |               1 |      19721973 |          22 |          3 |         294 |          857 |      935 |         50 |                  3 |       NA |       90 |           NA |    133 |              0 |           5564 |    0.0136 |      8 |         83 |                  2 |       NA |       71 |              0 |            0 |       12 |      2 | New York Islanders |   NA | NYI     |  161 |
|   5 |               1 |      19261927 |          10 |          2 |        6504 |        19863 |    19864 |       1132 |                 73 |      448 |     1600 |           NA |   2693 |            147 |          85564 |    0.5125 |   6667 |       1561 |                 74 |      360 |     1256 |             66 |           78 |      403 |      3 | New York Rangers   |  808 | NYR     | 2856 |
|   6 |               1 |      19261927 |          10 |          3 |         518 |         1447 |     1404 |        104 |                  0 |        1 |      137 |           NA |    266 |              0 |           8181 |    0.0000 |      0 |        162 |                  0 |        7 |      107 |              0 |            0 |       44 |      3 | New York Rangers   |    8 | NYR     |  244 |

### Team Drill Down API

    TeamDDAPI <- function(id, ...) {
    # GET pull for NHL Team Totals
    drill_down <- GET(paste0("https://records.nhl.com/site/api/franchise-season-records?cayenneExp=franchiseId=", id))

    ## As JSON text
    drill_down <- content(drill_down, "text")

    ## As JSON List
    drill_down <- fromJSON(drill_down, flatten = TRUE)
    return(drill_down[[1]])
    }

### Wrapper test

|  id | fewestGoals | fewestGoalsAgainst | fewestGoalsAgainstSeasons | fewestGoalsSeasons | fewestLosses | fewestLossesSeasons | fewestPoints | fewestPointsSeasons | fewestTies | fewestTiesSeasons | fewestWins | fewestWinsSeasons | franchiseId | franchiseName       | homeLossStreak | homeLossStreakDates       | homePointStreak | homePointStreakDates      | homeWinStreak | homeWinStreakDates        | homeWinlessStreak | homeWinlessStreakDates    | lossStreak | lossStreakDates           | mostGameGoals | mostGameGoalsDates                                                                                                     | mostGoals | mostGoalsAgainst | mostGoalsAgainstSeasons | mostGoalsSeasons | mostLosses | mostLossesSeasons | mostPenaltyMinutes | mostPenaltyMinutesSeasons | mostPoints | mostPointsSeasons | mostShutouts | mostShutoutsSeasons | mostTies | mostTiesSeasons | mostWins | mostWinsSeasons | pointStreak | pointStreakDates          | roadLossStreak | roadLossStreakDates       | roadPointStreak | roadPointStreakDates      | roadWinStreak | roadWinStreakDates        | roadWinlessStreak | roadWinlessStreakDates                               | winStreak | winStreakDates                                                                  | winlessStreak | winlessStreakDates |
|----:|------------:|-------------------:|:--------------------------|:-------------------|-------------:|:--------------------|-------------:|:--------------------|-----------:|:------------------|-----------:|:------------------|------------:|:--------------------|---------------:|:--------------------------|----------------:|:--------------------------|--------------:|:--------------------------|------------------:|:--------------------------|-----------:|:--------------------------|--------------:|:-----------------------------------------------------------------------------------------------------------------------|----------:|-----------------:|:------------------------|:-----------------|-----------:|:------------------|-------------------:|:--------------------------|-----------:|:------------------|-------------:|:--------------------|---------:|:----------------|---------:|:----------------|------------:|:--------------------------|---------------:|:--------------------------|----------------:|:--------------------------|--------------:|:--------------------------|------------------:|:-----------------------------------------------------|----------:|:--------------------------------------------------------------------------------|:--------------|:-------------------|
|  12 |         171 |                202 | 1998-99 (82)              | 2002-03 (82)       |           22 | 2005-06 (82)        |           45 | 1982-83 (80)        |          4 | 1985-86 (80)      |         19 | 1982-83 (80)      |          26 | Carolina Hurricanes |              8 | Mar 14 2013 - Apr 09 2013 |              15 | Dec 13 2005 - Jan 28 2006 |            12 | Feb 20 2009 - Apr 07 2009 |                13 | Jan 15 1985 - Mar 10 1985 |          9 | Feb 19 1983 - Mar 08 1983 |            11 | Feb 12 1984 - EDM 0 @ HFD 11, Oct 19 1985 - MTL 6 @ HFD 11, Jan 17 1986 - QUE 6 @ HFD 11, Mar 15 1986 - CHI 4 @ HFD 11 |       332 |              403 | 1982-83 (80)            | 1985-86 (80)     |         54 | 1982-83 (80)      |               2354 | 1992-93 (84)              |        112 | 2005-06 (82)      |            8 | 1998-99 (82)        |       19 | 1979-80 (80)    |       52 | 2005-06 (82)    |          13 | Mar 09 2017 - Mar 30 2017 |             13 | Dec 18 1982 - Feb 05 1983 |              12 | Feb 23 2004 - Mar 27 2004 |             6 | Nov 10 1990 - Dec 07 1990 |                15 | Nov 11 1979 - Jan 09 1980, Jan 07 2003 - Mar 02 2003 |         9 | Oct 22 2005 - Nov 11 2005, Dec 31 2005 - Jan 19 2006, Mar 18 2009 - Apr 07 2009 | NA            | NA                 |

### Goalie API

    GoalieAPI <- function(id, ...) {
    # GET pull for NHL Team Totals
    goalie <- GET(paste0("https://records.nhl.com/site/api/franchise-goalie-records?cayenneExp=franchiseId=", id))

    ## As JSON text
    goalie <- content(goalie, "text")

    ## As JSON List
    goalie <- fromJSON(goalie, flatten = TRUE)
    return(goalie[[1]])
    }

### Wrapper Test

|  id | activePlayer | firstName | franchiseId | franchiseName      | gameTypeId | gamesPlayed | lastName   | losses | mostGoalsAgainstDates  | mostGoalsAgainstOneGame | mostSavesDates         | mostSavesOneGame | mostShotsAgainstDates | mostShotsAgainstOneGame | mostShutoutsOneSeason | mostShutoutsSeasonIds                  | mostWinsOneSeason | mostWinsSeasonIds  | overtimeLosses | playerId | positionCode | rookieGamesPlayed | rookieShutouts | rookieWins | seasons | shutouts | ties | wins |
|----:|:-------------|:----------|------------:|:-------------------|-----------:|------------:|:-----------|-------:|:-----------------------|------------------------:|:-----------------------|-----------------:|:----------------------|------------------------:|----------------------:|:---------------------------------------|------------------:|:-------------------|---------------:|---------:|:-------------|------------------:|---------------:|-----------:|--------:|---------:|-----:|-----:|
| 262 | FALSE        | Patrick   |          27 | Colorado Avalanche |          2 |         478 | Roy        |    140 | 1999-11-26             |                       7 | 1997-12-10             |               51 | 1997-12-10            |                      53 |                     9 | 20012002                               |                40 | 20002001           |             NA |  8451033 | G            |                NA |             NA |         NA |       8 |       37 |   65 |  262 |
| 325 | TRUE         | Semyon    |          27 | Colorado Avalanche |          2 |         389 | Varlamov   |    156 | 2013-12-05             |                       8 | 2017-11-02             |               57 | 2017-11-02            |                      60 |                     5 | 20142015                               |                41 | 20132014           |             38 |  8473575 | G            |                NA |             NA |         NA |       8 |       21 |    0 |  183 |
| 358 | FALSE        | Craig     |          27 | Colorado Avalanche |          2 |          67 | Billington |     23 | 1997-04-04             |                       7 | 1998-01-15, 1996-10-28 |               40 | 1998-01-15            |                      42 |                     1 | 19961997, 19971998                     |                11 | 19961997, 19981999 |             NA |  8445470 | G            |                NA |             NA |         NA |       3 |        2 |    7 |   30 |
| 360 | FALSE        | Dan       |          27 | Colorado Avalanche |          2 |         226 | Bouchard   |     80 | 1983-03-08             |                      11 | 1982-01-16             |               47 | 1982-01-16            |                      51 |                     2 | 19801981                               |                29 | 19831984           |             NA |  8445609 | G            |                NA |             NA |         NA |       5 |        5 |   36 |  107 |
| 383 | FALSE        | Jacques   |          27 | Colorado Avalanche |          2 |          58 | Cloutier   |     26 | 1991-02-23             |                      10 | 1991-02-23             |               49 | 1991-02-23            |                      59 |                     0 | 19901991, 19911992, 19921993, 19931994 |                 6 | 19911992           |             NA |  8446089 | G            |                NA |             NA |         NA |       4 |        0 |    7 |   12 |
| 390 | FALSE        | Michel    |          27 | Colorado Avalanche |          2 |          62 | Dion       |     33 | 1980-10-12, 1980-04-03 |                       8 | 1980-01-19             |               48 | 1980-01-19            |                      50 |                     2 | 19791980                               |                15 | 19791980           |             NA |  8446429 | G            |                NA |             NA |         NA |       2 |        2 |    9 |   15 |

### Skater API

    SkaterAPI <- function(id, ...) {
    # GET pull for NHL Team Totals
    skater <- GET(paste0("https://records.nhl.com/site/api/franchise-skater-records?cayenneExp=franchiseId=", id))

    ## As JSON text
    skater <- content(skater, "text")

    ## As JSON List
    skater <- fromJSON(skater, flatten = TRUE)
    return(skater[[1]])
    }

### Wrapper Test

|    id | activePlayer | assists | firstName | franchiseId | franchiseName      | gameTypeId | gamesPlayed | goals | lastName | mostAssistsGameDates                           | mostAssistsOneGame | mostAssistsOneSeason | mostAssistsSeasonIds | mostGoalsGameDates                             | mostGoalsOneGame | mostGoalsOneSeason | mostGoalsSeasonIds | mostPenaltyMinutesOneSeason | mostPenaltyMinutesSeasonIds | mostPointsGameDates                            | mostPointsOneGame | mostPointsOneSeason | mostPointsSeasonIds | penaltyMinutes | playerId | points | positionCode | rookiePoints | seasons |
|------:|:-------------|--------:|:----------|------------:|:-------------------|-----------:|------------:|------:|:---------|:-----------------------------------------------|-------------------:|---------------------:|:---------------------|:-----------------------------------------------|-----------------:|-------------------:|:-------------------|----------------------------:|:----------------------------|:-----------------------------------------------|------------------:|--------------------:|:--------------------|---------------:|---------:|-------:|:-------------|-------------:|--------:|
| 16889 | FALSE        |       0 | Billy     |           2 | Montreal Wanderers |          2 |           2 |     1 | Bell     | 1917-12-19, 1917-12-29                         |                  0 |                    0 | 19171918             | 1917-12-19                                     |                1 |                  1 | 19171918           |                           0 | 19171918                    | 1917-12-19                                     |                 1 |                   1 | 19171918            |              0 |  8445044 |      1 | C            |            1 |       1 |
| 16897 | FALSE        |       0 | Gerry     |           2 | Montreal Wanderers |          2 |           4 |     0 | Geran    | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                  0 |                    0 | 19171918             | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                0 |                  0 | 19171918           |                           0 | 19171918                    | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                 0 |                   0 | 19171918            |              0 |  8446580 |      0 | C            |            0 |       1 |
| 16901 | FALSE        |       1 | Harry     |           2 | Montreal Wanderers |          2 |           4 |     6 | Hyland   | 1917-12-29                                     |                  1 |                    1 | 19171918             | 1917-12-19                                     |                5 |                  6 | 19171918           |                           6 | 19171918                    | 1917-12-19                                     |                 5 |                   7 | 19171918            |              6 |  8447013 |      7 | R            |            7 |       1 |
| 16903 | FALSE        |       0 | Jack      |           2 | Montreal Wanderers |          2 |           1 |     0 | Marks    | 1917-12-29                                     |                  0 |                    0 | 19171918             | 1917-12-29                                     |                0 |                  0 | 19171918           |                           0 | 19171918                    | 1917-12-29                                     |                 0 |                   0 | 19171918            |              0 |  8447616 |      0 | L            |            0 |       1 |
| 16904 | FALSE        |       1 | Jack      |           2 | Montreal Wanderers |          2 |           4 |     3 | McDonald | 1917-12-29                                     |                  1 |                    1 | 19171918             | 1917-12-19, 1917-12-22, 1917-12-26             |                1 |                  3 | 19171918           |                           3 | 19171918                    | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                 1 |                   4 | 19171918            |              3 |  8447761 |      4 | L            |            4 |       1 |
| 16908 | FALSE        |       0 | George    |           2 | Montreal Wanderers |          2 |           4 |     0 | O’Grady  | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                  0 |                    0 | 19171918             | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                0 |                  0 | 19171918           |                           0 | 19171918                    | 1917-12-19, 1917-12-22, 1917-12-26, 1917-12-29 |                 0 |                   0 | 19171918            |              0 |  8448052 |      0 | D            |            0 |       1 |

### Complete Team Stats

    TeamStatsAPI <- function() {
    stats <- GET("https://statsapi.web.nhl.com/api/v1/teams")

    ## As JSON text
    stats <- content(stats, "text")

    ## As JSON List
    stats <- fromJSON(stats, flatten = TRUE)
    return(stats[[2]])
    }

### Wrapper Test

|  id | name                | link            | abbreviation | teamName  | locationName | firstYearOfPlay | shortName    | officialSiteUrl                                                                                 | franchiseId | active | venue.name            | venue.link          | venue.city   | venue.id | venue.timeZone.id | venue.timeZone.offset | venue.timeZone.tz | division.id | division.name | division.nameShort | division.link        | division.abbreviation | conference.id | conference.name | conference.link       | franchise.franchiseId | franchise.teamName | franchise.link        |
|----:|:--------------------|:----------------|:-------------|:----------|:-------------|:----------------|:-------------|:------------------------------------------------------------------------------------------------|------------:|:-------|:----------------------|:--------------------|:-------------|---------:|:------------------|----------------------:|:------------------|------------:|:--------------|:-------------------|:---------------------|:----------------------|--------------:|:----------------|:----------------------|----------------------:|:-------------------|:----------------------|
|   1 | New Jersey Devils   | /api/v1/teams/1 | NJD          | Devils    | New Jersey   | 1982            | New Jersey   | <a href="http://www.newjerseydevils.com/" class="uri">http://www.newjerseydevils.com/</a>       |          23 | TRUE   | Prudential Center     | /api/v1/venues/null | Newark       |       NA | America/New\_York |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    23 | Devils             | /api/v1/franchises/23 |
|   2 | New York Islanders  | /api/v1/teams/2 | NYI          | Islanders | New York     | 1972            | NY Islanders | <a href="http://www.newyorkislanders.com/" class="uri">http://www.newyorkislanders.com/</a>     |          22 | TRUE   | Barclays Center       | /api/v1/venues/5026 | Brooklyn     |     5026 | America/New\_York |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    22 | Islanders          | /api/v1/franchises/22 |
|   3 | New York Rangers    | /api/v1/teams/3 | NYR          | Rangers   | New York     | 1926            | NY Rangers   | <a href="http://www.newyorkrangers.com/" class="uri">http://www.newyorkrangers.com/</a>         |          10 | TRUE   | Madison Square Garden | /api/v1/venues/5054 | New York     |     5054 | America/New\_York |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    10 | Rangers            | /api/v1/franchises/10 |
|   4 | Philadelphia Flyers | /api/v1/teams/4 | PHI          | Flyers    | Philadelphia | 1967            | Philadelphia | <a href="http://www.philadelphiaflyers.com/" class="uri">http://www.philadelphiaflyers.com/</a> |          16 | TRUE   | Wells Fargo Center    | /api/v1/venues/5096 | Philadelphia |     5096 | America/New\_York |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    16 | Flyers             | /api/v1/franchises/16 |
|   5 | Pittsburgh Penguins | /api/v1/teams/5 | PIT          | Penguins  | Pittsburgh   | 1967            | Pittsburgh   | <a href="http://pittsburghpenguins.com/" class="uri">http://pittsburghpenguins.com/</a>         |          17 | TRUE   | PPG Paints Arena      | /api/v1/venues/5034 | Pittsburgh   |     5034 | America/New\_York |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    17 | Penguins           | /api/v1/franchises/17 |
|   6 | Boston Bruins       | /api/v1/teams/6 | BOS          | Bruins    | Boston       | 1924            | Boston       | <a href="http://www.bostonbruins.com/" class="uri">http://www.bostonbruins.com/</a>             |           6 | TRUE   | TD Garden             | /api/v1/venues/5085 | Boston       |     5085 | America/New\_York |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                     6 | Bruins             | /api/v1/franchises/6  |

### Roster API

    RosterAPI <- function(id, ...) {
    roster <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "/?expand=team.roster"))

    ## As JSON text
    roster <- content(roster, "text")

    ## As JSON List
    roster <- fromJSON(roster, flatten = TRUE)
    franchiseId <- roster$teams$franchiseId
    roster <- as_tibble(roster[[2]]$roster.roster[[1]]) %>% mutate("franchiseId" = franchiseId) %>% 
    select(franchiseId, everything())
    return(roster)
    }

### Wrapper Test

| franchiseId | jerseyNumber | person.id | person.fullName    | person.link            | position.code | position.name | position.type | position.abbreviation |
|------------:|:-------------|----------:|:-------------------|:-----------------------|:--------------|:--------------|:--------------|:----------------------|
|          24 | 63           |   8478063 | Shane Gersich      | /api/v1/people/8478063 | L             | Left Wing     | Forward       | LW                    |
|          24 | 30           |   8478492 | Ilya Samsonov      | /api/v1/people/8478492 | G             | Goalie        | Goalie        | G                     |
|          24 | 40           |   8479516 | Garrett Pilon      | /api/v1/people/8479516 | C             | Center        | Forward       | C                     |
|          24 | 27           |   8480823 | Alexander Alexeyev | /api/v1/people/8480823 | D             | Defenseman    | Defenseman    | D                     |
|          24 | 17           |   8469454 | Ilya Kovalchuk     | /api/v1/people/8469454 | L             | Left Wing     | Forward       | LW                    |
|          24 | 8            |   8471214 | Alex Ovechkin      | /api/v1/people/8471214 | L             | Left Wing     | Forward       | LW                    |

### Person API

    PersonAPI <- function(id, ...) {
    person <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "/?expand=person.names"))

    ## As JSON text
    person <- content(person, "text")

    ## As JSON List
    person <- fromJSON(person, flatten = TRUE)
    return(person[[2]])
    }

### Wrapper Test

|  id | name            | link             | abbreviation | teamName | locationName | firstYearOfPlay | shortName | officialSiteUrl                                                             | franchiseId | active | venue.name             | venue.link          | venue.city | venue.timeZone.id    | venue.timeZone.offset | venue.timeZone.tz | division.id | division.name | division.nameShort | division.link        | division.abbreviation | conference.id | conference.name | conference.link       | franchise.franchiseId | franchise.teamName | franchise.link        |
|----:|:----------------|:-----------------|:-------------|:---------|:-------------|:----------------|:----------|:----------------------------------------------------------------------------|------------:|:-------|:-----------------------|:--------------------|:-----------|:---------------------|----------------------:|:------------------|------------:|:--------------|:-------------------|:---------------------|:----------------------|--------------:|:----------------|:----------------------|----------------------:|:-------------------|:----------------------|
|  28 | San Jose Sharks | /api/v1/teams/28 | SJS          | Sharks   | San Jose     | 1990            | San Jose  | <a href="http://www.sjsharks.com/" class="uri">http://www.sjsharks.com/</a> |          29 | TRUE   | SAP Center at San Jose | /api/v1/venues/null | San Jose   | America/Los\_Angeles |                    -7 | PDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    29 | Sharks             | /api/v1/franchises/29 |

### People API (not in wrapper - internal use)

    # Detailed substitue for PersonAPI
    PeopleAPI <- function(id, ...) {
    people <- GET(paste0("https://statsapi.web.nhl.com/api/v1/people/", id))

    ## As JSON text
    people <- content(people, "text")

    ## As JSON List
    people <- fromJSON(people, flatten = TRUE)
    return(people[[2]])
    }

### Team Player Function (for internal analysis use)

    ## New DF combining People with Roster for additional player stats
    TeamPlayer <- function (id, ...) {
      
    # Get player ID from Roster
    playerId <- pull(RosterAPI(id), person.id)

    # Seed data frame
    players <- as.data.frame(PeopleAPI(playerId[1]))

    # Iterate player IDs over People API to build data frame 
      for (i in 2:length(playerId)) {
        players[i, ] <- (PeopleAPI(playerId[i]))
      }

    # Trim for relevant data for analysis
    players <- players %>% select(currentTeam.id, id, fullName, birthCountry, primaryPosition.name)
    if(length(players$currentTeam.id) > 2) {
      players$currentTeam.id = players$currentTeam.id[[1]]
    }
    return(players) 
    }

### Next Game API

    NextGAPI <- function(id, ...) {
    nextG <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.schedule.next"))

    ## As JSON text
    nextG <- content(nextG, "text")

    ## As JSON List
    nextG <- fromJSON(nextG, flatten = TRUE)
    nextG <- nextG[[2]]$nextGameSchedule.dates[[1]]$games[[1]]
    return(nextG)
    }

### Wrapper Test

|     gamePk | link                              | gameType | season   | gameDate             | status.abstractGameState | status.codedGameState | status.detailedState | status.statusCode | status.startTimeTBD | teams.away.score | teams.away.leagueRecord.wins | teams.away.leagueRecord.losses | teams.away.leagueRecord.ot | teams.away.leagueRecord.type | teams.away.team.id | teams.away.team.name | teams.away.team.link | teams.home.score | teams.home.leagueRecord.wins | teams.home.leagueRecord.losses | teams.home.leagueRecord.ot | teams.home.leagueRecord.type | teams.home.team.id | teams.home.team.name | teams.home.team.link | venue.id | venue.name   | venue.link          | content.link                    |
|-----------:|:----------------------------------|:---------|:---------|:---------------------|:-------------------------|:----------------------|:---------------------|:------------------|:--------------------|-----------------:|-----------------------------:|-------------------------------:|---------------------------:|:-----------------------------|-------------------:|:---------------------|:---------------------|-----------------:|-----------------------------:|-------------------------------:|---------------------------:|:-----------------------------|-------------------:|:---------------------|:---------------------|---------:|:-------------|:--------------------|:--------------------------------|
| 2019030411 | /api/v1/game/2019030411/feed/live | P        | 20192020 | 2020-09-19T23:30:00Z | Preview                  | 1                     | Scheduled            | 1                 | FALSE               |                0 |                           13 |                              8 |                          0 | league                       |                 25 | Dallas Stars         | /api/v1/teams/25     |                0 |                           14 |                              5 |                          0 | league                       |                 14 | Tampa Bay Lightning  | /api/v1/teams/14     |     5100 | Rogers Place | /api/v1/venues/5100 | /api/v1/game/2019030411/content |

### Prior Game API

    PriorGAPI <- function(id, ...) {
    priorG <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.schedule.previous"))

    ## As JSON text
    priorG <- content(priorG, "text")

    ## As JSON List
    priorG <- fromJSON(priorG, flatten = TRUE)
    priorG <- priorG[[2]]$previousGameSchedule.dates
    return(priorG)
    }

### Wrapper Test

<table class="kable_wrapper">
<tbody>
<tr>
<td>

| date       | totalItems | totalEvents | totalGames | totalMatches | games                                                                                                                                                                                                                                                                                                                                           | events | matches |
|:-----------|-----------:|------------:|-----------:|-------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------|:--------|
| 2020-03-11 |          1 |           0 |          1 |            0 | 2019021079 , /api/v1/game/2019021079/feed/live, R , 20192020 , 2020-03-12T00:00:00Z , Final , 7 , Final , 7 , FALSE , 2 , 29 , 36 , 5 , league , 28 , San Jose Sharks , /api/v1/teams/28 , 6 , 32 , 30 , 8 , league , 16 , Chicago Blackhawks , /api/v1/teams/16 , 5092 , United Center , /api/v1/venues/5092 , /api/v1/game/2019021079/content | NULL   | NULL    |

</td>
</tr>
</tbody>
</table>

### Expanded Stats API

    ExpStatsAPI <- function(id, ...) {
    expStats <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.stats"))

    ## As JSON text
    expStats <- content(expStats, "text")

    ## As JSON List
    expStats <- fromJSON(expStats, flatten = TRUE)
    expStats <- as.data.frame(expStats[[2]]$teamStats[[1]]$splits)
    return(expStats)
    }

### Wrapper Test

| stat.gamesPlayed | stat.wins | stat.losses | stat.ot | stat.pts | stat.ptPctg | stat.goalsPerGame | stat.goalsAgainstPerGame | stat.evGGARatio | stat.powerPlayPercentage | stat.powerPlayGoals | stat.powerPlayGoalsAgainst | stat.powerPlayOpportunities | stat.penaltyKillPercentage | stat.shotsPerGame | stat.shotsAllowed | stat.winScoreFirst | stat.winOppScoreFirst | stat.winLeadFirstPer | stat.winLeadSecondPer | stat.winOutshootOpp | stat.winOutshotByOpp | stat.faceOffsTaken | stat.faceOffsWon | stat.faceOffsLost | stat.faceOffWinPercentage | stat.shootingPctg | stat.savePctg | stat.penaltyKillOpportunities | stat.savePctRank | stat.shootingPctRank | team.id | team.name       | team.link        |
|-----------------:|:----------|:------------|:--------|:---------|:------------|:------------------|:-------------------------|:----------------|:-------------------------|:--------------------|:---------------------------|:----------------------------|:---------------------------|:------------------|:------------------|:-------------------|:----------------------|:---------------------|:----------------------|:--------------------|:---------------------|:-------------------|:-----------------|:------------------|:--------------------------|------------------:|--------------:|:------------------------------|:-----------------|:---------------------|--------:|:----------------|:-----------------|
|               70 | 29        | 36          | 5       | 63       | 45.0        | 2.571             | 3.214                    | 0.7593          | 17.5                     | 33                  | 32                         | 189                         | 85.7                       | 30.0143           | 30.5714           | 0.625              | 0.237                 | 0.737                | 0.87                  | 0.417               | 0.419                | 3817               | 1868             | 1949              | 48.9                      |               8.6 |         0.895 | NA                            | NA               | NA                   |      28 | San Jose Sharks | /api/v1/teams/28 |
|               NA | 28th      | 30th        | 30th    | 29th     | 29th        | 28th              | 27th                     | 30th            | 23rd                     | 26th                | 3rd                        | 28th                        | 1st                        | 26th              | 10th              | 28th               | 25th                  | 18th                 | 13th                  | 25th                | 25th                 | 29th               | 28th             | 9th               | 24th                      |                NA |            NA | 25th                          | 30th             | 27th                 |      28 | San Jose Sharks | /api/v1/teams/28 |

### Season API (tested in Data Collection)

    SeasonAPI <- function(id, season, ...) {
    season <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.roster&season=", season))

    ## As JSON text
    season <- content(season, "text")

    ## As JSON List
    season <- fromJSON(season, flatten = TRUE)
    franchiseId <- season$teams$franchiseId
    teamName <- season$teams$teamName
    season <- as_tibble((season[[2]]$roster.roster[[1]])) %>% mutate("franchiseId" = franchiseId, "teamName" = teamName) %>% select(franchiseId, everything())
    return(season)
    }

### Multi Team API (no wrapper but functions directly)

    MultiAPI <- function(id, ...) {
    multi <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", "?teamId=", id))

    ## As JSON text
    multi <- content(multi, "text")

    ## As JSON List
    multi <- fromJSON(multi, flatten = TRUE)
    return(multi[[2]])
    }

### Playoff API (void of valuable info)

    PlayoffAPI <- function(id, ...) {
    playoff <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?stats=statsSingleSeasonPlayoffs"))

    ## As JSON text
    playoff <- content(playoff, "text")

    ## As JSON List
    playoff <- fromJSON(playoff, flatten = TRUE)
    return(playoff[[2]])
    }

2017 - 2019 Presidents Cup Teams vs. Low Points Teams Analysis
==============================================================

Data
----

The NHL team with the highest regular season points (2 for ea win / 1
for ea overtime loss) is awarded the league’s Presidents Cup. The data
used for the analysis is taken for a comparison of the 2017 - 2019
Presidents Cup Winners (Capitals, Predators, Lightning) vs the
corresponding “Low Points Teams” (Avalanche, Sabres, Senators).
SeasonAPI was used to pull Player info for each of the six teams for
corresponding years. This was mutated & joined to the PeopleAPI data to
get nationalities for each Player (factored into USA, Canada, European
groups). That data was then joined to the SkaterAPI to get career stats
on which the Rosters were analyzed.

    # Roster for last 2 seasons, high points team (presidents cup) low points team
    pres17 <- SeasonAPI(15, 20162017)
    last17 <- SeasonAPI(21, 20162017)
    pres18 <- SeasonAPI(18, 20172018)
    last18 <- SeasonAPI(7, 20172018)
    pres19 <- SeasonAPI(14, 20182019)
    last19 <- SeasonAPI(9, 20182019)

    # Combine results into single DS & add year & finish
    PresLast <- bind_rows(pres17, last17, pres18, last18, pres19, last19)
    PresLast <- mutate(PresLast, year = 
                      ifelse((PresLast$teamName == "Capitals") | (PresLast$teamName == "Avalanche"), 17,
                      ifelse((PresLast$teamName == "Predators") | (PresLast$teamName == "Sabres"), 18, 19)))
    PresLast <- mutate(PresLast, rank = ifelse((PresLast$teamName == "Capitals") | (PresLast$teamName == "Predators") | (PresLast$teamName == "Lightning"), "First", "Last"))
    PresLast <- PresLast %>% select(franchiseId, teamName, year, rank, person.id, person.fullName, jerseyNumber, position.code)


    # Franchise ID's for SkaterAPI argument
    frIdList <- c(pres17$franchiseId[1], last17$franchiseId[1], pres18$franchiseId[1],last18$franchiseId[1], pres19$franchiseId[1], last19$franchiseId[1])

    # Skater for detailed stats
    PresLast_Skater <- lapply(frIdList, SkaterAPI)
    PresLast_Skater <- bind_rows(PresLast_Skater)

    # Combine results into single DS
    PresLast_Skater <- PresLast_Skater %>% rename("person.id" = playerId) 

    # Join Preslast & Preslast_Skater fo Skaters on Pres-last Teams / Seasons for analysis
    PL_SK_Season <- inner_join(PresLast, PresLast_Skater) 
    PL_SK_Season <-as_tibble(PL_SK_Season) %>% select(franchiseId, teamName, year, rank, person.id, person.fullName, jerseyNumber, position.code, seasons, penaltyMinutes, goals, assists, mostPointsOneSeason) %>% distinct()

    # Get additional categorical stats for Players
    Season_People <- lapply(PL_SK_Season$person.id, PeopleAPI)
    Season_People <- bind_rows(Season_People) %>% select(id, nationality) %>% mutate("person.id" = id)

    # Create regions for categorical analysis
    PL_SK_Season <- inner_join(PL_SK_Season, Season_People)
    PL_SK_Season <- mutate(PL_SK_Season, country = ifelse((nationality == "USA"), "USA",
                                                   ifelse((nationality == "CAN"), "CAN", "EUR")))

    # Create Average PM & Points stats for Players
    PL_SK_Season <- PL_SK_Season %>% mutate(AveragePM = round((penaltyMinutes/seasons), 2), TotalPoints = (goals+assists), AverageTP = round((goals+assists)/seasons), 2)

    # Select relevant variables for analysis
    PL_SK_Season <- PL_SK_Season %>% select(franchiseId, teamName, year, rank, person.fullName, country, position.code, seasons, AveragePM, AverageTP) %>% distinct()

    # Rename for Graphical & Table prentation
    PL_SK_Season <- PL_SK_Season %>% rename("Franchise ID" = franchiseId, "Team" = teamName, "Year" = year, "Finish" = rank, "Name" = person.fullName, "Country" = country, "Position" = position.code, "Player Seasons" = seasons, "Avg Penalty Min" = AveragePM, "Avg Total Pts" = AverageTP)

    # Create factor for Team Finish
    PL_SK_Season$Finish <- as.factor(PL_SK_Season$Finish)

    # Print sample table for report
    kable(head(PL_SK_Season), caption = "Preview of 2017 - 2019 Team Rosters: Presidents Cup vs Last Place")

| Franchise ID | Team     | Year | Finish | Name            | Country | Position | Player Seasons | Avg Penalty Min | Avg Total Pts |
|-------------:|:---------|-----:|:-------|:----------------|:--------|:---------|---------------:|----------------:|--------------:|
|           24 | Capitals |   17 | First  | Brooks Orpik    | USA     | D        |              5 |           47.60 |            12 |
|           24 | Capitals |   17 | First  | Justin Williams | CAN     | R        |              2 |           43.00 |            50 |
|           24 | Capitals |   17 | First  | Alex Ovechkin   | EUR     | L        |             15 |           47.93 |            85 |
|           24 | Capitals |   17 | First  | Daniel Winnik   | CAN     | L        |              2 |           35.50 |            15 |
|           24 | Capitals |   17 | First  | T.J. Oshie      | USA     | R        |              5 |           32.60 |            51 |
|           24 | Capitals |   17 | First  | Matt Niskanen   | USA     | D        |              5 |           38.80 |            31 |

Preview of 2017 - 2019 Team Rosters: Presidents Cup vs Last Place

Categorical Analysis
====================

Categories for Player Countries (regionalized), Positions (by code), &
Team Finish.

Total Summaries
---------------

    Pos_Ctry_table <- table(PL_SK_Season$Position, PL_SK_Season$Country)
    kable(Pos_Ctry_table, caption = "Player Position by Country")

|     | CAN | EUR | USA |
|:----|----:|----:|----:|
| C   |  29 |  11 |  13 |
| D   |  33 |  18 |  16 |
| L   |  18 |  14 |   7 |
| R   |  13 |   6 |  12 |

Player Position by Country

### Summaries by First Place Teams

    First <- filter(PL_SK_Season, PL_SK_Season$Finish == "First")
    Pos_Ctry1_table <- table(First$Position, First$Country)
    kable(Pos_Ctry1_table, caption = "Presidents Cup Winners")

|     | CAN | EUR | USA |
|:----|----:|----:|----:|
| C   |  14 |   5 |   4 |
| D   |  10 |  10 |   8 |
| L   |   5 |   7 |   3 |
| R   |   5 |   4 |   5 |

Presidents Cup Winners

### Summaries by Last Place Teams

    Last <- filter(PL_SK_Season, PL_SK_Season$Finish == "Last")
    Pos_Ctry2_table <- table(Last$Position, Last$Country)
    kable(Pos_Ctry2_table, caption = "Last Place Players")

|     | CAN | EUR | USA |
|:----|----:|----:|----:|
| C   |  15 |   6 |   9 |
| D   |  23 |   8 |   8 |
| L   |  13 |   7 |   4 |
| R   |   8 |   2 |   7 |

Last Place Players

Categorical Visuals
-------------------

### 1 Factor

The most interesting finding from the single category plot is the
smaller roster size of the 3 First Place teams. This could indicate
fewer injuries or the fact that the Last Place teams were juggling
lineups and bringing in players from their minor league ranks or through
trades.

    # bar plot of Team Finish
    FinPlot <- ggplot(PL_SK_Season, aes(x = Finish), color = "blue") 
    FinPlot + geom_bar() + labs(x = "Player Finish")

![](README_files/figure-gfm/univariate%20bar%20graphs-1.png)<!-- -->

    # bar plot of Team Finish
    COplot <- ggplot(PL_SK_Season, aes(x = Country), color = "blue") 
    COplot + geom_bar() + labs(x = "Player Country")

![](README_files/figure-gfm/univariate%20bar%20graphs-2.png)<!-- -->

    # bar plot of Team Finish
    COPlot <- ggplot(PL_SK_Season, aes(x = Position), color = "blue") 
    COPlot + geom_bar() + labs(x = "Player Position")

![](README_files/figure-gfm/univariate%20bar%20graphs-3.png)<!-- -->

### 2 Factors

Consistent with univariate analysis we see fewer players on the winning
teams. It’s notable that Canadians dominate both rosters (they invented
the sport). Europeans and Americans are approximately the same. Centers
and Defensemen are clearly the most valuable positions to fill - strong
stats in these groups could show significant differences between First /
Last groups in the Qantitative Analysis.

    # Finish by Nationality
    FxCOplot <- ggplot(PL_SK_Season, aes(Finish, fill = as.factor(Country)))
    FxCOplot+ geom_bar(position = "dodge") +  scale_fill_discrete(name = "Country") + labs(x = "Team Finish")

![](README_files/figure-gfm/2%20factor%20bar%20graphs-1.png)<!-- -->

    # Country by Position
    FxPosplot <- ggplot(PL_SK_Season, aes(Country, fill = as.factor(Position)))
    FxPosplot + geom_bar(position = "dodge") +  scale_fill_discrete(name = "Position") + labs(x = "Country Region")

![](README_files/figure-gfm/2%20factor%20bar%20graphs-2.png)<!-- -->

### 3 Factors

Basically a breakdown of the previous 2 bivariate plots demonstrating
the same conclusions. The number of Canadian defensemen on Last Place
rosters stands out - perhaps a crop of younger players.

    # Color by satellite indicator by spine condition
    FxPMxPtplot <- ggplot(PL_SK_Season, aes(Country, fill = Finish))
    FxPMxPtplot + geom_bar(position = "dodge") + scale_fill_discrete(name = "Team Finish") + labs(x = "Player Country", title = "Player Finish by Country and Position") + facet_wrap(. ~ Position, labeller = (label_both))

![](README_files/figure-gfm/3%20factor%20bar%20graphs-1.png)<!-- -->

Quantitative Analysis
=====================

Summaries
---------

    # Function to knit 5 number sum + Mean given Species input
    TeamSumm <- function(team, ...) {
    summ <- PL_SK_Season %>% filter(Team == team) %>% select(c(8, 9, 10)) %>% apply(2, summary)
    kable(round(summ, 2), caption = paste0("Team: ", team))
    }

    teams <- (c("Capitals", "Avalanche", "Predators", "Sabres", "Lightning", "Senators"))

    # Capitals summary
    TeamSumm(teams[[1]])

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.75 |            9.21 |          6.50 |
| Median  |           4.50 |           17.79 |         18.50 |
| Mean    |           5.21 |           25.53 |         24.96 |
| 3rd Qu. |           7.00 |           35.51 |         35.75 |
| Max.    |          15.00 |          146.71 |         85.00 |

Team: Capitals

    # Avalanche summary
    TeamSumm(teams[[2]])

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.00 |           10.67 |          6.00 |
| Median  |           3.00 |           23.00 |         18.00 |
| Mean    |           3.85 |           27.78 |         19.61 |
| 3rd Qu. |           5.00 |           36.60 |         26.00 |
| Max.    |          10.00 |          135.90 |         71.00 |

Team: Avalanche

    # Predators summary
    TeamSumm(teams[[3]])

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          1.00 |
| 1st Qu. |           3.00 |           15.67 |          5.50 |
| Median  |           5.00 |           25.00 |         19.00 |
| Mean    |           5.04 |           27.65 |         20.93 |
| 3rd Qu. |           7.00 |           31.03 |         33.00 |
| Max.    |           9.00 |           89.43 |         50.00 |

Team: Predators

    # Sabres summary
    TeamSumm(teams[[4]])

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.00 |            4.67 |          3.50 |
| Median  |           3.00 |           10.60 |          8.00 |
| Mean    |           3.54 |           18.71 |         15.23 |
| 3rd Qu. |           5.00 |           27.45 |         19.50 |
| Max.    |          11.00 |           87.00 |         67.00 |

Team: Sabres

    # lightning summary
    TeamSumm(teams[[5]])

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            5.50 |          2.00 |
| 1st Qu. |           2.00 |           18.40 |         11.00 |
| Median  |           5.00 |           21.00 |         22.00 |
| Mean    |           4.88 |           26.24 |         26.88 |
| 3rd Qu. |           7.00 |           37.29 |         39.00 |
| Max.    |          12.00 |           58.50 |         78.00 |

Team: Lightning

    # Senators summary
    TeamSumm(teams[[6]])

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.00 |            3.25 |          2.00 |
| Median  |           2.00 |            9.41 |          8.00 |
| Mean    |           3.24 |           14.77 |         13.19 |
| 3rd Qu. |           4.00 |           19.41 |         19.50 |
| Max.    |          11.00 |           90.50 |         54.00 |

Team: Senators

Visuals
-------

### Average Total Points vs Player Tenure

An apparent strong correlation between these variables especially
towards the upper right indicating veteran players produce more points
(goals + assists) on average over their careers. This could be the
result of their skill leading to longevity vs experience producing more
points (interesting topic for deeper analysis). Wide variance given by
the large CI bands.

    # Base plot aesthetic with Total Points on x axis
    Finish <- PL_SK_Season$Finish
    Avg_Total_Points <- PL_SK_Season$`Avg Total Pts`
    Avg_Penalty_Min <- PL_SK_Season$`Avg Penalty Min`
    PLayer_Seasons <- PL_SK_Season$`Player Seasons`

    g <- ggplot(PL_SK_Season, aes(x = Avg_Total_Points, y = PLayer_Seasons, color = Finish))

    # Avg total points histogram
    g + geom_point() + geom_smooth(aes(group = Team), method = lm) + scale_fill_continuous() + labs(title =  "Players Average Total Points vs Seasons")

![](README_files/figure-gfm/dotplot%20by%20TotalPoints-1.png)<!-- -->

### Penalty Mins by Player Tenure

Mixed results among First & Last Placed teams but generally First Place
teams show fewer PMs by season. Could indicate “maturity” and
recognition of importance of “staying out of the box” to winning over a
long season.

    # Base plot aesthetic with Total Points on x axis
    g <- ggplot(PL_SK_Season, aes(x = Avg_Penalty_Min, y = PLayer_Seasons, color = Finish))

    # Avg PM point plot
    g + geom_point() + geom_smooth(aes(group = Team), method = lm) + scale_fill_continuous() + labs(title =  "Players Average Penalty Minutes vs Average Total Points")

![](README_files/figure-gfm/dotplot%20by%20Penalty%20Minutes-1.png)<!-- -->

### Average Total Points vs Average Penalty Minutes

Breaking out colors by team to show another degree of team detail.
Tamapa Bay jumps out here for the steep Beta 1 - players getting the
most points out of their penalty minutes & shortness of line indicate
fewer penalty minute outliers (consistent blend of aggression &
discipline across roster). Capitals are next highest in Career points
per PM but w less discipline (aggressive play leading to positive
results). The 3 Last Place teams stand out for the shallowness (low
points per penalty mins) of their lines & clustering in the lower left
(fewer points/fewer penalty minutes) - teams appear to be less
aggressive/offensively minded - could be Experience related. The 3 Last
Place teams have man tenures under 4 years while the First Place teams
are over 5 as a group. Capitals have the max tenured player at 15 years
- The Great 8, Alex Ovechkin - you’ll see him at the top of all charts.
He’s pretty good.

    # Base plot aesthetic with Total Points on x axis
    g <- ggplot(PL_SK_Season, aes(x = Avg_Penalty_Min, y = Avg_Total_Points, color = Team))

    # Avg total points histogram
    g + geom_point() + geom_smooth(aes(group = Team), method = lm) + scale_fill_continuous() + labs(title =  "Players Average Total Points vs Average Penalty Minutes")

![](README_files/figure-gfm/dotplot%20by-1.png)<!-- -->
