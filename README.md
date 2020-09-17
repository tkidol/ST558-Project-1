NHL
================
Todd Idol
9/8/2020

-   [NHL Franchises](#nhl-franchises)
    -   [2017 & 2018 PHigh Points Team vs. Low Points Team
        Analysis](#phigh-points-team-vs.-low-points-team-analysis)
        -   [Language](#language)
-   [2020 Player Origin Country vs Penalty Minutes by Conference
    Analysis](#player-origin-country-vs-penalty-minutes-by-conference-analysis)

NHL Franchises
==============

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
    ## $ firstName                   <chr> "Jean", "Henri", "Maurice", "Guy", "Chr...
    ## $ franchiseId                 <int> 1, 1, 1, 1, 1, 1
    ## $ franchiseName               <chr> "Montréal Canadiens", "Montréal Canadie...
    ## $ gameTypeId                  <int> 2, 2, 2, 2, 2, 2
    ## $ gamesPlayed                 <int> 1125, 1258, 978, 961, 523, 871
    ## $ goals                       <int> 507, 358, 544, 518, 88, 408
    ## $ lastName                    <chr> "Beliveau", "Richard", "Richard", "Lafl...
    ## $ mostAssistsGameDates        <chr> "1955-02-19, 1956-12-01, 1962-11-24, 19...
    ## $ mostAssistsOneGame          <int> 4, 5, 5, 4, 2, 4
    ## $ mostAssistsOneSeason        <int> 58, 52, 36, 80, 16, 45
    ## $ mostAssistsSeasonIds        <chr> "19601961", "19571958", "19541955", "19...
    ## $ mostGoalsGameDates          <chr> "1955-11-05, 1959-03-07, 1969-02-11", "...
    ## $ mostGoalsOneGame            <int> 4, 3, 5, 4, 2, 4
    ## $ mostGoalsOneSeason          <int> 47, 30, 50, 60, 21, 60
    ## $ mostGoalsSeasonIds          <chr> "19551956", "19591960", "19441945", "19...
    ## $ mostPenaltyMinutesOneSeason <int> 143, 91, 125, 51, 358, 51
    ## $ mostPenaltyMinutesSeasonIds <chr> "19551956", "19601961", "19541955", "19...
    ## $ mostPointsGameDates         <chr> "1959-03-07", "1957-10-17", "1944-12-28...
    ## $ mostPointsOneGame           <int> 7, 6, 8, 6, 3, 5
    ## $ mostPointsOneSeason         <int> 91, 80, 74, 136, 37, 105
    ## $ mostPointsSeasonIds         <chr> "19581959", "19571958", "19541955", "19...
    ## $ penaltyMinutes              <int> 1033, 932, 1287, 381, 2248, 400
    ## $ playerId                    <int> 8445408, 8448320, 8448321, 8448624, 844...
    ## $ points                      <int> 1219, 1046, 966, 1246, 175, 776
    ## $ positionCode                <chr> "C", "C", "R", "R", "R", "L"
    ## $ rookiePoints                <int> 34, 40, 11, 64, 15, 16
    ## $ seasons                     <int> 20, 20, 18, 14, 10, 13

    ##    id                  name             link abbreviation       teamName
    ## 1   1     New Jersey Devils  /api/v1/teams/1          NJD         Devils
    ## 2   2    New York Islanders  /api/v1/teams/2          NYI      Islanders
    ## 3   3      New York Rangers  /api/v1/teams/3          NYR        Rangers
    ## 4   4   Philadelphia Flyers  /api/v1/teams/4          PHI         Flyers
    ## 5   5   Pittsburgh Penguins  /api/v1/teams/5          PIT       Penguins
    ## 6   6         Boston Bruins  /api/v1/teams/6          BOS         Bruins
    ## 7   7        Buffalo Sabres  /api/v1/teams/7          BUF         Sabres
    ## 8   8    Montréal Canadiens  /api/v1/teams/8          MTL      Canadiens
    ## 9   9       Ottawa Senators  /api/v1/teams/9          OTT       Senators
    ## 10 10   Toronto Maple Leafs /api/v1/teams/10          TOR    Maple Leafs
    ## 11 12   Carolina Hurricanes /api/v1/teams/12          CAR     Hurricanes
    ## 12 13      Florida Panthers /api/v1/teams/13          FLA       Panthers
    ## 13 14   Tampa Bay Lightning /api/v1/teams/14          TBL      Lightning
    ## 14 15   Washington Capitals /api/v1/teams/15          WSH       Capitals
    ## 15 16    Chicago Blackhawks /api/v1/teams/16          CHI     Blackhawks
    ## 16 17     Detroit Red Wings /api/v1/teams/17          DET      Red Wings
    ## 17 18   Nashville Predators /api/v1/teams/18          NSH      Predators
    ## 18 19       St. Louis Blues /api/v1/teams/19          STL          Blues
    ## 19 20        Calgary Flames /api/v1/teams/20          CGY         Flames
    ## 20 21    Colorado Avalanche /api/v1/teams/21          COL      Avalanche
    ## 21 22       Edmonton Oilers /api/v1/teams/22          EDM         Oilers
    ## 22 23     Vancouver Canucks /api/v1/teams/23          VAN        Canucks
    ## 23 24         Anaheim Ducks /api/v1/teams/24          ANA          Ducks
    ## 24 25          Dallas Stars /api/v1/teams/25          DAL          Stars
    ## 25 26     Los Angeles Kings /api/v1/teams/26          LAK          Kings
    ## 26 28       San Jose Sharks /api/v1/teams/28          SJS         Sharks
    ## 27 29 Columbus Blue Jackets /api/v1/teams/29          CBJ   Blue Jackets
    ## 28 30        Minnesota Wild /api/v1/teams/30          MIN           Wild
    ## 29 52         Winnipeg Jets /api/v1/teams/52          WPG           Jets
    ## 30 53       Arizona Coyotes /api/v1/teams/53          ARI        Coyotes
    ## 31 54  Vegas Golden Knights /api/v1/teams/54          VGK Golden Knights
    ##    locationName firstYearOfPlay    shortName                    officialSiteUrl
    ## 1    New Jersey            1982   New Jersey    http://www.newjerseydevils.com/
    ## 2      New York            1972 NY Islanders   http://www.newyorkislanders.com/
    ## 3      New York            1926   NY Rangers     http://www.newyorkrangers.com/
    ## 4  Philadelphia            1967 Philadelphia http://www.philadelphiaflyers.com/
    ## 5    Pittsburgh            1967   Pittsburgh     http://pittsburghpenguins.com/
    ## 6        Boston            1924       Boston       http://www.bostonbruins.com/
    ## 7       Buffalo            1970      Buffalo             http://www.sabres.com/
    ## 8      Montréal            1909     Montréal          http://www.canadiens.com/
    ## 9        Ottawa            1990       Ottawa     http://www.ottawasenators.com/
    ## 10      Toronto            1917      Toronto         http://www.mapleleafs.com/
    ## 11     Carolina            1979     Carolina http://www.carolinahurricanes.com/
    ## 12      Florida            1993      Florida    http://www.floridapanthers.com/
    ## 13    Tampa Bay            1991    Tampa Bay  http://www.tampabaylightning.com/
    ## 14   Washington            1974   Washington http://www.washingtoncapitals.com/
    ## 15      Chicago            1926      Chicago  http://www.chicagoblackhawks.com/
    ## 16      Detroit            1926      Detroit    http://www.detroitredwings.com/
    ## 17    Nashville            1997    Nashville http://www.nashvillepredators.com/
    ## 18    St. Louis            1967     St Louis       http://www.stlouisblues.com/
    ## 19      Calgary            1980      Calgary      http://www.calgaryflames.com/
    ## 20     Colorado            1979     Colorado  http://www.coloradoavalanche.com/
    ## 21     Edmonton            1979     Edmonton     http://www.edmontonoilers.com/
    ## 22    Vancouver            1970    Vancouver            http://www.canucks.com/
    ## 23      Anaheim            1993      Anaheim       http://www.anaheimducks.com/
    ## 24       Dallas            1967       Dallas        http://www.dallasstars.com/
    ## 25  Los Angeles            1967  Los Angeles            http://www.lakings.com/
    ## 26     San Jose            1990     San Jose           http://www.sjsharks.com/
    ## 27     Columbus            1997     Columbus        http://www.bluejackets.com/
    ## 28    Minnesota            1997    Minnesota               http://www.wild.com/
    ## 29     Winnipeg            2011     Winnipeg           http://winnipegjets.com/
    ## 30      Arizona            1979      Arizona     http://www.arizonacoyotes.com/
    ## 31        Vegas            2016        Vegas http://www.vegasgoldenknights.com/
    ##    franchiseId active               venue.name          venue.link   venue.city
    ## 1           23   TRUE        Prudential Center /api/v1/venues/null       Newark
    ## 2           22   TRUE          Barclays Center /api/v1/venues/5026     Brooklyn
    ## 3           10   TRUE    Madison Square Garden /api/v1/venues/5054     New York
    ## 4           16   TRUE       Wells Fargo Center /api/v1/venues/5096 Philadelphia
    ## 5           17   TRUE         PPG Paints Arena /api/v1/venues/5034   Pittsburgh
    ## 6            6   TRUE                TD Garden /api/v1/venues/5085       Boston
    ## 7           19   TRUE           KeyBank Center /api/v1/venues/5039      Buffalo
    ## 8            1   TRUE              Bell Centre /api/v1/venues/5028     Montréal
    ## 9           30   TRUE     Canadian Tire Centre /api/v1/venues/5031       Ottawa
    ## 10           5   TRUE         Scotiabank Arena /api/v1/venues/null      Toronto
    ## 11          26   TRUE                PNC Arena /api/v1/venues/5066      Raleigh
    ## 12          33   TRUE              BB&T Center /api/v1/venues/5027      Sunrise
    ## 13          31   TRUE             AMALIE Arena /api/v1/venues/null        Tampa
    ## 14          24   TRUE        Capital One Arena /api/v1/venues/5094   Washington
    ## 15          11   TRUE            United Center /api/v1/venues/5092      Chicago
    ## 16          12   TRUE     Little Caesars Arena /api/v1/venues/5145      Detroit
    ## 17          34   TRUE        Bridgestone Arena /api/v1/venues/5030    Nashville
    ## 18          18   TRUE        Enterprise Center /api/v1/venues/5076    St. Louis
    ## 19          21   TRUE    Scotiabank Saddledome /api/v1/venues/5075      Calgary
    ## 20          27   TRUE             Pepsi Center /api/v1/venues/5064       Denver
    ## 21          25   TRUE             Rogers Place /api/v1/venues/5100     Edmonton
    ## 22          20   TRUE             Rogers Arena /api/v1/venues/5073    Vancouver
    ## 23          32   TRUE             Honda Center /api/v1/venues/5046      Anaheim
    ## 24          15   TRUE American Airlines Center /api/v1/venues/5019       Dallas
    ## 25          14   TRUE           STAPLES Center /api/v1/venues/5081  Los Angeles
    ## 26          29   TRUE   SAP Center at San Jose /api/v1/venues/null     San Jose
    ## 27          36   TRUE         Nationwide Arena /api/v1/venues/5059     Columbus
    ## 28          37   TRUE       Xcel Energy Center /api/v1/venues/5098     St. Paul
    ## 29          35   TRUE           Bell MTS Place /api/v1/venues/5058     Winnipeg
    ## 30          28   TRUE         Gila River Arena /api/v1/venues/5043     Glendale
    ## 31          38   TRUE           T-Mobile Arena /api/v1/venues/5178    Las Vegas
    ##    venue.id   venue.timeZone.id venue.timeZone.offset venue.timeZone.tz
    ## 1        NA    America/New_York                    -4               EDT
    ## 2      5026    America/New_York                    -4               EDT
    ## 3      5054    America/New_York                    -4               EDT
    ## 4      5096    America/New_York                    -4               EDT
    ## 5      5034    America/New_York                    -4               EDT
    ## 6      5085    America/New_York                    -4               EDT
    ## 7      5039    America/New_York                    -4               EDT
    ## 8      5028    America/Montreal                    -4               EDT
    ## 9      5031    America/New_York                    -4               EDT
    ## 10       NA     America/Toronto                    -4               EDT
    ## 11     5066    America/New_York                    -4               EDT
    ## 12     5027    America/New_York                    -4               EDT
    ## 13       NA    America/New_York                    -4               EDT
    ## 14     5094    America/New_York                    -4               EDT
    ## 15     5092     America/Chicago                    -5               CDT
    ## 16     5145     America/Detroit                    -4               EDT
    ## 17     5030     America/Chicago                    -5               CDT
    ## 18     5076     America/Chicago                    -5               CDT
    ## 19     5075      America/Denver                    -6               MDT
    ## 20     5064      America/Denver                    -6               MDT
    ## 21     5100    America/Edmonton                    -6               MDT
    ## 22     5073   America/Vancouver                    -7               PDT
    ## 23     5046 America/Los_Angeles                    -7               PDT
    ## 24     5019     America/Chicago                    -5               CDT
    ## 25     5081 America/Los_Angeles                    -7               PDT
    ## 26       NA America/Los_Angeles                    -7               PDT
    ## 27     5059    America/New_York                    -4               EDT
    ## 28     5098     America/Chicago                    -5               CDT
    ## 29     5058    America/Winnipeg                    -5               CDT
    ## 30     5043     America/Phoenix                    -7               MST
    ## 31     5178 America/Los_Angeles                    -7               PDT
    ##    division.id division.name division.nameShort        division.link
    ## 1           18  Metropolitan              Metro /api/v1/divisions/18
    ## 2           18  Metropolitan              Metro /api/v1/divisions/18
    ## 3           18  Metropolitan              Metro /api/v1/divisions/18
    ## 4           18  Metropolitan              Metro /api/v1/divisions/18
    ## 5           18  Metropolitan              Metro /api/v1/divisions/18
    ## 6           17      Atlantic                ATL /api/v1/divisions/17
    ## 7           17      Atlantic                ATL /api/v1/divisions/17
    ## 8           17      Atlantic                ATL /api/v1/divisions/17
    ## 9           17      Atlantic                ATL /api/v1/divisions/17
    ## 10          17      Atlantic                ATL /api/v1/divisions/17
    ## 11          18  Metropolitan              Metro /api/v1/divisions/18
    ## 12          17      Atlantic                ATL /api/v1/divisions/17
    ## 13          17      Atlantic                ATL /api/v1/divisions/17
    ## 14          18  Metropolitan              Metro /api/v1/divisions/18
    ## 15          16       Central                CEN /api/v1/divisions/16
    ## 16          17      Atlantic                ATL /api/v1/divisions/17
    ## 17          16       Central                CEN /api/v1/divisions/16
    ## 18          16       Central                CEN /api/v1/divisions/16
    ## 19          15       Pacific                PAC /api/v1/divisions/15
    ## 20          16       Central                CEN /api/v1/divisions/16
    ## 21          15       Pacific                PAC /api/v1/divisions/15
    ## 22          15       Pacific                PAC /api/v1/divisions/15
    ## 23          15       Pacific                PAC /api/v1/divisions/15
    ## 24          16       Central                CEN /api/v1/divisions/16
    ## 25          15       Pacific                PAC /api/v1/divisions/15
    ## 26          15       Pacific                PAC /api/v1/divisions/15
    ## 27          18  Metropolitan              Metro /api/v1/divisions/18
    ## 28          16       Central                CEN /api/v1/divisions/16
    ## 29          16       Central                CEN /api/v1/divisions/16
    ## 30          15       Pacific                PAC /api/v1/divisions/15
    ## 31          15       Pacific                PAC /api/v1/divisions/15
    ##    division.abbreviation conference.id conference.name       conference.link
    ## 1                      M             6         Eastern /api/v1/conferences/6
    ## 2                      M             6         Eastern /api/v1/conferences/6
    ## 3                      M             6         Eastern /api/v1/conferences/6
    ## 4                      M             6         Eastern /api/v1/conferences/6
    ## 5                      M             6         Eastern /api/v1/conferences/6
    ## 6                      A             6         Eastern /api/v1/conferences/6
    ## 7                      A             6         Eastern /api/v1/conferences/6
    ## 8                      A             6         Eastern /api/v1/conferences/6
    ## 9                      A             6         Eastern /api/v1/conferences/6
    ## 10                     A             6         Eastern /api/v1/conferences/6
    ## 11                     M             6         Eastern /api/v1/conferences/6
    ## 12                     A             6         Eastern /api/v1/conferences/6
    ## 13                     A             6         Eastern /api/v1/conferences/6
    ## 14                     M             6         Eastern /api/v1/conferences/6
    ## 15                     C             5         Western /api/v1/conferences/5
    ## 16                     A             6         Eastern /api/v1/conferences/6
    ## 17                     C             5         Western /api/v1/conferences/5
    ## 18                     C             5         Western /api/v1/conferences/5
    ## 19                     P             5         Western /api/v1/conferences/5
    ## 20                     C             5         Western /api/v1/conferences/5
    ## 21                     P             5         Western /api/v1/conferences/5
    ## 22                     P             5         Western /api/v1/conferences/5
    ## 23                     P             5         Western /api/v1/conferences/5
    ## 24                     C             5         Western /api/v1/conferences/5
    ## 25                     P             5         Western /api/v1/conferences/5
    ## 26                     P             5         Western /api/v1/conferences/5
    ## 27                     M             6         Eastern /api/v1/conferences/6
    ## 28                     C             5         Western /api/v1/conferences/5
    ## 29                     C             5         Western /api/v1/conferences/5
    ## 30                     P             5         Western /api/v1/conferences/5
    ## 31                     P             5         Western /api/v1/conferences/5
    ##    franchise.franchiseId franchise.teamName        franchise.link
    ## 1                     23             Devils /api/v1/franchises/23
    ## 2                     22          Islanders /api/v1/franchises/22
    ## 3                     10            Rangers /api/v1/franchises/10
    ## 4                     16             Flyers /api/v1/franchises/16
    ## 5                     17           Penguins /api/v1/franchises/17
    ## 6                      6             Bruins  /api/v1/franchises/6
    ## 7                     19             Sabres /api/v1/franchises/19
    ## 8                      1          Canadiens  /api/v1/franchises/1
    ## 9                     30           Senators /api/v1/franchises/30
    ## 10                     5        Maple Leafs  /api/v1/franchises/5
    ## 11                    26         Hurricanes /api/v1/franchises/26
    ## 12                    33           Panthers /api/v1/franchises/33
    ## 13                    31          Lightning /api/v1/franchises/31
    ## 14                    24           Capitals /api/v1/franchises/24
    ## 15                    11         Blackhawks /api/v1/franchises/11
    ## 16                    12          Red Wings /api/v1/franchises/12
    ## 17                    34          Predators /api/v1/franchises/34
    ## 18                    18              Blues /api/v1/franchises/18
    ## 19                    21             Flames /api/v1/franchises/21
    ## 20                    27          Avalanche /api/v1/franchises/27
    ## 21                    25             Oilers /api/v1/franchises/25
    ## 22                    20            Canucks /api/v1/franchises/20
    ## 23                    32              Ducks /api/v1/franchises/32
    ## 24                    15              Stars /api/v1/franchises/15
    ## 25                    14              Kings /api/v1/franchises/14
    ## 26                    29             Sharks /api/v1/franchises/29
    ## 27                    36       Blue Jackets /api/v1/franchises/36
    ## 28                    37               Wild /api/v1/franchises/37
    ## 29                    35               Jets /api/v1/franchises/35
    ## 30                    28            Coyotes /api/v1/franchises/28
    ## 31                    38     Golden Knights /api/v1/franchises/38

| currentTeam.id |      id | fullName        | birthCountry |
|:---------------|--------:|:----------------|:-------------|
| 12             | 8477488 | Brett Pesce     | USA          |
| 12             | 8468508 | Justin Williams | CAN          |
| 12             | 8473503 | James Reimer    | CAN          |
| 12             | 8473533 | Jordan Staal    | CAN          |
| 12             | 8474581 | Jake Gardiner   | USA          |
| 12             | 8475222 | Sami Vatanen    | FIN          |

Player Stats

    ##   stat.gamesPlayed stat.wins stat.losses stat.ot stat.pts stat.ptPctg
    ## 1               68        38          25       5       81        59.6
    ## 2               NA       9th        13th    28th     13th         9th
    ##   stat.goalsPerGame stat.goalsAgainstPerGame stat.evGGARatio
    ## 1             3.191                    2.838          1.0368
    ## 2              11th                     11th            12th
    ##   stat.powerPlayPercentage stat.powerPlayGoals stat.powerPlayGoalsAgainst
    ## 1                     22.3                  46                         39
    ## 2                      8th                 9th                       12th
    ##   stat.powerPlayOpportunities stat.penaltyKillPercentage stat.shotsPerGame
    ## 1                         206                       84.0             33.25
    ## 2                        17th                        4th               3rd
    ##   stat.shotsAllowed stat.winScoreFirst stat.winOppScoreFirst
    ## 1           29.3235              0.839                 0.324
    ## 2               2nd                9th                  13th
    ##   stat.winLeadFirstPer stat.winLeadSecondPer stat.winOutshootOpp
    ## 1                 0.95                 0.963               0.487
    ## 2                  1st                   1st                13th
    ##   stat.winOutshotByOpp stat.faceOffsTaken stat.faceOffsWon stat.faceOffsLost
    ## 1                0.643               4072             2058              2014
    ## 2                 13th                8th             10th              19th
    ##   stat.faceOffWinPercentage stat.shootingPctg stat.savePctg
    ## 1                      50.5               9.6         0.903
    ## 2                       9th                NA            NA
    ##   stat.penaltyKillOpportunities stat.savePctRank stat.shootingPctRank team.id
    ## 1                          <NA>             <NA>                 <NA>      12
    ## 2                          31st             17th                 14th      12
    ##             team.name        team.link
    ## 1 Carolina Hurricanes /api/v1/teams/12
    ## 2 Carolina Hurricanes /api/v1/teams/12

2017 & 2018 PHigh Points Team vs. Low Points Team Analysis
----------------------------------------------------------

### Language

    ## # A tibble: 6 x 8
    ##   franchiseId teamName  year rank  person.id person.fullName jerseyNumber
    ##         <int> <chr>    <dbl> <chr>     <int> <chr>           <chr>       
    ## 1          24 Capitals  2017 F       8468498 Brooks Orpik    44          
    ## 2          24 Capitals  2017 F       8468508 Justin Williams 14          
    ## 3          24 Capitals  2017 F       8471214 Alex Ovechkin   8           
    ## 4          24 Capitals  2017 F       8471476 Daniel Winnik   26          
    ## 5          24 Capitals  2017 F       8471698 T.J. Oshie      77          
    ## 6          24 Capitals  2017 F       8471702 Matt Niskanen   15          
    ## # ... with 1 more variable: position.code <chr>

    ##      id activePlayer assists firstName franchiseId       franchiseName
    ## 1 16910        FALSE     361     Calle          24 Washington Capitals
    ## 2 16982         TRUE     572      Alex          24 Washington Capitals
    ## 3 17011         TRUE     684   Nicklas          24 Washington Capitals
    ## 4 17021        FALSE     375      Dale          24 Washington Capitals
    ## 5 17075        FALSE     249    Dennis          24 Washington Capitals
    ## 6 17106        FALSE      42      Alan          24 Washington Capitals
    ##   gameTypeId gamesPlayed goals  lastName
    ## 1          2         983   113 Johansson
    ## 2          2        1152   706  Ovechkin
    ## 3          2         956   243 Backstrom
    ## 4          2         872   181    Hunter
    ## 5          2         343   182     Maruk
    ## 6          2         345    27       May
    ##                                                                                                                             mostAssistsGameDates
    ## 1 1990-02-04, 1990-10-19, 1991-03-14, 1991-03-16, 1991-11-13, 1992-03-15, 1993-03-16, 1993-12-17, 1995-04-04, 1999-03-02, 1999-11-27, 2000-10-07
    ## 2                                                                                                                                     2010-01-15
    ## 3 2008-01-19, 2008-01-21, 2008-11-15, 2009-12-05, 2010-02-04, 2010-11-11, 2013-04-02, 2013-12-10, 2013-12-20, 2017-03-18, 2018-03-24, 2018-12-11
    ## 4                                                                                                                         1991-10-23, 1993-02-13
    ## 5                                                                                                             1979-03-10, 1981-12-23, 1982-02-27
    ## 6                                                                                                                                     1992-11-22
    ##   mostAssistsOneGame mostAssistsOneSeason mostAssistsSeasonIds
    ## 1                  3                   42             19911992
    ## 2                  4                   59             20092010
    ## 3                  4                   68             20092010
    ## 4                  4                   59             19921993
    ## 5                  4                   76             19811982
    ## 6                  2                   10   19891990, 19921993
    ##                               mostGoalsGameDates mostGoalsOneGame
    ## 1 1990-10-20, 1996-02-10, 1998-01-06, 1998-12-04                2
    ## 2 2007-12-29, 2008-01-31, 2013-12-10, 2017-10-07                4
    ## 3                         2014-12-13, 2018-11-30                3
    ## 4                                     1992-03-20                3
    ## 5                         1979-10-14, 1981-12-04                4
    ## 6             1989-12-05, 1991-11-02, 1993-01-01                2
    ##   mostGoalsOneSeason mostGoalsSeasonIds mostPenaltyMinutesOneSeason
    ## 1                 15           19971998                          59
    ## 2                 65           20072008                          89
    ## 3                 33           20092010                          54
    ## 4                 28           19911992                         240
    ## 5                 60           19811982                         128
    ## 6                  7           19891990                         339
    ##   mostPenaltyMinutesSeasonIds
    ## 1                    19931994
    ## 2                    20092010
    ## 3                    20132014
    ## 4                    19871988
    ## 5                    19811982
    ## 6                    19891990
    ##                                                      mostPointsGameDates
    ## 1                                                             1991-03-14
    ## 2                         2007-12-29, 2008-01-31, 2008-03-03, 2010-01-15
    ## 3             2008-11-15, 2009-12-05, 2010-02-04, 2013-12-10, 2016-11-16
    ## 4                                     1991-10-23, 1992-11-22, 1993-02-13
    ## 5                                     1979-03-10, 1981-11-21, 1981-12-04
    ## 6 1989-11-29, 1989-12-05, 1991-11-02, 1992-11-22, 1993-01-01, 1994-01-08
    ##   mostPointsOneGame mostPointsOneSeason mostPointsSeasonIds penaltyMinutes
    ## 1                 4                  56            19911992            449
    ## 2                 5                 112            20072008            719
    ## 3                 5                 101            20092010            462
    ## 4                 4                  79            19921993           2003
    ## 5                 6                 136            19811982            365
    ## 6                 2                  17            19891990           1189
    ##   person.id points positionCode rookiePoints seasons
    ## 1   8448287    474            D           NA      15
    ## 2   8471214   1278            L          106      15
    ## 3   8473563    927            C           69      13
    ## 4   8448117    556            C           NA      12
    ## 5   8449284    431            C           NA       5
    ## 6   8449297     69            L           17       5

    ## # A tibble: 123 x 36
    ##    franchiseId teamName  year rank  person.id person.fullName jerseyNumber
    ##          <int> <chr>    <dbl> <chr>     <int> <chr>           <chr>       
    ##  1          24 Capitals  2017 F       8468498 Brooks Orpik    44          
    ##  2          24 Capitals  2017 F       8468508 Justin Williams 14          
    ##  3          24 Capitals  2017 F       8471214 Alex Ovechkin   8           
    ##  4          24 Capitals  2017 F       8471476 Daniel Winnik   26          
    ##  5          24 Capitals  2017 F       8471698 T.J. Oshie      77          
    ##  6          24 Capitals  2017 F       8471702 Matt Niskanen   15          
    ##  7          24 Capitals  2017 F       8471710 Taylor Chorney  44          
    ##  8          24 Capitals  2017 F       8473563 Nicklas Backst~ 19          
    ##  9          24 Capitals  2017 F       8473991 Karl Alzner     27          
    ## 10          24 Capitals  2017 F       8474008 Paul Carey      34          
    ## # ... with 113 more rows, and 29 more variables: position.code <chr>, id <int>,
    ## #   activePlayer <lgl>, assists <int>, firstName <chr>, franchiseName <chr>,
    ## #   gameTypeId <int>, gamesPlayed <int>, goals <int>, lastName <chr>,
    ## #   mostAssistsGameDates <chr>, mostAssistsOneGame <int>,
    ## #   mostAssistsOneSeason <int>, mostAssistsSeasonIds <chr>,
    ## #   mostGoalsGameDates <chr>, mostGoalsOneGame <int>, mostGoalsOneSeason <int>,
    ## #   mostGoalsSeasonIds <chr>, mostPenaltyMinutesOneSeason <int>,
    ## #   mostPenaltyMinutesSeasonIds <chr>, mostPointsGameDates <chr>,
    ## #   mostPointsOneGame <int>, mostPointsOneSeason <int>,
    ## #   mostPointsSeasonIds <chr>, penaltyMinutes <int>, points <int>,
    ## #   positionCode <chr>, rookiePoints <int>, seasons <int>

    ## # A tibble: 100 x 13
    ##    franchiseId teamName  year rank  person.id person.fullName jerseyNumber
    ##          <int> <chr>    <dbl> <chr>     <int> <chr>           <chr>       
    ##  1          24 Capitals  2017 F       8468498 Brooks Orpik    44          
    ##  2          24 Capitals  2017 F       8468508 Justin Williams 14          
    ##  3          24 Capitals  2017 F       8471214 Alex Ovechkin   8           
    ##  4          24 Capitals  2017 F       8471476 Daniel Winnik   26          
    ##  5          24 Capitals  2017 F       8471698 T.J. Oshie      77          
    ##  6          24 Capitals  2017 F       8471702 Matt Niskanen   15          
    ##  7          24 Capitals  2017 F       8471710 Taylor Chorney  44          
    ##  8          24 Capitals  2017 F       8473563 Nicklas Backst~ 19          
    ##  9          24 Capitals  2017 F       8473991 Karl Alzner     27          
    ## 10          24 Capitals  2017 F       8474008 Paul Carey      34          
    ## # ... with 90 more rows, and 6 more variables: position.code <chr>,
    ## #   seasons <int>, penaltyMinutes <int>, goals <int>, assists <int>,
    ## #   mostPointsOneSeason <int>

2020 Player Origin Country vs Penalty Minutes by Conference Analysis
====================================================================

    ##     continent conference playoffs currentTeam.id      id            fullName
    ## 1   N.America    Eastern    FALSE              1 8471233        Travis Zajac
    ## 2   N.America    Eastern    FALSE              1 8471239      Cory Schneider
    ## 3   N.America    Eastern    FALSE              1 8474056         P.K. Subban
    ## 4   N.America    Eastern    FALSE              1 8475151       Kyle Palmieri
    ## 5      Europe    Eastern    FALSE              1 8476368    Fredrik Claesson
    ## 6   N.America    Eastern    FALSE              1 8476923      Damon Severson
    ## 7   N.America    Eastern    FALSE              1 8476941      Connor Carrick
    ## 8      Europe    Eastern    FALSE              1 8477038        Nikita Gusev
    ## 9   N.America    Eastern    FALSE              1 8477355        Will Butcher
    ## 10  N.America    Eastern    FALSE              1 8477401         John Hayden
    ## 11  N.America    Eastern    FALSE              1 8477425          Miles Wood
    ## 12     Europe    Eastern    FALSE              1 8477509       Mirco Mueller
    ## 13  N.America    Eastern    FALSE              1 8477541       Dakota Mermis
    ## 14     Europe    Eastern    FALSE              1 8478401         Pavel Zacha
    ## 15  N.America    Eastern    FALSE              1 8478406 Mackenzie Blackwood
    ## 16  N.America    Eastern    FALSE              1 8479291        Kevin Rooney
    ## 17  N.America    Eastern    FALSE              1 8479315       Joey Anderson
    ## 18     Europe    Eastern    FALSE              1 8479407        Jesper Bratt
    ## 19  N.America    Eastern    FALSE              1 8479415      Michael McLeod
    ## 20     Europe    Eastern    FALSE              1 8480002       Nico Hischier
    ## 21  N.America    Eastern    FALSE              1 8481559         Jack Hughes
    ## 22  N.America    Eastern     TRUE              2 8470187      Johnny Boychuk
    ## 23  N.America    Eastern     TRUE              2 8471217         Andrew Ladd
    ## 24     Europe    Eastern     TRUE              2 8471306       Thomas Greiss
    ## 25  N.America    Eastern     TRUE              2 8472382         Andy Greene
    ## 26     Europe    Eastern     TRUE              2 8473463         Leo Komarov
    ## 27  N.America    Eastern     TRUE              2 8473504     Cal Clutterbuck
    ## 28  N.America    Eastern     TRUE              2 8473544     Derick Brassard
    ## 29     Europe    Eastern     TRUE              2 8473575     Semyon Varlamov
    ## 30  N.America    Eastern     TRUE              2 8474066       Thomas Hickey
    ## 31  N.America    Eastern     TRUE              2 8474573         Josh Bailey
    ## 32  N.America    Eastern     TRUE              2 8474586       Jordan Eberle
    ## 33  N.America    Eastern     TRUE              2 8474709         Matt Martin
    ## 34  N.America    Eastern     TRUE              2 8475181          Nick Leddy
    ## 35  N.America    Eastern     TRUE              2 8475231       Casey Cizikas
    ## 36  N.America    Eastern     TRUE              2 8475314          Anders Lee
    ## 37  N.America    Eastern     TRUE              2 8475754        Brock Nelson
    ## 38     Europe    Eastern     TRUE              2 8475832       Tom Kuhnhackl
    ## 39  N.America    Eastern     TRUE              2 8476419 Jean-Gabriel Pageau
    ## 40  N.America    Eastern     TRUE              2 8476429      Scott Mayfield
    ## 41     Europe    Eastern     TRUE              2 8476444  Christopher Gibson
    ## 42  N.America    Eastern     TRUE              2 8476917         Adam Pelech
    ## 43  N.America    Eastern     TRUE              2 8477506         Ryan Pulock
    ## 44  N.America    Eastern     TRUE              2 8477527       Ross Johnston
    ## 45  N.America    Eastern     TRUE              2 8477936   Michael Dal Colle
    ## 46  N.America    Eastern     TRUE              2 8478038         Devon Toews
    ## 47  N.America    Eastern     TRUE              2 8478445       Mathew Barzal
    ## 48  N.America    Eastern     TRUE              2 8478463 Anthony Beauvillier
    ## 49     Europe    Eastern     TRUE              2 8479526        Otto Koivula
    ## 50     Europe    Eastern     TRUE              2 8480222       Sebastian Aho
    ## 51  N.America    Eastern     TRUE              2 8480865         Noah Dobson
    ## 52  N.America    Eastern    FALSE              3 8474230       Micheal Haley
    ## 53     Europe    Eastern    FALSE              3 8480833     Vitali Kravtsov
    ## 54     Europe    Eastern    FALSE              3 8468685    Henrik Lundqvist
    ## 55  N.America    Eastern    FALSE              3 8471686          Marc Staal
    ## 56  N.America    Eastern    FALSE              3 8474090       Brendan Smith
    ## 57  N.America    Eastern    FALSE              3 8475184       Chris Kreider
    ## 58  N.America    Eastern    FALSE              3 8475735         Greg McKegg
    ## 59     Europe    Eastern    FALSE              3 8475855         Jesper Fast
    ## 60  N.America    Eastern    FALSE              3 8476396      Steven Fogarty
    ## 61  N.America    Eastern    FALSE              3 8476458         Ryan Strome
    ## 62     Europe    Eastern    FALSE              3 8476459      Mika Zibanejad
    ## 63  N.America    Eastern    FALSE              3 8476858 Phillip Di Giuseppe
    ## 64  N.America    Eastern    FALSE              3 8476885        Jacob Trouba
    ## 65  N.America    Eastern    FALSE              3 8476982       Danny O'Regan
    ## 66     Europe    Eastern    FALSE              3 8477402    Pavel Buchnevich
    ## 67  N.America    Eastern    FALSE              3 8477950       Tony DeAngelo
    ## 68  N.America    Eastern    FALSE              3 8477962     Brendan Lemieux
    ## 69     Europe    Eastern    FALSE              3 8478048     Igor Shesterkin
    ## 70  N.America    Eastern    FALSE              3 8478178      Darren Raddysh
    ## 71     Europe    Eastern    FALSE              3 8478550      Artemi Panarin
    ## 72  N.America    Eastern    FALSE              3 8479027     Brandon Crawley
    ## 73  N.America    Eastern    FALSE              3 8479323            Adam Fox
    ## 74  N.America    Eastern    FALSE              3 8479324       Ryan Lindgren
    ## 75  N.America    Eastern    FALSE              3 8479328     Julien Gauthier
    ## 76     Europe    Eastern    FALSE              3 8479333         Libor Hajek
    ## 77  N.America    Eastern    FALSE              3 8479353        Brett Howden
    ## 78  N.America    Eastern    FALSE              3 8479364       Tim Gettinger
    ## 79  N.America    Eastern    FALSE              3 8479968      Vinni Lettieri
    ## 80     Europe    Eastern    FALSE              3 8480078        Filip Chytil
    ## 81     Europe    Eastern    FALSE              3 8480382  Alexandar Georgiev
    ## 82     Europe    Eastern    FALSE              3 8481554         Kaapo Kakko
    ## 83  N.America    Eastern     TRUE              4 8477502        Samuel Morin
    ## 84  N.America    Eastern     TRUE              4 8473485       Chris Stewart
    ## 85  N.America    Eastern     TRUE              4 8470775       Nate Thompson
    ## 86  N.America    Eastern     TRUE              4 8470880       Brian Elliott
    ## 87  N.America    Eastern     TRUE              4 8471702       Matt Niskanen
    ## 88  N.America    Eastern     TRUE              4 8473512       Claude Giroux
    ## 89  N.America    Eastern     TRUE              4 8474027        Justin Braun
    ## 90  N.America    Eastern     TRUE              4 8474037  James van Riemsdyk
    ## 91     Europe    Eastern     TRUE              4 8474161       Jakub Voracek
    ## 92  N.America    Eastern     TRUE              4 8474683         Derek Grant
    ## 93  N.America    Eastern     TRUE              4 8475752       Tyler Pitlick
    ## 94  N.America    Eastern     TRUE              4 8475763         Kevin Hayes
    ## 95  N.America    Eastern     TRUE              4 8476404       Andy Andreoff
    ## 96  N.America    Eastern     TRUE              4 8476407       Andy Welinski
    ## 97  N.America    Eastern     TRUE              4 8476461      Sean Couturier
    ## 98  N.America    Eastern     TRUE              4 8476872      Scott Laughton
    ## 99  N.America    Eastern     TRUE              4 8476906 Shayne Gostisbehere
    ## 100    Europe    Eastern     TRUE              4 8477290       Michael Raffl
    ##     birthCountry
    ## 1            CAN
    ## 2            USA
    ## 3            CAN
    ## 4            USA
    ## 5            SWE
    ## 6            CAN
    ## 7            USA
    ## 8            RUS
    ## 9            USA
    ## 10           USA
    ## 11           USA
    ## 12           CHE
    ## 13           USA
    ## 14           CZE
    ## 15           CAN
    ## 16           USA
    ## 17           USA
    ## 18           SWE
    ## 19           CAN
    ## 20           CHE
    ## 21           USA
    ## 22           CAN
    ## 23           CAN
    ## 24           DEU
    ## 25           USA
    ## 26           FIN
    ## 27           CAN
    ## 28           CAN
    ## 29           RUS
    ## 30           CAN
    ## 31           CAN
    ## 32           CAN
    ## 33           CAN
    ## 34           USA
    ## 35           CAN
    ## 36           USA
    ## 37           USA
    ## 38           DEU
    ## 39           CAN
    ## 40           USA
    ## 41           FIN
    ## 42           CAN
    ## 43           CAN
    ## 44           CAN
    ## 45           CAN
    ## 46           CAN
    ## 47           CAN
    ## 48           CAN
    ## 49           FIN
    ## 50           SWE
    ## 51           CAN
    ## 52           CAN
    ## 53           RUS
    ## 54           SWE
    ## 55           CAN
    ## 56           CAN
    ## 57           USA
    ## 58           CAN
    ## 59           SWE
    ## 60           USA
    ## 61           CAN
    ## 62           SWE
    ## 63           CAN
    ## 64           USA
    ## 65           USA
    ## 66           RUS
    ## 67           USA
    ## 68           USA
    ## 69           RUS
    ## 70           CAN
    ## 71           RUS
    ## 72           USA
    ## 73           USA
    ## 74           USA
    ## 75           CAN
    ## 76           CZE
    ## 77           CAN
    ## 78           USA
    ## 79           USA
    ## 80           CZE
    ## 81           RUS
    ## 82           FIN
    ## 83           CAN
    ## 84           CAN
    ## 85           USA
    ## 86           CAN
    ## 87           USA
    ## 88           CAN
    ## 89           USA
    ## 90           USA
    ## 91           CZE
    ## 92           CAN
    ## 93           USA
    ## 94           USA
    ## 95           CAN
    ## 96           USA
    ## 97           USA
    ## 98           CAN
    ## 99           USA
    ## 100          AUT

    ## Rows: 896
    ## Columns: 7
    ## $ continent      <chr> "N.America", "N.America", "N.America", "N.America", ...
    ## $ conference     <chr> "Eastern", "Eastern", "Eastern", "Eastern", "Eastern...
    ## $ playoffs       <lgl> FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FAL...
    ## $ currentTeam.id <int> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1...
    ## $ id             <int> 8471233, 8471239, 8474056, 8475151, 8476368, 8476923...
    ## $ fullName       <chr> "Travis Zajac", "Cory Schneider", "P.K. Subban", "Ky...
    ## $ birthCountry   <chr> "CAN", "USA", "CAN", "USA", "SWE", "CAN", "USA", "RU...

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

\#\#{r, user input} t\_id &lt;- FranchiseAPI()\[ , “Team ID”\]
selectInput(“n”,label = “Choose a Team ID”, choices = t\_id, selected =
26) renderDT({RosterAPI(input$n)})

down::render(“P1\_TKIdol.Rmd”, output\_file = “README.md”) \`\`\`
