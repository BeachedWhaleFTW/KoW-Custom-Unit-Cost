# KoW-Custom-Unit-Cost
This project aims to estimate the cost of a custom Kings of War unit given a set of unit stats. The exact format of how this will be done is TBD. The intent is to add units to existing armies and not create new armies.

## Current Goals
The current goals for the project are to import the existing KoW armies in as .csv files.  The "Undead Armies.csv" has been uploaded as an example of how the data should be structured.  Once the .csv files are in place, the data will be parsed and structured in a way such that a multiple linear regression analysis can be performed.  The data will ideally be split into a training group as well as a testing group in order to evaluate fitness.

## Future Goals
Assuming the model achieves an acceptable fitness value (criterion TBD), a simple interface should be built in the form of a web application to allow users to input stats for custom units and output an associated cost.  Ideally, there would be a database to store custom units and allow users to retrieve or view community content, but this feature will depend primarily on adoption rates.

## Help Needed
Given the current goals, the main help needed revolves around importing/creating army .csv files.  Accuracy of the stats as well as format is key as the code that imports the .csv files depends on sameness across each file.

## .csv Formatting Notes
A couple of notes when formatting the .csv files:
- leave off '+' values (for example: Regeneration (5+) turns to Regeneration (5))
- any values of '-' should turn to 0
- any 'Inspiring(unit_type)' should input as just 'Inspiring'
- unique or legendary units should input as 'Unit Name [1]'
- special traits should be separated by ';' delimiters and all other values ','
- random values such as D6+2 should be added as their expected value. D6 expected value is 3.5 so "Blast (D6+2)" would be "Blast (5.5)"
- values that reference other values such as "Breath Attack(att)" should include the numerical value of the 'att' instead of reference.

If any other oddities appear, feel free to drop a note of how it was handled so it can be added to this section for future reference
