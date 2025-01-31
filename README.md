# DA-graduation-project

## Objectives
**PROJECT NAME: ANALYZE NUTRITIONAL CONTENT AND BUILD A MODEL TO FORECAST CALORIES IN DISHES**
- Analyze the nutrient content in food categories, thereby recognizing the nutritional value of food groups to help build a healthy diet.
- Build a model to predict the calorie content in new dishes.
## Dataset used
[LINK TO DATASET](https://www.kaggle.com/datasets/shrutisaxena/food-nutrition-dataset/)

**Note**: The dataset has been edited by me (spelling errors in column names) and some columns have been removed for ease of analysis.

### Overview of the dataset
This dataset contains data on the nutritional content of many types of food divided into different categories.

**Description of columns:**
- **Category**: the category to which this dish belongs.
- **Description**: a complete description of this dish, including categories and their subcategories (separated by commas, the main category name is written at the beginning).
- **Carbohydrate (in g)**: also known as starch (including sugar and fiber). Carbohydrate is the main source of energy for the body. When entering the body, carbohydrates will be converted into glucose, providing energy for all life activities, from thinking to action.
- **Cholesterol (in mg)**: cholesterol is a structural component of cell membranes, helping to maintain the stability and flexibility of the membrane. It is a raw material for the production of steroid hormones such as cortisol, estrogen, testosterone, which play an important role in the growth, development and reproduction process. When exposed to sunlight, subcutaneous cholesterol is converted into vitamin D, helping the body absorb calcium. Helps the body absorb fat from food.
- **Fiber (in g)**: Fiber helps improve the digestive system, control weight, reduce bad cholesterol, is good for the heart, prevents cancer, and strengthens the immune system.
- **Calorie (calories)**: total calories that foods in this category provide to the body.
- **Manganese (in mg)**: manganese helps strengthen bones, keep the brain healthy, is an antioxidant, has a healthy colon, and regulates blood sugar.
- **Niacin (in mg)**: vitamin B3, helps reduce blood fat, improve blood circulation, support the nervous system, protect the skin, good for the digestive system.
- **Pantothenic Acid (in mg)**: vitamin B5, helps the body convert fat, protein and carbohydrates into energy. It participates in the production of steroid hormones, such as cortisol and testosterone. Helps strengthen the immune system, helping the body fight infections. Has the effect of moisturizing and softening the skin, helping to reduce inflammation and skin irritation. Maintains normal function of the nervous system, reduces stress and fatigue.
- **Protein (in g)**: protein provides energy for the body, transports substances to cells in the body, creates antibodies against diseases, and forms hormones that help regulate metabolism, growth, and reproduction.
- **Retinol (in mcg)**: a form of vitamin A, helps maintain healthy vision, supports the immune system, is good for pregnant women and reproductive health, maintains healthy skin.
- **Riboflavin (in mg)**: vitamin B2, helps convert carbohydrates, proteins and fats into energy, protects eyes from damage caused by strong light and prevents eye diseases such as cataracts, enhances skin health and prevents skin diseases, supports nerve function, improves mood and reduces stress.
- **Selenium (in mcg)**: selenium, boosts immunity, antioxidants, protects the thyroid, anti-aging, improves cardiovascular health.
- **Sugar total (in g)**: the amount of sugar that the dish provides.
- **Thiamin (in mg)**: vitamin B1, helps maintain digestive health, supports heart function by helping maintain a regular heartbeat, is necessary for transmitting nerve impulses, helps maintain healthy brain and nervous system function, converts carbohydrates into glucose, provides energy for daily activities.
- **Monounsaturated Fat (in g)**: monounsaturated fat, a healthy fat commonly found in plants. Reduces bad cholesterol and increases good cholesterol, protects the heart. Reduces inflammation. Improves brain health, prevents Alzheimer's disease.
- **Polyunsaturated Fat (in g)**: polyunsaturated fat, a healthy fat commonly found in fatty fish and seeds, vegetable oils. Helps reduce the risk of cardiovascular disease, improves the brain, reduces inflammation, improves skin health, controls weight, strengthens immunity.
- **Saturated fat (in g)**: saturated fat, a type of fat that is often considered an enemy to health. Often found in dairy products, dishes related to red meat. Increases bad cholesterol, loss of weight control, increases the risk of diabetes and cardiovascular disease.
- **Total lipid (in g)**: total amount of fat provided by the dish.
- **Calcium (in mg)**: calcium, calcium combined with phosphorus to form the structure of bones and teeth. Supports muscle activity. Regulates heart rate. Participates in the blood clotting process, helping the body heal wounds. Helps transmit nerve signals, ensuring normal body functions.
- **Copper (in mg)**: copper, helps the body convert food into energy. Supports the production of hemoglobin, which helps transport oxygen to cells. Maintains the elasticity of arteries and supports heart function. Participates in the production of neurotransmitters, which help transmit nerve signals. Helps maintain bone health. Helps strengthen the immune system, protecting the body from infection. Protects cells from damage caused by free radicals.
- **Iron (in mg)**: iron, helps form red blood cells, provides energy, supports the immune system, and brain development.
- **Magnesium (in mg)**: magnesium, helps regulate nerve activity, strengthens cardiovascular health, bone health, produces energy, and improves muscle function.
- **Phosphorus (in mg)**: phosphorus, combined with calcium, helps strengthen bones and teeth. Is a component of DNA and RNA - molecules that carry genetic information. Is an important component of adenosine triphosphate (ATP), a molecule that provides energy for cell activities. Maintains acid-base balance in the body and participates in the kidney's blood filtration process. Participates in muscle contraction, nerve conduction and enzyme activity.
- **Potassium (in mg)**: potassium, helps regulate the amount of water in and out of cells, maintains stable blood pressure. Maintains a regular and stable heart rate, prevents arrhythmias. Participates in the process of transmitting nerve signals, helping the body respond quickly to stimuli. Helps muscles contract normally, supports daily activities. Helps maintain bone health, prevents osteoporosis.
- **Sodium (in mg)**: sodium, helps regulate the amount of water in and out of cells, helps maintain stable blood pressure. Participates in the process of transmitting nerve signals, helping the body respond quickly to stimuli. Helps muscles contract and relax, supporting daily activities. Helps the body absorb certain nutrients such as glucose.
- **Zinc (in mg)**: zinc, helps strengthen the immune system, helping the body fight bacteria, viruses and other pathogens. Participates in the process of cell division and development, especially important for children during growth. Zinc is necessary for maintaining the sense of taste and smell. Plays an important role in the reproductive process in both men and women. Helps the body increase collagen production, heal wounds, reduce inflammation and protect the skin from the harmful effects of sunlight. Supports brain function, improves memory and learning ability.
- **Vitamin A - RAE (in mcg)**: vitamin A - rae, is essential for maintaining healthy vision, especially in low light conditions. Helps strengthen the immune system, helping the body fight infections. Maintains healthy skin, prevents acne, slows down the aging process of the skin. Helps protect mucous membranes such as the eye mucosa, respiratory tract, digestive tract. Necessary for cell development, especially in children. Plays an important role in the reproductive process in both men and women. - **Vitamin B12 (in mcg)**: vitamin B12 along with folate helps the body produce red blood cells, preventing anemia. Participates in the creation of myelin - a fatty substance that covers and protects nerve cells. Helps convert food into energy, providing energy for daily activities. Reduces the risk of cardiovascular diseases such as stroke, heart attack. Helps improve mood, reduce the risk of depression.
- **Vitamin B6 (in mg)**: vitamin B6, participates in the process of converting nutrients protein, carbohydrates and fat into energy, helping the body function effectively. Helps the body produce hemoglobin - the main component of red blood cells, helping to transport oxygen throughout the body. Participates in the production of neurotransmitters such as serotonin and dopamine, helping to regulate mood, improve sleep and reduce stress. Helps strengthen the immune system, helping the body fight pathogens. Helps maintain healthy skin, shiny hair and strong nails.
- **Vitamin C (in mg)**: helps strengthen the immune system, heal wounds, increase iron absorption, anti-oxidant, reduce the risk of cardiovascular disease, improve skin health, support the nervous system.
- **Vitamin E (in mg)**: helps with anti-oxidation, protects skin, cardiovascular health, supports the nervous system, improves vision, and boosts immunity.
- **Vitamin K (in mcg)**: participates in the blood clotting process, helps blood clot when injured, strengthens bone health, and regulates calcium.

## Key insights

After analyzing the above data set, I have drawn the following insights:
- Groups of cereal dishes, red meat (beef, pork, chicken, ...), candy contain a lot of calories.
- Cereals contain a lot of carbohydrates and sugar, fiber. Candy also contains a lot of sugar.
- Protein and cholesterol are most abundant in red meat dishes.
- Minerals are abundant in red meat, soup, and cereals.
- Meat dishes (beef, pork, lamb, chicken) and candy, cheese are very high in fat.
- B vitamins are most abundant in cereals, red meat.
- Vitamin E is abundant in nuts, cereals.
- Vitamin C is abundant in chili, sour fruits, fruit juices.
- Vitamin K is abundant in spices, green vegetables.
- Vitamin A is abundant in cereals, and red meat.

## Hypothesis based on key insights

From the analysis of correlations, I have the following hypotheses:
- The more sugar and calories a food has, the higher the carbohydrate content.
- The more Niacin a food group contains, the more B vitamins it contains.
- The more calories, the higher the fat content and vice versa.

## Recommendations

- For people who are obese or are losing weight, cutting down on calories and fat (from animals, saturated fat), cholesterol in their meals is very necessary. Eat more green vegetables and vegetable fats.
- For people with high blood sugar, adding fiber, protein, and healthy fats is very good because these substances help stabilize blood sugar. Green vegetables and nuts are recommended dishes.
