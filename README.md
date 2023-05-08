# Classification of winning and losing funds
This project aims to compare the efficiency of four supervised machine learning methods: Classification And Regression Tree, SVM, K-nearest Neighbours and Random Forest in classifying winning and losing funds.
The original dataset is collected from Kaggle through the following link: https://www.kaggle.com/datasets/stefanoleone992/mutual-funds-and-etfs and stored in ETFs.csv. 
The detailed code is stored in SML.ipynb.
I use 21 features to classify the funds:
- investment_type: Fund type, either "blend", "growth" or "value"
- total_net_assets: Total net assets in US dollars
- size_type: Investment category size: “small”, “medium” or “large”
- asset_stocks: Stocks to total assets ratio
- asset_bonds: Bonds to total assets ratio
- fund_price_book_ratio: Ratio of price per share to book value per share
- fund_price_cashflow_ratio: Ratio of price per share to cash flow per share
- fund_price_earning_ratio: Ratio of price per share to earning per share
- fund_price_sales_ratio: Ratio of price per share to sales per share
- Sector weights as percentage: basic materials, consumer cyclical, financial services, real estate, consumer defensive, healthcare, utilities, communication services, energy, industrials, technology (11 features)
In order to categorize the ETF funds, we come up with the following rules:
- If fund_return_1_month is more than or equal mean(fund_return_1_month) + one std.dev(fund_return_1_month), indicating a winning fund
- If fund_return_1_month is less than or equal mean(fund_return_1_month) - one std.dev(fund_return_1_month), indicating a losing fund
- The rest is otherwise
