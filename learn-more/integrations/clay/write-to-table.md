# Write to Table

{% embed url="https://www.loom.com/share/58192c84df5943b3be1d932b4758726e" %}

There are several integrations in which more than one person can be found per row. In this instance, it may be better to write out this data to a new table. By doing so, you can enrich these profiles and find more information for each individual.

In this tutorial, Matthew goes through a way of doing this without compromising any of the data quality from the original Clay Table; this can be done by implementing our “Write to Table” integration. Here’s how to do it:

Step 1: Create a new table in which you plan on writing your information from the original table. Matthew’s hack for this is to download the other table as a csv, upload it to the new table, and then delete all of the information so you’re left with the columns from the original table.

Step 2: Add the new columns that you want to write so you have columns in which to paste the new information.

Step 3: Find our “Write to Table integration and open it the prompt will ask you for what you want to write to the table, then for the columns that define the attribute you’re writing to.

Step 4: Now, you will need to define each field that you’re mapping to a new column. This will be repeated for each column in your table. You may be asked whether a value is a constant- this is asking whether the value is applicable to each person in your row. For example, if a company has raised $1,500,000 in funding, and your search returned three people from that company, then the $1,500,000 would be a constant because it applies to all three people from that company.

Step 5: When you’ve filled out all of the required and desired boxes, click “Save Changes” and run the integration. When you go to the other table you created, you should notice that all of the fields are filled in now.

We hope this helps, and feel free to reach out to us if you have any questions. Happy prospecting!
