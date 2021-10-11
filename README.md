# election-analysis
BootCamp Practice repository for Python.

## Overview of Election Audit: 


> In this module we explore the capabilities of python by applying them on helping Tom on the US Concretional Pressing Colorado Elections. 



#### The purpose of this election audit analysis is based on obtaining the following information. 
- ##### Total of Votes
> First we have to import the csv file to python by using the propper code.
````

# Initialize a total vote counter.
total_votes = 0

# Candidate Options and candidate votes.
candidate_options = []
candidate_votes = {}

# 1: Create a county list and county votes dictionary.

county_list = []
county_votes_dictionary = {}


# Read the csv and convert it into a list of dictionaries
with open(file_to_load) as election_data:
    reader = csv.reader(election_data)

    # Read the header
    header = next(reader)

    # For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        
# Save the results to our text file.
with open(file_to_save, "w") as txt_file:

    # Print the final vote count (to terminal)
    election_results = (
        f"\nElection Results\n"
        f"---(⌐■_■)---------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")
    #print(election_results)

````

- #### Total of votes for each candidate, the percentage of each candidate and the winner 

> First we have to import the csv file to python by using the propper code.

````

# Candidate Options and candidate votes.
candidate_options = []
candidate_votes = {}

# 1: Create a county list and county votes dictionary.

county_list = []
county_votes_dictionary = {}

# Track the winning candidate, vote count and percentage
winning_candidate = ""
winning_count = 0
winning_percentage = 0

# Read the csv and convert it into a list of dictionaries
with open(file_to_load) as election_data:
    reader = csv.reader(election_data)

    # Read the header
    header = next(reader)

    # For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row[1]

        # If the candidate does not match any existing candidate add it to
        # the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1
        
        
    # Save the final candidate vote count to the text file.
    for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
        f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

        # Print each candidate's voter count and percentage to the
        # terminal.
        print(candidate_results)

        # Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

    # Print the winning candidate (to terminal)

    winning_candidate_summary = (
        f"\nWinning Candidate Summary\n"
        f"--------------------------\n"
        f"----ヘ( ^o^)ノ＼(^_^ )----\n"
        f"--------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
    print(winning_candidate_summary)
````




## Election-Audit Results: 

### How many votes were cast in this congressional election?
   <img width="400" alt="electioon-results" src="https://user-images.githubusercontent.com/37987602/136725356-b6b0ae1d-7f8a-48b1-95d1-7f17546dc562.png">

### Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.
  #### County Votes:
  
  <img width="400" alt="county-votes" src="https://user-images.githubusercontent.com/37987602/136725462-03326986-a5b9-4059-ac55-53bf090e147c.png">

### Which county had the largest number of votes?
  <img width="400" alt="largest-county" src="https://user-images.githubusercontent.com/37987602/136725560-1a6f69ab-fa77-45ae-b928-61fad0961a93.png">

### Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.
  <img width="400" alt="total-votes-each-candidate" src="https://user-images.githubusercontent.com/37987602/136725582-6d7c8126-7f4d-4cb0-bc6e-81851ec14b33.png">


### Which candidate won the election, what was their vote count, and what was their percentage of the total votes?
  <img width="231" alt="winner-candidate" src="https://user-images.githubusercontent.com/37987602/136725637-2c03ef83-caa7-45ee-ab1e-082f812abd8d.png">


## Election-Audit Summary: 

### Business Proposal 

This election analysis serves as an example of the capabilities of the python script put together with the team effort between your employee Tom and Jorge Solis. We can appreciate that the script was able to evaluate more than 300,000 votes for a whole Pressing in seconds. This will allow an efficient audit analysis for more elections. As it can be appreciated in the images from our code, we can apply this to more states and replicate the report or create a new one by adding information. 

Please feel free to contact us for more information. 

It was a pleasure working you. 

We Love Voting!! 

｡^‿^｡

