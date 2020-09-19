NHL
================
Todd Idol
9/8/2020

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
    -   [Franchise Main API](#franchise-main-api)
    -   [Team Totals API](#team-totals-api)
    -   [Team Drill Down API](#team-drill-down-api)
    -   [Goalie API](#goalie-api)
    -   [Skater API](#skater-api)
    -   [2017 - 2019 Presidents Cup Teams vs. Low Points Teams
        Analysis](#presidents-cup-teams-vs.-low-points-teams-analysis)
        -   [Language](#language)
-   [Analysis](#analysis)
    -   [Data](#data)
    -   [Categorical Analysis](#categorical-analysis)
        -   [Total Summaries](#total-summaries)
        -   [Summaries by First Place
            Teams](#summaries-by-first-place-teams)
        -   [Summaries by Last Place
            Teams](#summaries-by-last-place-teams)
    -   [Visuals](#visuals)
        -   [1 Factor](#factor)
        -   [2 Factors](#factors)
        -   [3 Factors](#factors-1)
    -   [Quantitative Analysis](#quantitative-analysis)
        -   [Summaries](#summaries)
    -   [Visuals](#visuals-1)
        -   [Average Total Points vs Player
            Tenure](#average-total-points-vs-player-tenure)
        -   [Penalty Mins by Player
            Tenure](#penalty-mins-by-player-tenure)
        -   [Average Total Points vs Average Penalty
            Minutes](#average-total-points-vs-average-penalty-minutes)

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

    # Franchise Wrapper takes in an API Endpoint (from a list) & Team (either Franchise ID or Common Team name (e.g. "Hurricanes)) & returns distinct API data. 

    FR_Wrapper <- function(endpoint, team = NULL, ...) {
      menu <- FranchiseAPI()
      records <- c("franchise", "totals", "drilldown", "goalie", "skater")
      teamlist <- list(menu[5])
      frIDs <- list(menu[1])
      
      if(!(is.character(endpoint))) stop("Invalid Input")
      
      if(is.character(team)) {
        if ((team %in% teamlist)) stop ("Invalid Input")
      }
     
      if(is.numeric(team)) {
        if((team %in% frIDs)) stop ("Invalid Input")
      }

      
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

    ST_Wrapper <- function(mod, team = NULL, season = 00000000, ...) {
      menu <- FranchiseAPI()
      modifyer <- c("stats", "roster", "person", "nextgame", "priorgame", "expanded", "season")
      teamlist <- list(menu[5])
      teamIDs <- list(menu[4])
      
      if((!is.character(mod) & (mod %in% modifyer))) stop("Invalid Input")
      
      if(is.character(team)) {
          if ((team %in% teamlist)) stop("Invalid Input")
      }
         
      if(is.numeric(team)) {
        if((team %in% teamIDs)) stop("Invalid Input")
      }
      
      if(!length(season) != 8) stop("Invalid Input")
      

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

Franchise Main API
------------------

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

| Franchise ID | First Season | Last Season | Team ID | Name        | Location  |
|-------------:|-------------:|------------:|--------:|:------------|:----------|
|            1 |     19171918 |          NA |       8 | Canadiens   | Montréal  |
|            2 |     19171918 |    19171918 |      41 | Wanderers   | Montreal  |
|            3 |     19171918 |    19341935 |      45 | Eagles      | St. Louis |
|            4 |     19191920 |    19241925 |      37 | Tigers      | Hamilton  |
|            5 |     19171918 |          NA |      10 | Maple Leafs | Toronto   |
|            6 |     19241925 |          NA |       6 | Bruins      | Boston    |

Team Totals API
---------------

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

Team Drill Down API
-------------------

    TeamDDAPI <- function(id, ...) {
    # GET pull for NHL Team Totals
    drill_down <- GET(paste0("https://records.nhl.com/site/api/franchise-season-records?cayenneExp=franchiseId=", id))

    ## As JSON text
    drill_down <- content(drill_down, "text")

    ## As JSON List
    drill_down <- fromJSON(drill_down, flatten = TRUE)
    return(drill_down[[1]])
    }

|  id | fewestGoals | fewestGoalsAgainst | fewestGoalsAgainstSeasons | fewestGoalsSeasons | fewestLosses | fewestLossesSeasons | fewestPoints | fewestPointsSeasons | fewestTies | fewestTiesSeasons | fewestWins | fewestWinsSeasons | franchiseId | franchiseName       | homeLossStreak | homeLossStreakDates       | homePointStreak | homePointStreakDates      | homeWinStreak | homeWinStreakDates        | homeWinlessStreak | homeWinlessStreakDates    | lossStreak | lossStreakDates           | mostGameGoals | mostGameGoalsDates                                                                                                     | mostGoals | mostGoalsAgainst | mostGoalsAgainstSeasons | mostGoalsSeasons | mostLosses | mostLossesSeasons | mostPenaltyMinutes | mostPenaltyMinutesSeasons | mostPoints | mostPointsSeasons | mostShutouts | mostShutoutsSeasons | mostTies | mostTiesSeasons | mostWins | mostWinsSeasons | pointStreak | pointStreakDates          | roadLossStreak | roadLossStreakDates       | roadPointStreak | roadPointStreakDates      | roadWinStreak | roadWinStreakDates        | roadWinlessStreak | roadWinlessStreakDates                               | winStreak | winStreakDates                                                                  | winlessStreak | winlessStreakDates |
|----:|------------:|-------------------:|:--------------------------|:-------------------|-------------:|:--------------------|-------------:|:--------------------|-----------:|:------------------|-----------:|:------------------|------------:|:--------------------|---------------:|:--------------------------|----------------:|:--------------------------|--------------:|:--------------------------|------------------:|:--------------------------|-----------:|:--------------------------|--------------:|:-----------------------------------------------------------------------------------------------------------------------|----------:|-----------------:|:------------------------|:-----------------|-----------:|:------------------|-------------------:|:--------------------------|-----------:|:------------------|-------------:|:--------------------|---------:|:----------------|---------:|:----------------|------------:|:--------------------------|---------------:|:--------------------------|----------------:|:--------------------------|--------------:|:--------------------------|------------------:|:-----------------------------------------------------|----------:|:--------------------------------------------------------------------------------|:--------------|:-------------------|
|  12 |         171 |                202 | 1998-99 (82)              | 2002-03 (82)       |           22 | 2005-06 (82)        |           45 | 1982-83 (80)        |          4 | 1985-86 (80)      |         19 | 1982-83 (80)      |          26 | Carolina Hurricanes |              8 | Mar 14 2013 - Apr 09 2013 |              15 | Dec 13 2005 - Jan 28 2006 |            12 | Feb 20 2009 - Apr 07 2009 |                13 | Jan 15 1985 - Mar 10 1985 |          9 | Feb 19 1983 - Mar 08 1983 |            11 | Feb 12 1984 - EDM 0 @ HFD 11, Oct 19 1985 - MTL 6 @ HFD 11, Jan 17 1986 - QUE 6 @ HFD 11, Mar 15 1986 - CHI 4 @ HFD 11 |       332 |              403 | 1982-83 (80)            | 1985-86 (80)     |         54 | 1982-83 (80)      |               2354 | 1992-93 (84)              |        112 | 2005-06 (82)      |            8 | 1998-99 (82)        |       19 | 1979-80 (80)    |       52 | 2005-06 (82)    |          13 | Mar 09 2017 - Mar 30 2017 |             13 | Dec 18 1982 - Feb 05 1983 |              12 | Feb 23 2004 - Mar 27 2004 |             6 | Nov 10 1990 - Dec 07 1990 |                15 | Nov 11 1979 - Jan 09 1980, Jan 07 2003 - Mar 02 2003 |         9 | Oct 22 2005 - Nov 11 2005, Dec 31 2005 - Jan 19 2006, Mar 18 2009 - Apr 07 2009 | NA            | NA                 |

Goalie API
----------

    GoalieAPI <- function(id, ...) {
    # GET pull for NHL Team Totals
    goalie <- GET(paste0("https://records.nhl.com/site/api/franchise-goalie-records?cayenneExp=franchiseId=", id))

    ## As JSON text
    goalie <- content(goalie, "text")

    ## As JSON List
    goalie <- fromJSON(goalie, flatten = TRUE)
    return(goalie[[1]])
    }

Skater API
----------

    SkaterAPI <- function(id, ...) {
    # GET pull for NHL Team Totals
    skater <- GET(paste0("https://records.nhl.com/site/api/franchise-skater-records?cayenneExp=franchiseId=", id))

    ## As JSON text
    skater <- content(skater, "text")

    ## As JSON List
    skater <- fromJSON(skater, flatten = TRUE)
    return(skater[[1]])
    }

    Franchise <- FranchiseAPI()
    Franchise <- arrange(Franchise, (Franchise[[4]]))
    kable((Franchise), caption = "Franchise All")

| Franchise ID | First Season | Last Season | Team ID | Name           | Location     |
|-------------:|-------------:|------------:|--------:|:---------------|:-------------|
|           23 |     19741975 |          NA |       1 | Devils         | New Jersey   |
|           22 |     19721973 |          NA |       2 | Islanders      | New York     |
|           10 |     19261927 |          NA |       3 | Rangers        | New York     |
|           16 |     19671968 |          NA |       4 | Flyers         | Philadelphia |
|           17 |     19671968 |          NA |       5 | Penguins       | Pittsburgh   |
|            6 |     19241925 |          NA |       6 | Bruins         | Boston       |
|           19 |     19701971 |          NA |       7 | Sabres         | Buffalo      |
|            1 |     19171918 |          NA |       8 | Canadiens      | Montréal     |
|           30 |     19921993 |          NA |       9 | Senators       | Ottawa       |
|            5 |     19171918 |          NA |      10 | Maple Leafs    | Toronto      |
|           26 |     19791980 |          NA |      12 | Hurricanes     | Carolina     |
|           33 |     19931994 |          NA |      13 | Panthers       | Florida      |
|           31 |     19921993 |          NA |      14 | Lightning      | Tampa Bay    |
|           24 |     19741975 |          NA |      15 | Capitals       | Washington   |
|           11 |     19261927 |          NA |      16 | Blackhawks     | Chicago      |
|           12 |     19261927 |          NA |      17 | Red Wings      | Detroit      |
|           34 |     19981999 |          NA |      18 | Predators      | Nashville    |
|           18 |     19671968 |          NA |      19 | Blues          | St. Louis    |
|           21 |     19721973 |          NA |      20 | Flames         | Calgary      |
|           27 |     19791980 |          NA |      21 | Avalanche      | Colorado     |
|           25 |     19791980 |          NA |      22 | Oilers         | Edmonton     |
|           20 |     19701971 |          NA |      23 | Canucks        | Vancouver    |
|           32 |     19931994 |          NA |      24 | Ducks          | Anaheim      |
|           15 |     19671968 |          NA |      25 | Stars          | Dallas       |
|           14 |     19671968 |          NA |      26 | Kings          | Los Angeles  |
|           29 |     19911992 |          NA |      28 | Sharks         | San Jose     |
|           36 |     20002001 |          NA |      29 | Blue Jackets   | Columbus     |
|           37 |     20002001 |          NA |      30 | Wild           | Minnesota    |
|            4 |     19191920 |    19241925 |      37 | Tigers         | Hamilton     |
|            9 |     19251926 |    19301931 |      39 | Quakers        | Philadelphia |
|            2 |     19171918 |    19171918 |      41 | Wanderers      | Montreal     |
|            7 |     19241925 |    19371938 |      43 | Maroons        | Montreal     |
|            3 |     19171918 |    19341935 |      45 | Eagles         | St. Louis    |
|           13 |     19671968 |    19771978 |      49 | Barons         | Cleveland    |
|            8 |     19251926 |    19411942 |      51 | Americans      | Brooklyn     |
|           35 |     19992000 |          NA |      52 | Jets           | Winnipeg     |
|           28 |     19791980 |          NA |      53 | Coyotes        | Arizona      |
|           38 |     20172018 |          NA |      54 | Golden Knights | Vegas        |

Franchise All

    SkaterAPI_Call <- head(SkaterAPI(1))
    glimpse(SkaterAPI_Call)

    ## Rows: 6
    ## Columns: 30
    ## $ id                          <int> 16891, 16911, 16990, 17000, 17025, 17054
    ## $ activePlayer                <lgl> FALSE, FALSE, FALSE, FALSE, FALSE, FALSE
    ## $ assists                     <int> 712, 688, 422, 728, 87, 368
    ## $ firstName                   <chr> "Jean", "Henri", "Maurice", "Guy", "Chris", "Steve"
    ## $ franchiseId                 <int> 1, 1, 1, 1, 1, 1
    ## $ franchiseName               <chr> "Montréal Canadiens", "Montréal Canadiens", "Montréal Canadiens", "Mon...
    ## $ gameTypeId                  <int> 2, 2, 2, 2, 2, 2
    ## $ gamesPlayed                 <int> 1125, 1258, 978, 961, 523, 871
    ## $ goals                       <int> 507, 358, 544, 518, 88, 408
    ## $ lastName                    <chr> "Beliveau", "Richard", "Richard", "Lafleur", "Nilan", "Shutt"
    ## $ mostAssistsGameDates        <chr> "1955-02-19, 1956-12-01, 1962-11-24, 1965-11-20, 1967-12-28", "1963-01...
    ## $ mostAssistsOneGame          <int> 4, 5, 5, 4, 2, 4
    ## $ mostAssistsOneSeason        <int> 58, 52, 36, 80, 16, 45
    ## $ mostAssistsSeasonIds        <chr> "19601961", "19571958", "19541955", "19761977", "19841985, 19861987", ...
    ## $ mostGoalsGameDates          <chr> "1955-11-05, 1959-03-07, 1969-02-11", "1957-10-17, 1959-03-14, 1961-03...
    ## $ mostGoalsOneGame            <int> 4, 3, 5, 4, 2, 4
    ## $ mostGoalsOneSeason          <int> 47, 30, 50, 60, 21, 60
    ## $ mostGoalsSeasonIds          <chr> "19551956", "19591960", "19441945", "19771978", "19841985", "19761977"
    ## $ mostPenaltyMinutesOneSeason <int> 143, 91, 125, 51, 358, 51
    ## $ mostPenaltyMinutesSeasonIds <chr> "19551956", "19601961", "19541955", "19721973", "19841985", "19801981"
    ## $ mostPointsGameDates         <chr> "1959-03-07", "1957-10-17", "1944-12-28", "1975-01-04, 1978-02-28, 197...
    ## $ mostPointsOneGame           <int> 7, 6, 8, 6, 3, 5
    ## $ mostPointsOneSeason         <int> 91, 80, 74, 136, 37, 105
    ## $ mostPointsSeasonIds         <chr> "19581959", "19571958", "19541955", "19761977", "19841985", "19761977"
    ## $ penaltyMinutes              <int> 1033, 932, 1287, 381, 2248, 400
    ## $ playerId                    <int> 8445408, 8448320, 8448321, 8448624, 8449883, 8451354
    ## $ points                      <int> 1219, 1046, 966, 1246, 175, 776
    ## $ positionCode                <chr> "C", "C", "R", "R", "R", "L"
    ## $ rookiePoints                <int> 34, 40, 11, 64, 15, 16
    ## $ seasons                     <int> 20, 20, 18, 14, 10, 13

    TeamStatsAPI <- function() {
    stats <- GET("https://statsapi.web.nhl.com/api/v1/teams")

    ## As JSON text
    stats <- content(stats, "text")

    ## As JSON List
    stats <- fromJSON(stats, flatten = TRUE)
    return(stats[[2]])
    }

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

    PersonAPI <- function(id, ...) {
    person <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "/?expand=person.names"))

    ## As JSON text
    person <- content(person, "text")

    ## As JSON List
    person <- fromJSON(person, flatten = TRUE)
    return(person[[2]])
    }

    # Detailed substitue for PersonAPI
    PeopleAPI <- function(id, ...) {
    people <- GET(paste0("https://statsapi.web.nhl.com/api/v1/people/", id))

    ## As JSON text
    people <- content(people, "text")

    ## As JSON List
    people <- fromJSON(people, flatten = TRUE)
    return(people[[2]])
    }

    ## New DF combining People with Roster
    TeamPlayer <- function (id, ...) {
    playerId <- pull(RosterAPI(id), person.id)
    players <- as.data.frame(PeopleAPI(playerId[1]))
      for (i in 2:length(playerId)) {
        players[i, ] <- (PeopleAPI(playerId[i]))
      }
    players <- players %>% select(currentTeam.id, id, fullName, birthCountry, primaryPosition.name)
    if(length(players$currentTeam.id) > 2) {
      players$currentTeam.id = players$currentTeam.id[[1]]
    }
    return(players) 
    }

    NextGAPI <- function(id, ...) {
    nextG <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.schedule.next"))

    ## As JSON text
    nextG <- content(nextG, "text")

    ## As JSON List
    nextG <- fromJSON(nextG, flatten = TRUE)
    nextG <- nextG[[2]]$nextGameSchedule.dates[[1]]$games[[1]]
    return(nextG)
    }

    PriorGAPI <- function(id, ...) {
    priorG <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.schedule.previous"))

    ## As JSON text
    priorG <- content(priorG, "text")

    ## As JSON List
    priorG <- fromJSON(priorG, flatten = TRUE)
    priorG <- priorG[[2]]$previousGameSchedule.dates
    return(priorG)
    }

    ExpStatsAPI <- function(id, ...) {
    expStats <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?expand=team.stats"))

    ## As JSON text
    expStats <- content(expStats, "text")

    ## As JSON List
    expStats <- fromJSON(expStats, flatten = TRUE)
    expStats <- as.data.frame(expStats[[2]]$teamStats[[1]]$splits)
    return(expStats)
    }

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

    MultiAPI <- function(id, ...) {
    multi <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", "?teamId=", id))

    ## As JSON text
    multi <- content(multi, "text")

    ## As JSON List
    multi <- fromJSON(multi, flatten = TRUE)
    return(multi[[2]])
    }

    PlayoffAPI <- function(id, ...) {
    playoff <- GET(paste0("https://statsapi.web.nhl.com/api/v1/teams/", id, "?stats=statsSingleSeasonPlayoffs"))

    ## As JSON text
    playoff <- content(playoff, "text")

    ## As JSON List
    playoff <- fromJSON(playoff, flatten = TRUE)
    return(playoff[[2]])
    }

2017 - 2019 Presidents Cup Teams vs. Low Points Teams Analysis
--------------------------------------------------------------

### Language

Analysis
========

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

    # Combine results into single DS & add year & rank
    PresLast <- bind_rows(pres17, last17, pres18, last18, pres19, last19)
    PresLast <- mutate(PresLast, year = 
                      ifelse((PresLast$teamName == "Capitals") | (PresLast$teamName == "Avalanche"), 17,
                      ifelse((PresLast$teamName == "Predators") | (PresLast$teamName == "Sabres"), 18, 19)))
    PresLast <- mutate(PresLast, rank = ifelse((PresLast$teamName == "Capitals") | (PresLast$teamName == "Predators") | (PresLast$teamName == "Lightning"), "First", "Last"))
    PresLast <- PresLast %>% select(franchiseId, teamName, year, rank, person.id, person.fullName, jerseyNumber, position.code)

    # Skater for detailed stats

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


    Season_People <- lapply(PL_SK_Season$person.id, PeopleAPI)
    Season_People <- bind_rows(Season_People) %>% select(id, nationality) %>% mutate("person.id" = id)

    PL_SK_Season <- inner_join(PL_SK_Season, Season_People)
    PL_SK_Season <- mutate(PL_SK_Season, country = ifelse((nationality == "USA"), "USA",
                                                   ifelse((nationality == "CAN"), "CAN", "EUR")))

    PL_SK_Season <- PL_SK_Season %>% mutate(AveragePM = round((penaltyMinutes/seasons), 2), TotalPoints = (goals+assists), AverageTP = round((goals+assists)/seasons), 2)

    PL_SK_Season <- PL_SK_Season %>% select(franchiseId, teamName, year, rank, person.fullName, country, position.code, seasons, AveragePM, AverageTP) %>% distinct()


    PL_SK_Season <- PL_SK_Season %>% rename("Franchise ID" = franchiseId, "Team" = teamName, "Year" = year, "Finish" = rank, "Name" = person.fullName, "Country" = country, "Position" = position.code, "Player Seasons" = seasons, "Avg Penalty Min" = AveragePM, "Avg Total Pts" = AverageTP)

    PL_SK_Season$Finish <- as.factor(PL_SK_Season$Finish)


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
--------------------

Categories for Player Countries (regionalized), Positions (by code), &
Team Finish.

### Total Summaries

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

Visuals
-------

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
    FxCOplot+ geom_bar(position = "dodge") +  scale_fill_discrete(name = "Nationality") + labs(x = "Team Finish")

![](README_files/figure-gfm/2%20factor%20bar%20graphs-1.png)<!-- -->

    # Country by Position
    FxPosplot <- ggplot(PL_SK_Season, aes(Country, fill = as.factor(Position)))
    FxPosplot + geom_bar(position = "dodge") +  scale_fill_discrete(name = "Position") + labs(x = "Nationality")

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
---------------------

### Summaries

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

Mixd results among First & Last Placed teams but generally First Place
teams show fewer PMs by season. Could indicate “maturity” and
recognition of importance of “staying out of the box” to winning over a
long season.

    # Base plot aesthetic with Total Points on x axis
    g <- ggplot(PL_SK_Season, aes(x = Avg_Penalty_Min, y = PLayer_Seasons, color = Finish))

    # Avg total points histogram
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
aggressive/offensively minded

    # Base plot aesthetic with Total Points on x axis
    g <- ggplot(PL_SK_Season, aes(x = Avg_Penalty_Min, y = Avg_Total_Points, color = Team))

    # Avg total points histogram
    g + geom_point() + geom_smooth(aes(group = Team), method = lm) + scale_fill_continuous() + labs(title =  "Players Average Total Points vs Average Penalty Minutes")

![](README_files/figure-gfm/dotplot%20by-1.png)<!-- -->

    TeamStatsAPI_Call <- (TeamStatsAPI())
    knitr::kable(TeamStatsAPI_Call)

|  id | name                  | link             | abbreviation | teamName       | locationName | firstYearOfPlay | shortName    | officialSiteUrl                                                                                 | franchiseId | active | venue.name               | venue.link          | venue.city   | venue.id | venue.timeZone.id    | venue.timeZone.offset | venue.timeZone.tz | division.id | division.name | division.nameShort | division.link        | division.abbreviation | conference.id | conference.name | conference.link       | franchise.franchiseId | franchise.teamName | franchise.link        |
|----:|:----------------------|:-----------------|:-------------|:---------------|:-------------|:----------------|:-------------|:------------------------------------------------------------------------------------------------|------------:|:-------|:-------------------------|:--------------------|:-------------|---------:|:---------------------|----------------------:|:------------------|------------:|:--------------|:-------------------|:---------------------|:----------------------|--------------:|:----------------|:----------------------|----------------------:|:-------------------|:----------------------|
|   1 | New Jersey Devils     | /api/v1/teams/1  | NJD          | Devils         | New Jersey   | 1982            | New Jersey   | <a href="http://www.newjerseydevils.com/" class="uri">http://www.newjerseydevils.com/</a>       |          23 | TRUE   | Prudential Center        | /api/v1/venues/null | Newark       |       NA | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    23 | Devils             | /api/v1/franchises/23 |
|   2 | New York Islanders    | /api/v1/teams/2  | NYI          | Islanders      | New York     | 1972            | NY Islanders | <a href="http://www.newyorkislanders.com/" class="uri">http://www.newyorkislanders.com/</a>     |          22 | TRUE   | Barclays Center          | /api/v1/venues/5026 | Brooklyn     |     5026 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    22 | Islanders          | /api/v1/franchises/22 |
|   3 | New York Rangers      | /api/v1/teams/3  | NYR          | Rangers        | New York     | 1926            | NY Rangers   | <a href="http://www.newyorkrangers.com/" class="uri">http://www.newyorkrangers.com/</a>         |          10 | TRUE   | Madison Square Garden    | /api/v1/venues/5054 | New York     |     5054 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    10 | Rangers            | /api/v1/franchises/10 |
|   4 | Philadelphia Flyers   | /api/v1/teams/4  | PHI          | Flyers         | Philadelphia | 1967            | Philadelphia | <a href="http://www.philadelphiaflyers.com/" class="uri">http://www.philadelphiaflyers.com/</a> |          16 | TRUE   | Wells Fargo Center       | /api/v1/venues/5096 | Philadelphia |     5096 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    16 | Flyers             | /api/v1/franchises/16 |
|   5 | Pittsburgh Penguins   | /api/v1/teams/5  | PIT          | Penguins       | Pittsburgh   | 1967            | Pittsburgh   | <a href="http://pittsburghpenguins.com/" class="uri">http://pittsburghpenguins.com/</a>         |          17 | TRUE   | PPG Paints Arena         | /api/v1/venues/5034 | Pittsburgh   |     5034 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    17 | Penguins           | /api/v1/franchises/17 |
|   6 | Boston Bruins         | /api/v1/teams/6  | BOS          | Bruins         | Boston       | 1924            | Boston       | <a href="http://www.bostonbruins.com/" class="uri">http://www.bostonbruins.com/</a>             |           6 | TRUE   | TD Garden                | /api/v1/venues/5085 | Boston       |     5085 | America/New\_York    |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                     6 | Bruins             | /api/v1/franchises/6  |
|   7 | Buffalo Sabres        | /api/v1/teams/7  | BUF          | Sabres         | Buffalo      | 1970            | Buffalo      | <a href="http://www.sabres.com/" class="uri">http://www.sabres.com/</a>                         |          19 | TRUE   | KeyBank Center           | /api/v1/venues/5039 | Buffalo      |     5039 | America/New\_York    |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                    19 | Sabres             | /api/v1/franchises/19 |
|   8 | Montréal Canadiens    | /api/v1/teams/8  | MTL          | Canadiens      | Montréal     | 1909            | Montréal     | <a href="http://www.canadiens.com/" class="uri">http://www.canadiens.com/</a>                   |           1 | TRUE   | Bell Centre              | /api/v1/venues/5028 | Montréal     |     5028 | America/Montreal     |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                     1 | Canadiens          | /api/v1/franchises/1  |
|   9 | Ottawa Senators       | /api/v1/teams/9  | OTT          | Senators       | Ottawa       | 1990            | Ottawa       | <a href="http://www.ottawasenators.com/" class="uri">http://www.ottawasenators.com/</a>         |          30 | TRUE   | Canadian Tire Centre     | /api/v1/venues/5031 | Ottawa       |     5031 | America/New\_York    |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                    30 | Senators           | /api/v1/franchises/30 |
|  10 | Toronto Maple Leafs   | /api/v1/teams/10 | TOR          | Maple Leafs    | Toronto      | 1917            | Toronto      | <a href="http://www.mapleleafs.com/" class="uri">http://www.mapleleafs.com/</a>                 |           5 | TRUE   | Scotiabank Arena         | /api/v1/venues/null | Toronto      |       NA | America/Toronto      |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                     5 | Maple Leafs        | /api/v1/franchises/5  |
|  12 | Carolina Hurricanes   | /api/v1/teams/12 | CAR          | Hurricanes     | Carolina     | 1979            | Carolina     | <a href="http://www.carolinahurricanes.com/" class="uri">http://www.carolinahurricanes.com/</a> |          26 | TRUE   | PNC Arena                | /api/v1/venues/5066 | Raleigh      |     5066 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    26 | Hurricanes         | /api/v1/franchises/26 |
|  13 | Florida Panthers      | /api/v1/teams/13 | FLA          | Panthers       | Florida      | 1993            | Florida      | <a href="http://www.floridapanthers.com/" class="uri">http://www.floridapanthers.com/</a>       |          33 | TRUE   | BB&T Center              | /api/v1/venues/5027 | Sunrise      |     5027 | America/New\_York    |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                    33 | Panthers           | /api/v1/franchises/33 |
|  14 | Tampa Bay Lightning   | /api/v1/teams/14 | TBL          | Lightning      | Tampa Bay    | 1991            | Tampa Bay    | <a href="http://www.tampabaylightning.com/" class="uri">http://www.tampabaylightning.com/</a>   |          31 | TRUE   | AMALIE Arena             | /api/v1/venues/null | Tampa        |       NA | America/New\_York    |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                    31 | Lightning          | /api/v1/franchises/31 |
|  15 | Washington Capitals   | /api/v1/teams/15 | WSH          | Capitals       | Washington   | 1974            | Washington   | <a href="http://www.washingtoncapitals.com/" class="uri">http://www.washingtoncapitals.com/</a> |          24 | TRUE   | Capital One Arena        | /api/v1/venues/5094 | Washington   |     5094 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    24 | Capitals           | /api/v1/franchises/24 |
|  16 | Chicago Blackhawks    | /api/v1/teams/16 | CHI          | Blackhawks     | Chicago      | 1926            | Chicago      | <a href="http://www.chicagoblackhawks.com/" class="uri">http://www.chicagoblackhawks.com/</a>   |          11 | TRUE   | United Center            | /api/v1/venues/5092 | Chicago      |     5092 | America/Chicago      |                    -5 | CDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    11 | Blackhawks         | /api/v1/franchises/11 |
|  17 | Detroit Red Wings     | /api/v1/teams/17 | DET          | Red Wings      | Detroit      | 1926            | Detroit      | <a href="http://www.detroitredwings.com/" class="uri">http://www.detroitredwings.com/</a>       |          12 | TRUE   | Little Caesars Arena     | /api/v1/venues/5145 | Detroit      |     5145 | America/Detroit      |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                    12 | Red Wings          | /api/v1/franchises/12 |
|  18 | Nashville Predators   | /api/v1/teams/18 | NSH          | Predators      | Nashville    | 1997            | Nashville    | <a href="http://www.nashvillepredators.com/" class="uri">http://www.nashvillepredators.com/</a> |          34 | TRUE   | Bridgestone Arena        | /api/v1/venues/5030 | Nashville    |     5030 | America/Chicago      |                    -5 | CDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    34 | Predators          | /api/v1/franchises/34 |
|  19 | St. Louis Blues       | /api/v1/teams/19 | STL          | Blues          | St. Louis    | 1967            | St Louis     | <a href="http://www.stlouisblues.com/" class="uri">http://www.stlouisblues.com/</a>             |          18 | TRUE   | Enterprise Center        | /api/v1/venues/5076 | St. Louis    |     5076 | America/Chicago      |                    -5 | CDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    18 | Blues              | /api/v1/franchises/18 |
|  20 | Calgary Flames        | /api/v1/teams/20 | CGY          | Flames         | Calgary      | 1980            | Calgary      | <a href="http://www.calgaryflames.com/" class="uri">http://www.calgaryflames.com/</a>           |          21 | TRUE   | Scotiabank Saddledome    | /api/v1/venues/5075 | Calgary      |     5075 | America/Denver       |                    -6 | MDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    21 | Flames             | /api/v1/franchises/21 |
|  21 | Colorado Avalanche    | /api/v1/teams/21 | COL          | Avalanche      | Colorado     | 1979            | Colorado     | <a href="http://www.coloradoavalanche.com/" class="uri">http://www.coloradoavalanche.com/</a>   |          27 | TRUE   | Pepsi Center             | /api/v1/venues/5064 | Denver       |     5064 | America/Denver       |                    -6 | MDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    27 | Avalanche          | /api/v1/franchises/27 |
|  22 | Edmonton Oilers       | /api/v1/teams/22 | EDM          | Oilers         | Edmonton     | 1979            | Edmonton     | <a href="http://www.edmontonoilers.com/" class="uri">http://www.edmontonoilers.com/</a>         |          25 | TRUE   | Rogers Place             | /api/v1/venues/5100 | Edmonton     |     5100 | America/Edmonton     |                    -6 | MDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    25 | Oilers             | /api/v1/franchises/25 |
|  23 | Vancouver Canucks     | /api/v1/teams/23 | VAN          | Canucks        | Vancouver    | 1970            | Vancouver    | <a href="http://www.canucks.com/" class="uri">http://www.canucks.com/</a>                       |          20 | TRUE   | Rogers Arena             | /api/v1/venues/5073 | Vancouver    |     5073 | America/Vancouver    |                    -7 | PDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    20 | Canucks            | /api/v1/franchises/20 |
|  24 | Anaheim Ducks         | /api/v1/teams/24 | ANA          | Ducks          | Anaheim      | 1993            | Anaheim      | <a href="http://www.anaheimducks.com/" class="uri">http://www.anaheimducks.com/</a>             |          32 | TRUE   | Honda Center             | /api/v1/venues/5046 | Anaheim      |     5046 | America/Los\_Angeles |                    -7 | PDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    32 | Ducks              | /api/v1/franchises/32 |
|  25 | Dallas Stars          | /api/v1/teams/25 | DAL          | Stars          | Dallas       | 1967            | Dallas       | <a href="http://www.dallasstars.com/" class="uri">http://www.dallasstars.com/</a>               |          15 | TRUE   | American Airlines Center | /api/v1/venues/5019 | Dallas       |     5019 | America/Chicago      |                    -5 | CDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    15 | Stars              | /api/v1/franchises/15 |
|  26 | Los Angeles Kings     | /api/v1/teams/26 | LAK          | Kings          | Los Angeles  | 1967            | Los Angeles  | <a href="http://www.lakings.com/" class="uri">http://www.lakings.com/</a>                       |          14 | TRUE   | STAPLES Center           | /api/v1/venues/5081 | Los Angeles  |     5081 | America/Los\_Angeles |                    -7 | PDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    14 | Kings              | /api/v1/franchises/14 |
|  28 | San Jose Sharks       | /api/v1/teams/28 | SJS          | Sharks         | San Jose     | 1990            | San Jose     | <a href="http://www.sjsharks.com/" class="uri">http://www.sjsharks.com/</a>                     |          29 | TRUE   | SAP Center at San Jose   | /api/v1/venues/null | San Jose     |       NA | America/Los\_Angeles |                    -7 | PDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    29 | Sharks             | /api/v1/franchises/29 |
|  29 | Columbus Blue Jackets | /api/v1/teams/29 | CBJ          | Blue Jackets   | Columbus     | 1997            | Columbus     | <a href="http://www.bluejackets.com/" class="uri">http://www.bluejackets.com/</a>               |          36 | TRUE   | Nationwide Arena         | /api/v1/venues/5059 | Columbus     |     5059 | America/New\_York    |                    -4 | EDT               |          18 | Metropolitan  | Metro              | /api/v1/divisions/18 | M                     |             6 | Eastern         | /api/v1/conferences/6 |                    36 | Blue Jackets       | /api/v1/franchises/36 |
|  30 | Minnesota Wild        | /api/v1/teams/30 | MIN          | Wild           | Minnesota    | 1997            | Minnesota    | <a href="http://www.wild.com/" class="uri">http://www.wild.com/</a>                             |          37 | TRUE   | Xcel Energy Center       | /api/v1/venues/5098 | St. Paul     |     5098 | America/Chicago      |                    -5 | CDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    37 | Wild               | /api/v1/franchises/37 |
|  52 | Winnipeg Jets         | /api/v1/teams/52 | WPG          | Jets           | Winnipeg     | 2011            | Winnipeg     | <a href="http://winnipegjets.com/" class="uri">http://winnipegjets.com/</a>                     |          35 | TRUE   | Bell MTS Place           | /api/v1/venues/5058 | Winnipeg     |     5058 | America/Winnipeg     |                    -5 | CDT               |          16 | Central       | CEN                | /api/v1/divisions/16 | C                     |             5 | Western         | /api/v1/conferences/5 |                    35 | Jets               | /api/v1/franchises/35 |
|  53 | Arizona Coyotes       | /api/v1/teams/53 | ARI          | Coyotes        | Arizona      | 1979            | Arizona      | <a href="http://www.arizonacoyotes.com/" class="uri">http://www.arizonacoyotes.com/</a>         |          28 | TRUE   | Gila River Arena         | /api/v1/venues/5043 | Glendale     |     5043 | America/Phoenix      |                    -7 | MST               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    28 | Coyotes            | /api/v1/franchises/28 |
|  54 | Vegas Golden Knights  | /api/v1/teams/54 | VGK          | Golden Knights | Vegas        | 2016            | Vegas        | <a href="http://www.vegasgoldenknights.com/" class="uri">http://www.vegasgoldenknights.com/</a> |          38 | TRUE   | T-Mobile Arena           | /api/v1/venues/5178 | Las Vegas    |     5178 | America/Los\_Angeles |                    -7 | PDT               |          15 | Pacific       | PAC                | /api/v1/divisions/15 | P                     |             5 | Western         | /api/v1/conferences/5 |                    38 | Golden Knights     | /api/v1/franchises/38 |

    RosterAPI_Call <- head(RosterAPI(10))
    knitr::kable(RosterAPI_Call)

| franchiseId | jerseyNumber | person.id | person.fullName | person.link            | position.code | position.name | position.type | position.abbreviation |
|------------:|:-------------|----------:|:----------------|:-----------------------|:--------------|:--------------|:--------------|:----------------------|
|           5 | 19           |   8469455 | Jason Spezza    | /api/v1/people/8469455 | C             | Center        | Forward       | C                     |
|           5 | 8            |   8474162 | Jake Muzzin     | /api/v1/people/8474162 | D             | Defenseman    | Defenseman    | D                     |
|           5 | 73           |   8475160 | Kyle Clifford   | /api/v1/people/8475160 | L             | Left Wing     | Forward       | LW                    |
|           5 | 91           |   8475166 | John Tavares    | /api/v1/people/8475166 | C             | Center        | Forward       | C                     |
|           5 | 94           |   8475197 | Tyson Barrie    | /api/v1/people/8475197 | D             | Defenseman    | Defenseman    | D                     |
|           5 | 52           |   8475716 | Martin Marincin | /api/v1/people/8475716 | D             | Defenseman    | Defenseman    | D                     |

    PersonAPI_Call <- head(PersonAPI(10))
    knitr::kable(PersonAPI_Call)

|  id | name                | link             | abbreviation | teamName    | locationName | firstYearOfPlay | shortName | officialSiteUrl                                                                 | franchiseId | active | venue.name       | venue.link          | venue.city | venue.timeZone.id | venue.timeZone.offset | venue.timeZone.tz | division.id | division.name | division.nameShort | division.link        | division.abbreviation | conference.id | conference.name | conference.link       | franchise.franchiseId | franchise.teamName | franchise.link       |
|----:|:--------------------|:-----------------|:-------------|:------------|:-------------|:----------------|:----------|:--------------------------------------------------------------------------------|------------:|:-------|:-----------------|:--------------------|:-----------|:------------------|----------------------:|:------------------|------------:|:--------------|:-------------------|:---------------------|:----------------------|--------------:|:----------------|:----------------------|----------------------:|:-------------------|:---------------------|
|  10 | Toronto Maple Leafs | /api/v1/teams/10 | TOR          | Maple Leafs | Toronto      | 1917            | Toronto   | <a href="http://www.mapleleafs.com/" class="uri">http://www.mapleleafs.com/</a> |           5 | TRUE   | Scotiabank Arena | /api/v1/venues/null | Toronto    | America/Toronto   |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                     5 | Maple Leafs        | /api/v1/franchises/5 |

    PeopleAPI_Call <- head(PeopleAPI(8468508))
    knitr::kable(PeopleAPI_Call)

|      id | fullName        | link                   | firstName | lastName | primaryNumber | birthDate  | currentAge | birthCity | birthStateProvince | birthCountry | nationality | height | weight | active | alternateCaptain | captain | rookie | shootsCatches | rosterStatus | currentTeam.id | currentTeam.name    | currentTeam.link | primaryPosition.code | primaryPosition.name | primaryPosition.type | primaryPosition.abbreviation |
|--------:|:----------------|:-----------------------|:----------|:---------|:--------------|:-----------|-----------:|:----------|:-------------------|:-------------|:------------|:-------|-------:|:-------|:-----------------|:--------|:-------|:--------------|:-------------|---------------:|:--------------------|:-----------------|:---------------------|:---------------------|:---------------------|:-----------------------------|
| 8468508 | Justin Williams | /api/v1/people/8468508 | Justin    | Williams | 14            | 1981-10-04 |         38 | Cobourg   | ON                 | CAN          | CAN         | 6’ 1"  |    184 | TRUE   | FALSE            | FALSE   | FALSE  | R             | Y            |             12 | Carolina Hurricanes | /api/v1/teams/12 | R                    | Right Wing           | Forward              | RW                           |

    NextGAPI_Call <- head(NextGAPI(1))
    knitr::kable(NextGAPI_Call)

\|\| \|\| \|\| \|\|

    PriorGAPI_Call <- head(PriorGAPI(12))
    knitr::kable(PriorGAPI_Call)

<table class="kable_wrapper">
<tbody>
<tr>
<td>

| date       | totalItems | totalEvents | totalGames | totalMatches | games                                                                                                                                                                                                                                                                                                                                | events | matches |
|:-----------|-----------:|------------:|-----------:|-------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------|:--------|
| 2020-08-19 |          1 |           0 |          1 |            0 | 2019030145 , /api/v1/game/2019030145/feed/live, P , 20192020 , 2020-08-19T20:00:00Z , Final , 7 , Final , 7 , FALSE , 1 , 4 , 4 , 0 , league , 12 , Carolina Hurricanes , /api/v1/teams/12 , 2 , 4 , 4 , 0 , league , 6 , Boston Bruins , /api/v1/teams/6 , Scotiabank Arena , /api/v1/venues/null , /api/v1/game/2019030145/content | NULL   | NULL    |

</td>
</tr>
</tbody>
</table>

    SeasonAPI_Call <- head(SeasonAPI(12, 20052006))
    knitr::kable(SeasonAPI_Call)

| franchiseId | jerseyNumber | person.id | person.fullName | person.link            | position.code | position.name | position.type | position.abbreviation | teamName   |
|------------:|:-------------|----------:|:----------------|:-----------------------|:--------------|:--------------|:--------------|:----------------------|:-----------|
|          26 | 17           |   8445735 | Rod Brind’Amour | /api/v1/people/8445735 | C             | Center        | Forward       | C                     | Hurricanes |
|          26 | 28           |   8450725 | Mark Recchi     | /api/v1/people/8450725 | R             | Right Wing    | Forward       | RW                    | Hurricanes |
|          26 | 2            |   8452371 | Glen Wesley     | /api/v1/people/8452371 | D             | Defenseman    | Defenseman    | D                     | Hurricanes |
|          26 | 3            |   8456547 | Bret Hedican    | /api/v1/people/8456547 | D             | Defenseman    | Defenseman    | D                     | Hurricanes |
|          26 | 93           |   8458361 | Doug Weight     | /api/v1/people/8458361 | C             | Center        | Forward       | C                     | Hurricanes |
|          26 | 4            |   8458519 | Aaron Ward      | /api/v1/people/8458519 | D             | Defenseman    | Defenseman    | D                     | Hurricanes |
