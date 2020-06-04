# EDEN Protocol - 2020 Pilot Example:

## A simple example:

### SETTING UP A PROFILE:

- Profile Step 1.1: A farmer generates a new identity on the network. "peerID=123"

- Profile Step 1.2: The farmer creates a claim to a farm name: "Farmer Brown"

- Profile Step 1.3: The farmer creates a claim to a farm location: "41.120278, -114.968056"

- Profile Step 1.4: The farmer creates a claim to a farm practice: "Organic farming only"

- Profile Step 1.5: The farmer associates all 3 claims to his farm's network identity.
              <br> Peers inquiring about this farm ID on the network will be able to view all 3 notarized claims.

- Profile Step 1.6: The farmer creates an evidence transaction pointing to usda.gov organic certification status.

- Profile Step 1.7: The farmer associates the "Organic farming only" claim with the "usda.gov" evidence record.

### CREATING A PRODUCT BATCH HISTORY:

- Product Step 2.1: The farmer creates a new product batch history on the network. "batchID=ABC"

- Product Step 2.2: The farmer associates the new batch history ID to his farm identity.
               <br> This automatically relates the farm's claims and evidence to the product batch.

- Product Step 2.3: The farmer creates a new claim for the product name: "OG Delicious"

- Product Step 2.4: The farmer creates a new claim for the product quality: "No mold or additives"

- Product Step 2.5: The farmer transfers control of the product batch history to next partner on the chain.

- Product Step 2.6: The farmer creates a new claim for the product status: "shipped"

- Product Step 2.7: The farmer associates the product batch history transfer of control transaction as evidence to product status change.

- Product Step 2.8: The farmer subscribe to notifications of product history updates .

### VALIDATING WITH EVIDENCE:

(we assume here that a lab went through the profile creation process)

- Lab Step 3.1: The lab network ID receives product batch history control from the farmer.

- Lab Step 3.2: The lab creates a new claim for the product status: "received"

- Lab Step 3.3: The lab performs product analysis and creates a new claim for the product: "no additives found"

- Lab Step 3.4: The lab creates a new evidence record: "chemical analysis result file"

- Lab Step 3.5: The lab associates the "no additives found" claim to the "chemical analysis" evidence.

### END USER VALIDATION:

- User Step 4.1: A user purchases a product. The product batch history id is delivered as an insert with the product.
            <br> (we need to define how the batch ID will be inserted with the product packaging)

- User Step 4.2: The user scans the batch ID with a smart phone application.

- User Step 4.3: The scan brings-up a timeline showing recorded supply chain information from farmer and lab.
            <br> At this point, the user is able to explore claims and evidence to make their own assessment of product quality.

- User Step 4.4: The user creates a new claim for the product batch history: "great stuff!"

### ANALYTICS:

- Analyst Step 5.1: An outside observer can look at transactions repeated over time and discover patterns and reputations across the supply chain

- Analyst Step 5.2: Quality brands (like our farmer and lab) will publish their EDEN network identity on their websites.
               <br> This will demonstrate their good standing and sustained delivery of quality products for future customers.
