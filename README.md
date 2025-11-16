Housing Price Analysis and Deal Classifier (Venn Diagram)

This Python script performs a set theory analysis on a dataset of housing properties to calculate the average price based on a combination of features (square footage, number of rooms, and parking availability). It visualizes these average prices using a 3-set Venn diagram and provides an interactive tool to classify a new user-input house as a "Deal" or "No Deal" based on its category's average price.

🌟 Features

Data Classification: Automatically classifies each house into one of the eight Venn diagram categories (bitstreams) based on defined criteria.

Average Price Calculation: Calculates the average price for all houses belonging to each unique combination of features.

Venn Diagram Visualization: Generates a 3-set Venn diagram displaying the average price within each intersection and non-intersection region.

Interactive Deal Finder: Prompts the user for a new house's details and determines if its asking price is below the calculated average for its specific category (classified as a "Deal").

⚙️ Requirements

This project requires Python and the following libraries:

matplotlib (for plotting and displaying the diagram)

matplotlib-venn (for generating the specialized 3-set Venn diagram)

You can install them using pip:

pip install matplotlib matplotlib-venn


🧠 Core Logic: Bitstream Classification

The script uses three criteria to classify each house, resulting in a 3-digit bitstream (e.g., '101', '010', '111'). The position of the '1' or '0' corresponds to the inclusion or exclusion from the following sets:

Set

Bitstream Position

Criterion (1 = Yes, 0 = No)

A

1st digit

sqft (Square Footage) $> 2000$

B

2nd digit

rooms (Number of Rooms) $> 2$

C

3rd digit

parking (Has Parking) $> 0$

Bitstream Examples

Bitstream

Interpretation

Venn Region

111

A and B and C

Intersection of all three

100

A only

In set A, but outside B and C

011

B and C, not A

Intersection of B and C, outside A

000

None

Outside all three sets (The Universe)

The calculated average price for each bitstream (e.g., avgPrice101) is then displayed in the corresponding section of the Venn diagram.

💡 Deal or No Deal Logic

After calculating all category averages, the script loops to receive new house data from the user.

The user's house is classified into one of the eight bitstream categories.

The user's house price is compared to the avgPriceXXX for that specific category.

If the user's house price is less than the category average price, it is labeled a "Deal."

Otherwise, it is labeled a "No Deal."

▶️ How to Run

Ensure you have met the requirements listed above.

Save the code as a Python file (e.g., house_predictor.py).

Run the script from your terminal:

python house_predictor.py


The script will immediately display the Venn diagram and then prompt you in the console to input the details of a test house.
