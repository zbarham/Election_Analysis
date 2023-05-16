# Election Analysis: Overview of the Election Audit

The purpose of this election audit analysis is to ensure the integrity of the election process by providing a detailed report on the election results. This report includes voter turnout for each county, the percentage of votes from each county out of the total count, and the county with the highest turnout. The analysis is based on the election_results.csv file and uses for loops, conditional statements, membership, and logical operators to achieve the desired results. The results are printed to the command line and saved to an election_results.txt file for further examination and documentation.

* Command line output

![Election Audit Results Screenshot](./analysis/Deliverable%201%20Print%20Screenshot%202023-05-13%20111337.png)

# Election Audit Results

The audit produced the following results, code shown to support and explain how I came upon the result where beneficial.

* Total votes cast in this congressional election: 369,711

* County breakdown:
  * Jefferson: 10.5% (38,855)
  * Denver: 82.8% (306,055)
  * Arapahoe: 6.7% (24,801)
```python
for county_name in county_votes:
    # Retrieve the county vote count and calculate the percentage
    votes = county_votes[county_name]
    vote_percentage = float(votes) / float(total_votes) * 100

    county_results = (
        f"{county_name}: {vote_percentage:.1f}% ({votes:,})\n")  # prints each county's vote count and percentage
```
* County with the largest number of votes: Denver
```python
if (votes > county_turnout):
    county_turnout = votes
    largest_county = county_name  # largest_county variable will hold the county with the largest turnout
```

* Candidate breakdown:
  * Charles Casper Stockham: 23.0% (85,213)
  * Diana DeGette: 73.8% (272,892)
  * Raymon Anthony Doane: 3.1% (11,606)
```python
for candidate_name in candidate_votes:
    # Retrieve vote count and percentage
    votes = candidate_votes.get(candidate_name)
    vote_percentage = float(votes) / float(total_votes) * 100

    candidate_results = (
        f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")  # prints each candidate's vote count and percentage
```

* Election winner: Diana DeGette with 272,892 votes and 73.8% of the total votes

# Election Audit Summary

The script developed for this election audit can be easily modified and used for other elections with minimal adjustments. Here are two examples of how this script can be adapted for different elections:

1. Modifying the script for different levels of elections: The script can be modified to accommodate different levels of elections, such as state or local elections. This can be achieved by adjusting the code to read from different data sources (such as different CSV files) and changing the variables to represent different regions (e.g., districts, cities, or states) instead of counties.

2. Adapting the script for elections with multiple positions: In elections where multiple positions are being voted on, the script can be adapted to track votes for each position separately. This can be accomplished by creating additional dictionaries to store vote counts and percentages for each position, and updating the code to loop through each position and calculate the results accordingly.

By making these modifications, the election commission can use this script to audit a wide range of elections, ensuring the transparency and accuracy of the election process.
