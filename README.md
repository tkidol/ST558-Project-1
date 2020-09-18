NHL
================
Todd Idol
9/8/2020

-   [NHL API Wrapper](#nhl-api-wrapper)
-   [NHL Franchises](#nhl-franchises)
    -   [2017 - 2019 Presidents Cup Teams vs. Low Points Teams
        Analysis](#presidents-cup-teams-vs.-low-points-teams-analysis)
        -   [Language](#language)
        -   [Data](#data)
    -   [Visuals](#visuals)
        -   [1 Factor](#factor)
        -   [2 Factors](#factors)
        -   [3 Factors](#factors-1)

NHL API Wrapper
===============

NHL Franchises
==============

    ##          Name
    ## 1   Canadiens
    ## 2   Wanderers
    ## 3      Eagles
    ## 4      Tigers
    ## 5 Maple Leafs
    ## 6      Bruins

    ##   id fewestGoals fewestGoalsAgainst fewestGoalsAgainstSeasons fewestGoalsSeasons fewestLosses
    ## 1 25         189                167              1997-98 (82)       1968-69 (76)           17
    ##   fewestLossesSeasons fewestPoints fewestPointsSeasons fewestTies fewestTiesSeasons fewestWins
    ## 1        2002-03 (82)           45        1977-78 (80)          4      1989-90 (80)         18
    ##            fewestWinsSeasons franchiseId franchiseName homeLossStreak
    ## 1 1968-69 (76), 1977-78 (80)          15  Dallas Stars              6
    ##                                    homeLossStreakDates homePointStreak      homePointStreakDates homeWinStreak
    ## 1 Jan 17 1970 - Feb 04 1970, Feb 21 2009 - Mar 08 2009              17 Jan 23 2004 - Mar 20 2004            11
    ##          homeWinStreakDates homeWinlessStreak    homeWinlessStreakDates lossStreak           lossStreakDates
    ## 1 Nov 04 1972 - Dec 27 1972                12 Jan 17 1970 - Feb 25 1970         10 Feb 01 1976 - Feb 20 1976
    ##   mostGameGoals           mostGameGoalsDates mostGoals mostGoalsAgainst mostGoalsAgainstSeasons
    ## 1            15 Nov 11 1981 - WIN 2 @ MNS 15       346              349            1987-88 (80)
    ##   mostGoalsSeasons mostLosses          mostLossesSeasons mostPenaltyMinutes mostPenaltyMinutesSeasons
    ## 1     1981-82 (80)         53 1975-76 (80), 1977-78 (80)               2317              1987-88 (80)
    ##   mostPoints mostPointsSeasons mostShutouts        mostShutoutsSeasons mostTies mostTiesSeasons mostWins
    ## 1        114      1998-99 (82)           11 2000-01 (82), 2002-03 (82)       22    1969-70 (76)       53
    ##   mostWinsSeasons pointStreak          pointStreakDates roadLossStreak
    ## 1    2005-06 (82)          15 Dec 06 1998 - Jan 06 1999              8
    ##                                                               roadLossStreakDates roadPointStreak
    ## 1 Oct 19 1975 - Nov 13 1975, Jan 28 1988 - Mar 03 1988, Feb 27 1993 - Apr 01 1993              11
    ##        roadPointStreakDates roadWinStreak        roadWinStreakDates roadWinlessStreak
    ## 1 Dec 27 2002 - Feb 27 2003             8 Dec 13 2010 - Jan 20 2011                23
    ##      roadWinlessStreakDates winStreak
    ## 1 Oct 25 1974 - Jan 28 1975         7
    ##                                                                                                                          winStreakDates
    ## 1 Mar 16 1980 - Mar 28 1980, Mar 16 1997 - Apr 02 1997, Nov 22 1997 - Dec 05 1997, Jan 29 2008 - Feb 11 2008, Nov 13 2019 - Nov 25 2019
    ##   winlessStreak        winlessStreakDates
    ## 1             6 Feb 27 2020 - Mar 10 2020

    ##      id activePlayer firstName franchiseId      franchiseName gameTypeId gamesPlayed   lastName losses
    ## 1   261        FALSE   Patrick           1 Montréal Canadiens          2         551        Roy    175
    ## 2   294         TRUE     Carey           1 Montréal Canadiens          2         682      Price    250
    ## 3   296        FALSE   Jacques           1 Montréal Canadiens          2         556     Plante    133
    ## 4   327        FALSE    George           1 Montréal Canadiens          2         318 Hainsworth     96
    ## 5   414        FALSE  Stephane           1 Montréal Canadiens          2           2      Fiset      1
    ## 6   437        FALSE      Jeff           1 Montréal Canadiens          2         161    Hackett     68
    ## 7   450        FALSE     Brian           1 Montréal Canadiens          2         141    Hayward     48
    ## 8   457        FALSE     Denis           1 Montréal Canadiens          2          86     Herron     18
    ## 9   469        FALSE       Pat           1 Montréal Canadiens          2          40  Jablonski     15
    ## 10  511        FALSE    Roland           1 Montréal Canadiens          2           9   Melanson      3
    ## 11  527        FALSE      Andy           1 Montréal Canadiens          2          42       Moog     17
    ## 12  549        FALSE     Lorne           1 Montréal Canadiens          2          47     Chabot     20
    ## 13  559        FALSE     Abbie           1 Montréal Canadiens          2           1        Cox      0
    ## 14  565        FALSE      Wilf           1 Montréal Canadiens          2         220       Cude    101
    ## 15  569        FALSE     Denis           1 Montréal Canadiens          2           7    DeJordy      2
    ## 16  585        FALSE      Bert           1 Montréal Canadiens          2          52   Gardiner     31
    ## 17  612        FALSE      Mike           1 Montréal Canadiens          2           5    Karakas      4
    ## 18  623        FALSE     Gerry           1 Montréal Canadiens          2         276     McNeil    105
    ## 19  654        FALSE      Gump           1 Montréal Canadiens          2         172    Worsley     41
    ## 20  656        FALSE       Roy           1 Montréal Canadiens          2           1    Worters      0
    ## 21  681        FALSE   Vincent           1 Montréal Canadiens          2           1   Riendeau      0
    ## 22  710        FALSE      Doug           1 Montréal Canadiens          2          51   Soetaert     16
    ## 23  724        FALSE       Ron           1 Montréal Canadiens          2          15    Tugnutt      6
    ## 24  863        FALSE   Jocelyn           1 Montréal Canadiens          2         158   Thibault     56
    ## 25  880        FALSE      Eric           1 Montréal Canadiens          2           2    Fichaud      2
    ## 26  924        FALSE      Marc           1 Montréal Canadiens          2           1      Denis      0
    ## 27  954        FALSE     David           1 Montréal Canadiens          2          39  Aebischer     15
    ## 28  975        FALSE      Alex           1 Montréal Canadiens          2          16       Auld      2
    ## 29 1017        FALSE     Peter           1 Montréal Canadiens          2          54      Budaj     16
    ## 30 1028        FALSE Cristobal           1 Montréal Canadiens          2         117       Huet     39
    ## 31 1068        FALSE        Al           1 Montréal Canadiens          2          23    Montoya      7
    ## 32 1124        FALSE     Antti           1 Montréal Canadiens          2          36      Niemi     11
    ## 33 1160        FALSE       Ben           1 Montréal Canadiens          2          15   Scrivens      8
    ## 34 1182        FALSE       Ken           1 Montréal Canadiens          2         397     Dryden     57
    ##                             mostGoalsAgainstDates mostGoalsAgainstOneGame                     mostSavesDates
    ## 1                                      1995-12-02                       9                         1991-03-06
    ## 2                          2019-03-08, 2011-02-09                       8                         2009-11-14
    ## 3              1960-10-25, 1960-01-03, 1959-10-11                       8                         1955-11-13
    ## 4                                      1933-02-21                      10                               <NA>
    ## 5                                      2002-04-12                       5                         2002-04-12
    ## 6  2001-12-29, 2000-04-02, 2000-01-04, 1999-03-06                       6                         2000-12-16
    ## 7              1990-03-24, 1988-11-13, 1987-01-22                       7 1990-03-01, 1988-12-08, 1988-02-29
    ## 8                                      1980-01-26                       7                         1981-12-09
    ## 9                          1996-02-23, 1995-12-07                       6                         1996-10-16
    ## 10                                     1991-11-21                       5                         1991-12-05
    ## 11                         1998-03-26, 1997-10-11                       5                         1998-01-25
    ## 12                                     1933-12-05                       5                               <NA>
    ## 13                                     1936-02-16                       1                               <NA>
    ## 14                                     1938-01-11                      11                               <NA>
    ## 15                         1972-04-02, 1972-01-09                       5                         1972-04-02
    ## 16                                     1941-12-04                       9                               <NA>
    ## 17                                     1940-02-25                       6                               <NA>
    ## 18             1956-11-18, 1954-01-24, 1950-12-28                       8                         1956-11-08
    ## 19                                     1965-03-07                       7                         1969-01-26
    ## 20                                     1930-02-27                       2                               <NA>
    ## 21                                     1987-12-28                       5                         1987-12-28
    ## 22                                     1985-12-05                       7             1986-02-10, 1986-01-20
    ## 23                         1995-03-16, 1994-04-13                       6             1995-03-16, 1995-02-16
    ## 24                                     1996-01-06                       7                         1996-02-03
    ## 25                                     2000-11-18                       3                         2000-11-17
    ## 26                                     2009-01-02                       1                         2009-01-02
    ## 27                                     2007-03-02                       7                         2006-10-28
    ## 28                                     2011-01-17                       4                         2010-11-26
    ## 29             2014-03-06, 2014-02-27, 2013-01-30                       5                         2014-04-04
    ## 30                         2007-04-07, 2007-01-13                       6 2007-11-21, 2007-01-18, 2006-11-30
    ## 31                                     2016-11-04                      10                         2017-01-04
    ## 32                                     2018-12-11                       7                         2019-01-15
    ## 33                                     2016-03-19                       5                         2016-03-16
    ## 34                         1974-11-13, 1972-01-22                       8                         1971-03-21
    ##    mostSavesOneGame  mostShotsAgainstDates mostShotsAgainstOneGame mostShutoutsOneSeason
    ## 1                49             1995-02-27                      53                     7
    ## 2                53             2009-11-14                      55                     9
    ## 3                52             1955-11-13                      52                     9
    ## 4                NA                   <NA>                      NA                    22
    ## 5                36             2002-04-12                      41                     0
    ## 6                49             2000-12-16                      53                     5
    ## 7                39             1990-03-01                      44                     2
    ## 8                39             1981-12-09                      45                     3
    ## 9                42             1996-10-16                      44                     0
    ## 10               28             1991-12-05                      32                     2
    ## 11               38             1998-01-25                      40                     3
    ## 12               NA                   <NA>                      NA                     8
    ## 13               NA                   <NA>                      NA                     0
    ## 14               NA                   <NA>                      NA                     6
    ## 15               41             1972-04-02                      46                     0
    ## 16               NA                   <NA>                      NA                     1
    ## 17               NA                   <NA>                      NA                     0
    ## 18               33             1956-11-18                      37                    10
    ## 19               42             1969-01-26                      45                     6
    ## 20               NA                   <NA>                      NA                     0
    ## 21               17             1987-12-28                      22                     0
    ## 22               35             1986-02-10                      39                     3
    ## 23               32             1995-03-16                      38                     0
    ## 24               49 1997-02-01, 1996-02-03                      50                     3
    ## 25               18             2000-11-17                      19                     0
    ## 26                6             2009-01-02                       7                     0
    ## 27               47             2006-10-28                      51                     0
    ## 28               44             2010-11-26                      47                     0
    ## 29               39             2014-04-04                      43                     1
    ## 30               44             2006-11-30                      48                     7
    ## 31               39 2017-10-18, 2017-01-04                      42                     2
    ## 32               52             2019-01-15                      53                     1
    ## 33               41             2016-03-19                      44                     0
    ## 34               47             1971-03-21                      49                    10
    ##           mostShutoutsSeasonIds mostWinsOneSeason  mostWinsSeasonIds overtimeLosses playerId positionCode
    ## 1                      19931994                36           19911992             NA  8451033            G
    ## 2                      20142015                44           20142015             74  8471679            G
    ## 3  19561957, 19571958, 19581959                42 19551956, 19611962             NA  8450066            G
    ## 4                      19281929                28           19261927             NA  8449987            G
    ## 5                      20012002                 0           20012002             NA  8446831            G
    ## 6                      19981999                24           19981999             NA  8447449            G
    ## 7                      19871988                22           19871988             NA  8447701            G
    ## 8                      19811982                25           19791980             NA  8447755            G
    ## 9            19951996, 19961997                 5           19951996             NA  8448207            G
    ## 10                     19911992                 5           19911992             NA  8449547            G
    ## 11                     19971998                18           19971998             NA  8449681            G
    ## 12                     19331934                21           19331934             NA  8449850            G
    ## 13                     19351936                 0           19351936             NA  8449858            G
    ## 14                     19351936                22           19361937             NA  8449861            G
    ## 15                     19711972                 3           19711972             NA  8449866            G
    ## 16                     19401941                13           19401941             NA  8449960            G
    ## 17                     19391940                 0           19391940             NA  8450007            G
    ## 18                     19521953                34           19511952             NA  8450041            G
    ## 19                     19671968                28           19651966             NA  8450152            G
    ## 20                     19291930                 1           19291930             NA  8450153            G
    ## 21                     19871988                 0           19871988             NA  8450834            G
    ## 22                     19851986                14           19841985             NA  8451595            G
    ## 23           19931994, 19941995                 2           19931994             NA  8451837            G
    ## 24                     19951996                23           19951996             NA  8459432            G
    ## 25           20002001, 20022003                 0 20002001, 20022003             NA  8460506            G
    ## 26                     20082009                 0           20082009              0  8462055            G
    ## 27           20052006, 20062007                13           20062007              3  8466290            G
    ## 28                     20102011                 6           20102011              2  8467913            G
    ## 29           20122013, 20132014                10           20132014              9  8469514            G
    ## 30                     20052006                21           20072008             13  8469658            G
    ## 31                     20162017                 8           20162017              4  8471219            G
    ## 32                     20172018                 8           20182019              6  8474550            G
    ## 33                     20152016                 5           20152016              0  8475681            G
    ## 34                     19761977                42           19751976             NA  8446490            G
    ##    rookieGamesPlayed rookieShutouts rookieWins seasons shutouts ties wins
    ## 1                 47              1         23      12       29   66  289
    ## 2                 41              3         24      13       48    0  348
    ## 3                 52              5         33      11       58  107  314
    ## 4                 44             14         28       8       75   54  167
    ## 5                 NA             NA         NA       1        0    0    0
    ## 6                 NA             NA         NA       5        8   22   63
    ## 7                 NA             NA         NA       4        5   17   71
    ## 8                 NA             NA         NA       3        4   17   43
    ## 9                 NA             NA         NA       2        0    8    9
    ## 10                NA             NA         NA       1        2    0    5
    ## 11                NA             NA         NA       1        3    5   18
    ## 12                NA             NA         NA       1        8    6   21
    ## 13                NA             NA         NA       1        0    1    0
    ## 14                NA             NA         NA       8       18   39   80
    ## 15                NA             NA         NA       1        0    1    3
    ## 16                NA             NA         NA       2        1    7   14
    ## 17                NA             NA         NA       1        0    1    0
    ## 18                70              6         25       7       28   52  119
    ## 19                NA             NA         NA       7       16   24   90
    ## 20                NA             NA         NA       1        0    0    1
    ## 21                NA             NA         NA       1        0    0    0
    ## 22                NA             NA         NA       2        3    6   25
    ## 23                NA             NA         NA       2        0    2    3
    ## 24                NA             NA         NA       4        7   24   67
    ## 25                NA             NA         NA       2        0    0    0
    ## 26                NA             NA         NA       1        0   NA    0
    ## 27                NA             NA         NA       2        0   NA   17
    ## 28                NA             NA         NA       1        0   NA    6
    ## 29                NA             NA         NA       3        2   NA   23
    ## 30                NA             NA         NA       3       11   NA   58
    ## 31                NA             NA         NA       2        2    0   10
    ## 32                NA             NA         NA       2        1    0   15
    ## 33                NA             NA         NA       1        0   NA    5
    ## 34                64              8         39       8       46   74  258
    ##  [ reached 'max' / getOption("max.print") -- omitted 3 rows ]

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

2017 - 2019 Presidents Cup Teams vs. Low Points Teams Analysis
--------------------------------------------------------------

### Language

### Data

| Franchise ID | Team      | Year | Finish | Name                | Country | Position | Player Seasons | Avg Penalty Min | Avg Total Pts |
|-------------:|:----------|-----:|:-------|:--------------------|:--------|:---------|---------------:|----------------:|--------------:|
|           24 | Capitals  |   17 | First  | Brooks Orpik        | USA     | D        |              5 |           47.60 |            12 |
|           24 | Capitals  |   17 | First  | Justin Williams     | CAN     | R        |              2 |           43.00 |            50 |
|           24 | Capitals  |   17 | First  | Alex Ovechkin       | EUR     | L        |             15 |           47.93 |            85 |
|           24 | Capitals  |   17 | First  | Daniel Winnik       | CAN     | L        |              2 |           35.50 |            15 |
|           24 | Capitals  |   17 | First  | T.J. Oshie          | USA     | R        |              5 |           32.60 |            51 |
|           24 | Capitals  |   17 | First  | Matt Niskanen       | USA     | D        |              5 |           38.80 |            31 |
|           24 | Capitals  |   17 | First  | Taylor Chorney      | CAN     | D        |              3 |           13.33 |             5 |
|           24 | Capitals  |   17 | First  | Nicklas Backstrom   | EUR     | C        |             13 |           35.54 |            71 |
|           24 | Capitals  |   17 | First  | Karl Alzner         | CAN     | D        |              9 |           19.67 |            13 |
|           24 | Capitals  |   17 | First  | Paul Carey          | USA     | C        |              2 |            0.00 |             0 |
|           24 | Capitals  |   17 | First  | Kevin Shattenkirk   | USA     | D        |              1 |           10.00 |            14 |
|           24 | Capitals  |   17 | First  | Lars Eller          | EUR     | C        |              4 |           39.75 |            34 |
|           24 | Capitals  |   17 | First  | Jay Beagle          | CAN     | C        |             10 |           15.90 |            12 |
|           24 | Capitals  |   17 | First  | John Carlson        | USA     | D        |             11 |           23.45 |            43 |
|           24 | Capitals  |   17 | First  | Aaron Ness          | USA     | D        |              3 |            3.33 |             1 |
|           24 | Capitals  |   17 | First  | Marcus Johansson    | EUR     | C        |              7 |            8.86 |            41 |
|           24 | Capitals  |   17 | First  | Dmitry Orlov        | EUR     | D        |              8 |           25.62 |            22 |
|           24 | Capitals  |   17 | First  | Garrett Mitchell    | CAN     | R        |              1 |            0.00 |             0 |
|           24 | Capitals  |   17 | First  | Evgeny Kuznetsov    | EUR     | C        |              7 |           35.14 |            56 |
|           24 | Capitals  |   17 | First  | Brett Connolly      | CAN     | R        |              3 |           31.33 |            32 |
|           24 | Capitals  |   17 | First  | Tom Wilson          | CAN     | R        |              7 |          146.71 |            27 |
|           24 | Capitals  |   17 | First  | Chandler Stephenson | CAN     | C        |              5 |            3.20 |             7 |
|           24 | Capitals  |   17 | First  | Riley Barber        | USA     | R        |              1 |            0.00 |             0 |
|           24 | Capitals  |   17 | First  | Liam O’Brien        | CAN     | C        |              3 |            9.33 |             1 |
|           24 | Capitals  |   17 | First  | Nate Schmidt        | USA     | D        |              4 |           12.00 |            11 |
|           24 | Capitals  |   17 | First  | Andre Burakovsky    | EUR     | L        |              5 |           15.40 |            29 |
|           24 | Capitals  |   17 | First  | Zach Sanford        | USA     | L        |              1 |            6.00 |             3 |
|           24 | Capitals  |   17 | First  | Jakub Vrana         | EUR     | L        |              4 |           14.75 |            33 |
|           27 | Avalanche |   17 | Last   | Jarome Iginla       | CAN     | R        |              3 |           45.67 |            41 |
|           27 | Avalanche |   17 | Last   | Francois Beauchemin | CAN     | D        |              2 |           35.00 |            26 |
|           27 | Avalanche |   17 | Last   | Fedor Tyutin        | EUR     | D        |              1 |           38.00 |            13 |
|           27 | Avalanche |   17 | Last   | John Mitchell       | CAN     | C        |              5 |           36.60 |            21 |
|           27 | Avalanche |   17 | Last   | Blake Comeau        | CAN     | L        |              3 |           55.33 |            30 |
|           27 | Avalanche |   17 | Last   | Carl Soderberg      | EUR     | C        |              4 |           26.50 |            38 |
|           27 | Avalanche |   17 | Last   | Rene Bourque        | CAN     | R        |              1 |           56.00 |            18 |
|           27 | Avalanche |   17 | Last   | Cody McLeod         | CAN     | L        |             10 |          135.90 |            12 |
|           27 | Avalanche |   17 | Last   | Erik Johnson        | USA     | D        |             10 |           33.20 |            21 |
|           27 | Avalanche |   17 | Last   | Joe Colborne        | CAN     | C        |              1 |           34.00 |             8 |
|           27 | Avalanche |   17 | Last   | Cody Goloubef       | CAN     | D        |              1 |           25.00 |             5 |
|           27 | Avalanche |   17 | Last   | Patrick Wiercioch   | CAN     | D        |              1 |           23.00 |            12 |
|           27 | Avalanche |   17 | Last   | Mark Barberio       | CAN     | D        |              4 |           13.75 |             6 |
|           27 | Avalanche |   17 | Last   | Ben Smith           | USA     | R        |              1 |            0.00 |             0 |
|           27 | Avalanche |   17 | Last   | Matt Duchene        | CAN     | C        |              9 |           16.00 |            48 |
|           27 | Avalanche |   17 | Last   | Tyson Barrie        | CAN     | D        |              8 |           20.38 |            38 |
|           27 | Avalanche |   17 | Last   | Eric Gelinas        | CAN     | D        |              2 |            6.00 |             0 |
|           27 | Avalanche |   17 | Last   | Gabriel Bourque     | CAN     | L        |              3 |            7.33 |             6 |
|           27 | Avalanche |   17 | Last   | Rocco Grimaldi      | USA     | R        |              2 |            1.00 |             2 |
|           27 | Avalanche |   17 | Last   | Matt Nieto          | USA     | L        |              4 |            8.00 |            20 |
|           27 | Avalanche |   17 | Last   | Gabriel Landeskog   | EUR     | L        |              9 |           54.33 |            51 |
|           27 | Avalanche |   17 | Last   | Duncan Siemens      | CAN     | D        |              3 |            8.33 |             1 |
|           27 | Avalanche |   17 | Last   | Samuel Henley       | CAN     | C        |              1 |            2.00 |             1 |
|           27 | Avalanche |   17 | Last   | Mikhail Grigorenko  | EUR     | C        |              2 |           13.00 |            25 |
|           27 | Avalanche |   17 | Last   | Sven Andrighetto    | EUR     | R        |              3 |           10.67 |            18 |
|           27 | Avalanche |   17 | Last   | J.T. Compher        | USA     | L        |              4 |           18.25 |            23 |
|           27 | Avalanche |   17 | Last   | Nathan MacKinnon    | CAN     | C        |              7 |           28.14 |            71 |
|           27 | Avalanche |   17 | Last   | Nikita Zadorov      | EUR     | D        |              5 |           65.60 |            12 |
|           27 | Avalanche |   17 | Last   | Anton Lindholm      | EUR     | D        |              4 |            4.00 |             1 |
|           27 | Avalanche |   17 | Last   | Mikko Rantanen      | EUR     | R        |              5 |           25.20 |            50 |
|           27 | Avalanche |   17 | Last   | A.J. Greer          | CAN     | L        |              3 |           15.67 |             2 |
|           27 | Avalanche |   17 | Last   | Andreas Martinsen   | EUR     | L        |              2 |           39.50 |             9 |
|           27 | Avalanche |   17 | Last   | Tyson Jost          | CAN     | C        |              4 |           15.50 |            18 |
|           34 | Predators |   18 | First  | Mike Fisher         | CAN     | C        |              8 |           32.62 |            30 |
|           34 | Predators |   18 | First  | Scott Hartnell      | CAN     | L        |              7 |           89.43 |            34 |
|           34 | Predators |   18 | First  | Alexei Emelin       | EUR     | D        |              1 |           40.00 |             9 |
|           34 | Predators |   18 | First  | Cody McLeod         | CAN     | L        |              3 |           57.33 |             2 |
|           34 | Predators |   18 | First  | Nick Bonino         | USA     | C        |              3 |           18.00 |            32 |
|           34 | Predators |   18 | First  | P.K. Subban         | CAN     | D        |              3 |           62.00 |            43 |
|           34 | Predators |   18 | First  | Kyle Turris         | CAN     | C        |              3 |           26.33 |            32 |
|           34 | Predators |   18 | First  | Yannick Weber       | EUR     | D        |              4 |           18.25 |             6 |
|           34 | Predators |   18 | First  | Roman Josi          | EUR     | D        |              9 |           26.00 |            46 |
|           34 | Predators |   18 | First  | Ryan Ellis          | CAN     | D        |              9 |           19.89 |            28 |
|           34 | Predators |   18 | First  | Mattias Ekholm      | EUR     | D        |              9 |           29.44 |            22 |
|           34 | Predators |   18 | First  | Craig Smith         | USA     | R        |              9 |           29.33 |            37 |
|           34 | Predators |   18 | First  | Matt Irwin          | CAN     | D        |              4 |           20.75 |             8 |
|           34 | Predators |   18 | First  | Calle Jarnkrok      | EUR     | C        |              7 |           14.14 |            26 |
|           34 | Predators |   18 | First  | Austin Watson       | USA     | L        |              6 |           59.67 |            13 |
|           34 | Predators |   18 | First  | Ryan Johansen       | CAN     | C        |              5 |           52.20 |            50 |
|           34 | Predators |   18 | First  | Anthony Bitetto     | USA     | D        |              5 |           17.20 |             4 |
|           34 | Predators |   18 | First  | Miikka Salomaki     | EUR     | R        |              6 |           12.67 |             4 |
|           34 | Predators |   18 | First  | Pontus Aberg        | EUR     | L        |              2 |            6.00 |             5 |
|           34 | Predators |   18 | First  | Filip Forsberg      | EUR     | L        |              8 |           25.00 |            44 |
|           34 | Predators |   18 | First  | Colton Sissons      | CAN     | C        |              6 |           18.83 |            15 |
|           34 | Predators |   18 | First  | Ryan Hartman        | USA     | R        |              2 |           29.00 |            13 |
|           34 | Predators |   18 | First  | Frederick Gaudreau  | CAN     | C        |              3 |            1.33 |             3 |
|           34 | Predators |   18 | First  | Kevin Fiala         | EUR     | L        |              5 |           14.00 |            19 |
|           34 | Predators |   18 | First  | Viktor Arvidsson    | EUR     | R        |              6 |           25.17 |            36 |
|           34 | Predators |   18 | First  | Samuel Girard       | CAN     | D        |              1 |            2.00 |             3 |
|           34 | Predators |   18 | First  | Eeli Tolvanen       | EUR     | R        |              2 |            0.00 |             1 |
|           19 | Sabres    |   18 | Last   | Jason Pominville    | CAN     | R        |             11 |           14.45 |            47 |
|           19 | Sabres    |   18 | Last   | Josh Gorges         | CAN     | D        |              4 |           38.75 |             6 |
|           19 | Sabres    |   18 | Last   | Matt Moulson        | CAN     | L        |              5 |           10.40 |            25 |
|           19 | Sabres    |   18 | Last   | Benoit Pouliot      | CAN     | L        |              1 |           22.00 |            19 |
|           19 | Sabres    |   18 | Last   | Kyle Okposo         | USA     | R        |              4 |           33.25 |            34 |
|           19 | Sabres    |   18 | Last   | Justin Falk         | CAN     | D        |              2 |           28.50 |             5 |
|           19 | Sabres    |   18 | Last   | Zach Bogosian       | USA     | D        |              6 |           39.00 |            11 |
|           19 | Sabres    |   18 | Last   | Marco Scandella     | CAN     | D        |              3 |           23.67 |            15 |
|           19 | Sabres    |   18 | Last   | Zach Redmond        | USA     | D        |              1 |            2.00 |             0 |
|           19 | Sabres    |   18 | Last   | Ryan O’Reilly       | CAN     | C        |              3 |            6.67 |            59 |
|           19 | Sabres    |   18 | Last   | Evander Kane        | CAN     | L        |              3 |           87.00 |            39 |
|           19 | Sabres    |   18 | Last   | Jacob Josefson      | EUR     | C        |              1 |            6.00 |             4 |
|           19 | Sabres    |   18 | Last   | Jordan Nolan        | CAN     | C        |              1 |           69.00 |             8 |
|           19 | Sabres    |   18 | Last   | Johan Larsson       | EUR     | C        |              7 |           27.14 |            14 |
|           19 | Sabres    |   18 | Last   | Taylor Fedun        | CAN     | D        |              2 |            9.00 |             4 |
|           19 | Sabres    |   18 | Last   | Scott Wilson        | CAN     | L        |              3 |            4.67 |             6 |
|           19 | Sabres    |   18 | Last   | Nathan Beaulieu     | CAN     | D        |              2 |           34.00 |             8 |
|           19 | Sabres    |   18 | Last   | Seth Griffith       | CAN     | C        |              1 |            6.00 |             3 |
|           19 | Sabres    |   18 | Last   | Matt Tennyson       | USA     | D        |              2 |            4.00 |             0 |
|           19 | Sabres    |   18 | Last   | Zemgus Girgensons   | EUR     | C        |              7 |           18.57 |            20 |
|           19 | Sabres    |   18 | Last   | Jake McCabe         | USA     | D        |              7 |           27.71 |            11 |
|           19 | Sabres    |   18 | Last   | Danny O’Regan       | USA     | C        |              2 |            0.00 |             0 |
|           19 | Sabres    |   18 | Last   | Hudson Fasching     | USA     | R        |              3 |            2.67 |             1 |
|           19 | Sabres    |   18 | Last   | Justin Bailey       | USA     | R        |              3 |            2.67 |             3 |
|           19 | Sabres    |   18 | Last   | Nick Baptiste       | CAN     | R        |              2 |           10.00 |             5 |
|           19 | Sabres    |   18 | Last   | Rasmus Ristolainen  | EUR     | D        |              7 |           36.43 |            32 |
|           19 | Sabres    |   18 | Last   | Sam Reinhart        | CAN     | C        |              6 |           13.33 |            42 |
|           19 | Sabres    |   18 | Last   | Jack Eichel         | USA     | C        |              5 |           27.20 |            67 |
|           19 | Sabres    |   18 | Last   | Brendan Guhle       | CAN     | D        |              3 |            4.00 |             2 |
|           19 | Sabres    |   18 | Last   | Evan Rodrigues      | CAN     | C        |              5 |           10.60 |            14 |
|           19 | Sabres    |   18 | Last   | Casey Nelson        | USA     | D        |              4 |            8.25 |             4 |
|           19 | Sabres    |   18 | Last   | Kyle Criscuolo      | USA     | C        |              1 |            4.00 |             0 |
|           19 | Sabres    |   18 | Last   | Alex Nylander       | CAN     | L        |              3 |            1.33 |             2 |
|           19 | Sabres    |   18 | Last   | Victor Antipin      | EUR     | D        |              1 |           18.00 |            10 |
|           19 | Sabres    |   18 | Last   | Casey Mittelstadt   | USA     | C        |              3 |            4.67 |            13 |
|           31 | Lightning |   19 | First  | Braydon Coburn      | CAN     | D        |              6 |           33.67 |            11 |
|           31 | Lightning |   19 | First  | Ryan Callahan       | USA     | R        |              6 |           26.67 |            22 |
|           31 | Lightning |   19 | First  | Anton Stralman      | EUR     | D        |              5 |           18.40 |            26 |
|           31 | Lightning |   19 | First  | Dan Girardi         | CAN     | D        |              2 |           19.50 |            17 |
|           31 | Lightning |   19 | First  | Alex Killorn        | CAN     | L        |              8 |           41.62 |            39 |
|           31 | Lightning |   19 | First  | Ryan McDonagh       | USA     | D        |              3 |           17.67 |            20 |
|           31 | Lightning |   19 | First  | Steven Stamkos      | CAN     | C        |             12 |           41.58 |            69 |
|           31 | Lightning |   19 | First  | Cameron Gaunce      | CAN     | D        |              2 |            5.50 |             2 |
|           31 | Lightning |   19 | First  | Tyler Johnson       | USA     | C        |              8 |           21.25 |            42 |
|           31 | Lightning |   19 | First  | Victor Hedman       | EUR     | D        |             11 |           50.91 |            43 |
|           31 | Lightning |   19 | First  | Cory Conacher       | CAN     | C        |              5 |           10.00 |             8 |
|           31 | Lightning |   19 | First  | Ondrej Palat        | EUR     | L        |              8 |           18.88 |            41 |
|           31 | Lightning |   19 | First  | Nikita Kucherov     | EUR     | R        |              7 |           37.29 |            78 |
|           31 | Lightning |   19 | First  | J.T. Miller         | USA     | C        |              2 |           21.00 |            32 |
|           31 | Lightning |   19 | First  | Yanni Gourde        | CAN     | C        |              5 |           35.00 |            30 |
|           31 | Lightning |   19 | First  | Slater Koekkoek     | CAN     | D        |              5 |            6.80 |             3 |
|           31 | Lightning |   19 | First  | Cedric Paquette     | CAN     | C        |              7 |           49.29 |            12 |
|           31 | Lightning |   19 | First  | Adam Erne           | USA     | L        |              3 |           20.67 |             9 |
|           31 | Lightning |   19 | First  | Brayden Point       | CAN     | C        |              4 |           19.25 |            66 |
|           31 | Lightning |   19 | First  | Danick Martel       | CAN     | L        |              1 |            8.00 |             2 |
|           31 | Lightning |   19 | First  | Erik Cernak         | EUR     | D        |              2 |           58.50 |            14 |
|           31 | Lightning |   19 | First  | Mathieu Joseph      | CAN     | R        |              2 |           21.00 |            16 |
|           31 | Lightning |   19 | First  | Anthony Cirelli     | CAN     | C        |              3 |           23.33 |            31 |
|           31 | Lightning |   19 | First  | Mikhail Sergachev   | EUR     | D        |              3 |           41.33 |            35 |
|           31 | Lightning |   19 | First  | Jan Rutta           | EUR     | D        |              2 |            9.00 |             4 |
|           30 | Senators  |   19 | Last   | Bobby Ryan          | USA     | R        |              7 |           27.43 |            38 |
|           30 | Senators  |   19 | Last   | Tom Pyatt           | CAN     | L        |              3 |            9.33 |            16 |
|           30 | Senators  |   19 | Last   | Justin Falk         | CAN     | D        |              1 |           11.00 |             0 |
|           30 | Senators  |   19 | Last   | Paul Carey          | USA     | C        |              1 |            0.00 |             0 |
|           30 | Senators  |   19 | Last   | Zack Smith          | CAN     | C        |             11 |           63.00 |            18 |
|           30 | Senators  |   19 | Last   | Mikkel Boedker      | EUR     | L        |              2 |            3.00 |            20 |
|           30 | Senators  |   19 | Last   | Cody Goloubef       | CAN     | D        |              2 |            5.00 |             1 |
|           30 | Senators  |   19 | Last   | Mark Borowiecki     | CAN     | D        |              9 |           71.89 |             6 |
|           30 | Senators  |   19 | Last   | Matt Duchene        | CAN     | C        |              2 |           10.00 |            54 |
|           30 | Senators  |   19 | Last   | Magnus Paajarvi     | EUR     | L        |              2 |            5.00 |            14 |
|           30 | Senators  |   19 | Last   | Stefan Elliott      | CAN     | D        |              1 |            0.00 |             1 |
|           30 | Senators  |   19 | Last   | Chris Wideman       | USA     | D        |              4 |           24.50 |            11 |
|           30 | Senators  |   19 | Last   | Darren Archibald    | CAN     | R        |              1 |            0.00 |             0 |
|           30 | Senators  |   19 | Last   | Oscar Lindberg      | EUR     | L        |              1 |            4.00 |             8 |
|           30 | Senators  |   19 | Last   | Mark Stone          | CAN     | R        |              7 |           16.43 |            44 |
|           30 | Senators  |   19 | Last   | Erik Burgdoerfer    | USA     | D        |              2 |            1.00 |             0 |
|           30 | Senators  |   19 | Last   | Brian Gibbons       | USA     | C        |              1 |            4.00 |            14 |
|           30 | Senators  |   19 | Last   | Ryan Dzingel        | USA     | C        |              4 |           26.25 |            32 |
|           30 | Senators  |   19 | Last   | Max McCormick       | USA     | L        |              4 |           19.50 |             2 |
|           30 | Senators  |   19 | Last   | Dylan DeMelo        | CAN     | D        |              2 |           31.50 |            16 |
|           30 | Senators  |   19 | Last   | Jean-Gabriel Pageau | CAN     | C        |              8 |           19.12 |            23 |
|           30 | Senators  |   19 | Last   | Cody Ceci           | CAN     | D        |              6 |           14.67 |            20 |
|           30 | Senators  |   19 | Last   | Chris Tierney       | CAN     | C        |              2 |           23.00 |            42 |
|           30 | Senators  |   19 | Last   | Anthony Duclair     | CAN     | L        |              2 |           10.00 |            27 |
|           30 | Senators  |   19 | Last   | Nick Paul           | CAN     | L        |              5 |            6.80 |             6 |
|           30 | Senators  |   19 | Last   | Ben Harpur          | CAN     | D        |              4 |           19.75 |             2 |
|           30 | Senators  |   19 | Last   | Andreas Englund     | EUR     | D        |              4 |            6.00 |             1 |
|           30 | Senators  |   19 | Last   | Jack Rodewald       | CAN     | R        |              2 |            1.00 |             0 |
|           30 | Senators  |   19 | Last   | Colin White         | USA     | C        |              4 |           17.75 |            18 |
|           30 | Senators  |   19 | Last   | Thomas Chabot       | CAN     | D        |              4 |           22.00 |            30 |
|           30 | Senators  |   19 | Last   | Filip Chlapik       | EUR     | C        |              3 |            6.00 |             4 |
|           30 | Senators  |   19 | Last   | Christian Wolanin   | CAN     | D        |              3 |            2.00 |             5 |
|           30 | Senators  |   19 | Last   | Christian Jaros     | EUR     | D        |              3 |           11.00 |             4 |
|           30 | Senators  |   19 | Last   | Rudolfs Balcers     | EUR     | L        |              2 |            5.00 |             8 |
|           30 | Senators  |   19 | Last   | Maxime Lajoie       | CAN     | D        |              2 |           10.00 |             8 |
|           30 | Senators  |   19 | Last   | Logan Brown         | USA     | C        |              3 |            1.33 |             3 |
|           30 | Senators  |   19 | Last   | Vitaly Abramov      | EUR     | L        |              2 |            1.00 |             0 |
|           30 | Senators  |   19 | Last   | Alex Formenton      | CAN     | L        |              2 |            3.00 |             0 |
|           30 | Senators  |   19 | Last   | Erik Brannstrom     | EUR     | D        |              2 |            8.00 |             2 |
|           30 | Senators  |   19 | Last   | Drake Batherson     | USA     | R        |              2 |            9.50 |            10 |
|           30 | Senators  |   19 | Last   | Max Veronneau       | CAN     | R        |              2 |            0.00 |             2 |
|           30 | Senators  |   19 | Last   | Brady Tkachuk       | USA     | L        |              2 |           90.50 |            44 |

Preview of 2017 - 2019 Team Rosters: Presidents Cup vs Last Place

|     | CAN | EUR | USA |
|:----|----:|----:|----:|
| C   |  29 |  11 |  13 |
| D   |  33 |  18 |  16 |
| L   |  18 |  14 |   7 |
| R   |  13 |   6 |  12 |

Player Position by Country

|     | CAN | EUR | USA |
|:----|----:|----:|----:|
| C   |  14 |   5 |   4 |
| D   |  10 |  10 |   8 |
| L   |   5 |   7 |   3 |
| R   |   5 |   4 |   5 |

Presidents Cup Winners

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

![](README_files/figure-gfm/univariate%20bar%20graphs-1.png)<!-- -->![](README_files/figure-gfm/univariate%20bar%20graphs-2.png)<!-- -->![](README_files/figure-gfm/univariate%20bar%20graphs-3.png)<!-- -->

### 2 Factors

![](README_files/figure-gfm/2%20factor%20bar%20graphs-1.png)<!-- -->![](README_files/figure-gfm/2%20factor%20bar%20graphs-2.png)<!-- -->

### 3 Factors

![](README_files/figure-gfm/3%20factor%20bar%20graphs-1.png)<!-- -->

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.75 |            9.21 |          6.50 |
| Median  |           4.50 |           17.79 |         18.50 |
| Mean    |           5.21 |           25.53 |         24.96 |
| 3rd Qu. |           7.00 |           35.51 |         35.75 |
| Max.    |          15.00 |          146.71 |         85.00 |

Team: Capitals

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.00 |           10.67 |          6.00 |
| Median  |           3.00 |           23.00 |         18.00 |
| Mean    |           3.85 |           27.78 |         19.61 |
| 3rd Qu. |           5.00 |           36.60 |         26.00 |
| Max.    |          10.00 |          135.90 |         71.00 |

Team: Avalanche

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          1.00 |
| 1st Qu. |           3.00 |           15.67 |          5.50 |
| Median  |           5.00 |           25.00 |         19.00 |
| Mean    |           5.04 |           27.65 |         20.93 |
| 3rd Qu. |           7.00 |           31.03 |         33.00 |
| Max.    |           9.00 |           89.43 |         50.00 |

Team: Predators

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.00 |            4.67 |          3.50 |
| Median  |           3.00 |           10.60 |          8.00 |
| Mean    |           3.54 |           18.71 |         15.23 |
| 3rd Qu. |           5.00 |           27.45 |         19.50 |
| Max.    |          11.00 |           87.00 |         67.00 |

Team: Sabres

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            5.50 |          2.00 |
| 1st Qu. |           2.00 |           18.40 |         11.00 |
| Median  |           5.00 |           21.00 |         22.00 |
| Mean    |           4.88 |           26.24 |         26.88 |
| 3rd Qu. |           7.00 |           37.29 |         39.00 |
| Max.    |          12.00 |           58.50 |         78.00 |

Team: Lightning

|         | Player Seasons | Avg Penalty Min | Avg Total Pts |
|:--------|---------------:|----------------:|--------------:|
| Min.    |           1.00 |            0.00 |          0.00 |
| 1st Qu. |           2.00 |            3.25 |          2.00 |
| Median  |           2.00 |            9.41 |          8.00 |
| Mean    |           3.24 |           14.77 |         13.19 |
| 3rd Qu. |           4.00 |           19.41 |         19.50 |
| Max.    |          11.00 |           90.50 |         54.00 |

Team: Senators

![](README_files/figure-gfm/dotplot%20by%20TotalPoints-1.png)<!-- -->
![](README_files/figure-gfm/dotplot%20by%20Penalty%20Minutes-1.png)<!-- -->

![](README_files/figure-gfm/dotplot%20by-1.png)<!-- -->

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

| franchiseId | jerseyNumber | person.id | person.fullName | person.link            | position.code | position.name | position.type | position.abbreviation |
|------------:|:-------------|----------:|:----------------|:-----------------------|:--------------|:--------------|:--------------|:----------------------|
|           5 | 19           |   8469455 | Jason Spezza    | /api/v1/people/8469455 | C             | Center        | Forward       | C                     |
|           5 | 8            |   8474162 | Jake Muzzin     | /api/v1/people/8474162 | D             | Defenseman    | Defenseman    | D                     |
|           5 | 73           |   8475160 | Kyle Clifford   | /api/v1/people/8475160 | L             | Left Wing     | Forward       | LW                    |
|           5 | 91           |   8475166 | John Tavares    | /api/v1/people/8475166 | C             | Center        | Forward       | C                     |
|           5 | 94           |   8475197 | Tyson Barrie    | /api/v1/people/8475197 | D             | Defenseman    | Defenseman    | D                     |
|           5 | 52           |   8475716 | Martin Marincin | /api/v1/people/8475716 | D             | Defenseman    | Defenseman    | D                     |

|  id | name                | link             | abbreviation | teamName    | locationName | firstYearOfPlay | shortName | officialSiteUrl                                                                 | franchiseId | active | venue.name       | venue.link          | venue.city | venue.timeZone.id | venue.timeZone.offset | venue.timeZone.tz | division.id | division.name | division.nameShort | division.link        | division.abbreviation | conference.id | conference.name | conference.link       | franchise.franchiseId | franchise.teamName | franchise.link       |
|----:|:--------------------|:-----------------|:-------------|:------------|:-------------|:----------------|:----------|:--------------------------------------------------------------------------------|------------:|:-------|:-----------------|:--------------------|:-----------|:------------------|----------------------:|:------------------|------------:|:--------------|:-------------------|:---------------------|:----------------------|--------------:|:----------------|:----------------------|----------------------:|:-------------------|:---------------------|
|  10 | Toronto Maple Leafs | /api/v1/teams/10 | TOR          | Maple Leafs | Toronto      | 1917            | Toronto   | <a href="http://www.mapleleafs.com/" class="uri">http://www.mapleleafs.com/</a> |           5 | TRUE   | Scotiabank Arena | /api/v1/venues/null | Toronto    | America/Toronto   |                    -4 | EDT               |          17 | Atlantic      | ATL                | /api/v1/divisions/17 | A                     |             6 | Eastern         | /api/v1/conferences/6 |                     5 | Maple Leafs        | /api/v1/franchises/5 |

|      id | fullName        | link                   | firstName | lastName | primaryNumber | birthDate  | currentAge | birthCity | birthStateProvince | birthCountry | nationality | height | weight | active | alternateCaptain | captain | rookie | shootsCatches | rosterStatus | currentTeam.id | currentTeam.name    | currentTeam.link | primaryPosition.code | primaryPosition.name | primaryPosition.type | primaryPosition.abbreviation |
|--------:|:----------------|:-----------------------|:----------|:---------|:--------------|:-----------|-----------:|:----------|:-------------------|:-------------|:------------|:-------|-------:|:-------|:-----------------|:--------|:-------|:--------------|:-------------|---------------:|:--------------------|:-----------------|:---------------------|:---------------------|:---------------------|:-----------------------------|
| 8468508 | Justin Williams | /api/v1/people/8468508 | Justin    | Williams | 14            | 1981-10-04 |         38 | Cobourg   | ON                 | CAN          | CAN         | 6’ 1"  |    184 | TRUE   | FALSE            | FALSE   | FALSE  | R             | Y            |             12 | Carolina Hurricanes | /api/v1/teams/12 | R                    | Right Wing           | Forward              | RW                           |

\|\| \|\| \|\| \|\|

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

| franchiseId | jerseyNumber | person.id | person.fullName | person.link            | position.code | position.name | position.type | position.abbreviation | teamName   |
|------------:|:-------------|----------:|:----------------|:-----------------------|:--------------|:--------------|:--------------|:----------------------|:-----------|
|          26 | 17           |   8445735 | Rod Brind’Amour | /api/v1/people/8445735 | C             | Center        | Forward       | C                     | Hurricanes |
|          26 | 28           |   8450725 | Mark Recchi     | /api/v1/people/8450725 | R             | Right Wing    | Forward       | RW                    | Hurricanes |
|          26 | 2            |   8452371 | Glen Wesley     | /api/v1/people/8452371 | D             | Defenseman    | Defenseman    | D                     | Hurricanes |
|          26 | 3            |   8456547 | Bret Hedican    | /api/v1/people/8456547 | D             | Defenseman    | Defenseman    | D                     | Hurricanes |
|          26 | 93           |   8458361 | Doug Weight     | /api/v1/people/8458361 | C             | Center        | Forward       | C                     | Hurricanes |
|          26 | 4            |   8458519 | Aaron Ward      | /api/v1/people/8458519 | D             | Defenseman    | Defenseman    | D                     | Hurricanes |
