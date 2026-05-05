# Analyse des données d'un restaurant de sushi 


## Objectif

Analyser 10 ans de données d'un restaurant de sushi pour identifier les facteurs qui influent sur les revenus et les reviews des clients.

## Données
Le fichier `data_sushi_restaurant.zip` contient les tables Excel utilisées pour cette analyse :
- sushi_orders.csv (83,890 rows — one row per customer order)
order_id — unique order identifier. date, year, month, quarter, day_of_week — when the order was placed. is_weekend and is_holiday — boolean flags for weekend and US public holidays respectively. customer_id — links to sushi_customers.csv. customer_segment — loyalty tier of the customer: regular, occasional, or one_time. is_local — whether the customer is from the local neighbourhood. channel — how the order was fulfilled: dine_in, takeaway, or delivery. party_size — number of diners in the group. revenue — total food and drink revenue before discounts (USD). cogs — raw ingredient cost for the order (USD). gross_profit — revenue minus cogs. discount — promotional discount applied if any (USD). tip — gratuity left by the customer, dine_in orders only (USD). delivery_fee — platform fee charged on delivery orders (USD). total_collected — actual cash collected: revenue minus discount plus tip plus delivery fee. rating — star rating left by the customer (1–5), NaN if no review was submitted.

- sushi_order_items.csv (998,920 rows — one row per line item within each order)
order_id — links to sushi_orders.csv. date — date of the parent order. item — menu item name. category — item category: nigiri, roll, sashimi, omakase, side, drink, or dessert. unit_price — price charged on that date, inflation-adjusted annually (USD). cogs — ingredient cost for this specific item (USD). gross_profit — unit_price minus cogs.

- sushi_daily_pnl.csv (3,652 rows — one row per calendar day)
date, year, month, quarter, day_of_week — calendar identifiers. is_weekend and is_holiday — boolean flags. covers — total number of customers served that day. gross_revenue — total revenue across all orders that day (USD). cogs — total ingredient cost that day (USD). gross_profit — gross_revenue minus cogs. labour_cost — total staff wages paid that day, scales with cover count (USD). fixed_ops_cost — daily share of fixed costs including rent, utilities, insurance, POS software, and supplies (USD). operating_profit — gross_profit minus labour_cost minus fixed_ops_cost — the bottom line (USD). gp_margin_pct — gross profit as a percentage of revenue.

- sushi_customers.csv (1,800 rows — one row per unique customer)
customer_id — unique identifier. segment — loyalty tier: regular customers visit frequently, occasional customers visit periodically, one_time customers visited only once. drinks_alcohol — whether the customer typically orders alcoholic drinks. is_local — whether the customer lives in the local neighbourhood. joined_date — date the customer first appeared, with the earliest 5% assigned as founding regulars from opening day.

- sushi_reviews.csv (15,146 rows — approximately 18% of orders received a review)
order_id — links to sushi_orders.csv. date — date the review was submitted. rating — star rating from 1 to 5. channel — the channel of the reviewed order: dine_in, takeaway, or delivery. year — year the review was submitted.

- sushi_staff.csv (11 rows — one row per staff member hired over the 10 years)
role — job title: Head Chef, Sous Chef, Sushi Chef, Server, Delivery Driver, or Manager. base_hourly_rate_2015 — hourly wage at time of hire in 2015 USD, with actual pay compounding at 2.5% annually. hire_date — date the staff member joined. termination_date — date the staff member left, or None if still employed at end of 2024.

## Visualisation des tables de données via SQL Design
![Visualisation des tables de données](Visualisation%20des%20tables%20de%20donn%C3%A9es.png)

## Key Insights

## SQL Queries
Vue d’ensemble de l’analyse :

1. Performance globale :
Analyse du chiffre d’affaires et du profit  ,
Évolution dans le temps (mensuelle, annuelle),
Identification des périodes de forte activité

2. Analyse clients :
Segmentation des clients,
Panier moyen,
Comparaison clients locaux / non locaux

3. Analyse produits :
Produits les plus vendus,
Produits les plus rentables,
Identification des produits peu performants

4. Satisfaction client :
Analyse des notes et avis,
Impact des évaluations sur le chiffre d’affaires

5. Analyse de la rentabilité :
Marges,
Impact des remises,
Analyse des coûts,

L’ensemble des requêtes utilisées est disponible dans le dossier /sql.

## Dashboard
(lien à venir)



