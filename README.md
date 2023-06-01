# Cricket-Analytics
End-to-End T20 World Cup Analytics with Web Scraping, Python, Pandas, and Power BI In this end-to-end data analytics project I have used cricket T20 world cup (2022) data to build insights on a best 11 players team I used bright data web scraping to collect data from espncricinfo website then we performed some data transformation and cleaning in pandas, followed by building dashboards in power bi.

Importing Libraries:

The pandas library is imported and assigned the alias pd. The json library is imported to handle JSON data. Loading and Processing Match Results:
The code opens the "t20_wc_match_results.json" file using the open() function and reads its content using json.load() to load the JSON data into a variable called data. The data is then used to create a DataFrame named df_match by extracting the "matchSummary" from the first element of data. The first 10 rows of df_match are displayed using df_match.head(10). The column name "scorecard" is renamed to "match_id" in df_match using df_match.rename().

Saving Match Results to CSV:

The df_batting DataFrame is saved as a CSV file named "match results.csv" using df_batting.to_csv(). Loading and Processing Batting Summary:
The code opens the "t20_wc_batting_summary.json" file and reads its content into data. A list named all_records is created to store all the batting summary records. The code loops through each record in data, extracts the "battingSummary" from each record, and extends all_records with the extracted data. all_records is used to create a DataFrame called df_batting containing the batting summary data. A new column named "out/not_out" is created in df_batting based on the presence or absence of a value in the "dismissal" column. Unnecessary columns like "dismissal" are dropped using df_batting.drop(). Some data cleaning operations are performed on the "batsmanName" column using df_batting['batsmanName'].apply() and string replacement operations.

Creating a Match ID Dictionary:

A dictionary named match_ids_dict is initialized to store the mapping between team names and their respective match IDs. The code iterates over each row in df_match using df_match.iterrows(). For each row, two keys are created using the team names and match IDs from the row, and these keys are mapped to the respective match IDs in match_ids_dict.

Mapping Match IDs to Batting Summary:

The "match_id" column in df_batting is populated by mapping the "match" column to the match IDs stored in match_ids_dict. Saving Batting Summary to CSV:
The df_batting DataFrame is saved as a CSV file named "temp.csv" using df_batting.to_csv(). Loading and Processing Bowling Summary:
The code opens the "t20_wc_bowling_summary.json" file and reads its content into data. Similar to the batting summary, a list named all_records is created to store all the bowling summary records. The code loops through each record in data, extracts the "bowlingSummary" from each record, and extends all_records with the extracted data. all_records is used to create a DataFrame called df_bowling containing the bowling summary data.

Mapping Match IDs to Bowling Summary:

The "match_id" column in df_bowling is populated by mapping the "match" column to the match IDs stored in match_ids_dict. Saving Bowling Summary to CSV:
The df_bowling DataFrame is saved as a CSV file named "bowling_summary.csv" using df_bowling.to_csv(). Loading and Processing Player Info:
The code opens the "t20_wc_player_info.json" file and reads its content into data. data is used to create a DataFrame named df_players to store player information.

Data Cleaning on Player Names:

Some data cleaning operations are performed on the "name" column in df_players using df_players['name'].apply() and string replacement operations. Saving Player Info to CSV:
The df_players DataFrame is saved as a CSV file named "players_no_images.csv" using df_players.to_csv().


Developed a comprehensive Power BI report leveraging data extraction from espncricinfo via the sophisticated Brightdata website tool. Employing the versatile functionalities of pandas, the extracted data was meticulously cleansed, transformed, and evaluated through an array of player performance metrics. Subsequently, the Power BI dashboard emerged as a valuable resource in discerning the optimal composition of the T20 cricket team, encompassing distinct categories such as openers, middle-order anchors, finishers, all-rounders, and specialist fast bowlers. With the astute selection made via the Power BI dashboard, the team's probability of clinching victory skyrocketed to an impressive 90%.
