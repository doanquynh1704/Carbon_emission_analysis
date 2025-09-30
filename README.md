# Carbon_emission_analysis
![https://youmatter.world/en/category-environment/greenhouse-gases-co2-decarbonizing-28439/](https://github.com/doanquynh1704/Carbon_emission_analysis/blob/main/greenhouse-co2-climate.jpg)
Source:https://youmatter.world/en/category-environment/greenhouse-gases-co2-decarbonizing-28439/
### Mô tả nhiệm vụ
Báo cáo này nhằm mục đích phân tích lượng khí thải carbon để kiểm tra dấu chân carbon trên nhiều ngành công nghiệp khác nhau. Thông qua phân tích này, chúng ta hy vọng sẽ hiểu rõ hơn về tác động môi trường của các ngành công nghiệp khác nhau và đóng góp vào việc đưa ra các quyết định sáng suốt trong phát triển bền vững. Các câu hỏi cần trả lười như sau:
<ol><li> Những sản phẩm nào đóng góp nhiều nhất vào lượng khí thải carbon?
<li> Các nhóm ngành của những sản phẩm này là gì?
<li>Những ngành nào có đóng góp cao nhất vào lượng khí thải carbon?
<li>Những công ty nào có đóng góp cao nhất vào lượng khí thải carbon?
<li>Những quốc gia nào có đóng góp cao nhất vào lượng khí thải carbon?
<li>Xu hướng của dấu chân carbon (PCFs) qua các năm là gì?
<li>Nhóm ngành nào đã thể hiện sự giảm đáng kể nhất về dấu chân carbon (PCFs) theo thời gian?

### Các bảng dữ liệu
***Bảng product_emissions***
```sql
SELECT * 
FROM product_emissions
LIMIT 10;
```
|id|company_id|country_id|industry_group_id|year|product_name|weight_kg|carbon_footprint_pcf|upstream_percent_total_pcf|operations_percent_total_pcf|downstream_percent_total_pcf|
|--|----------|----------|-----------------|----|------------|---------|--------------------|--------------------------|----------------------------|----------------------------|
|10056-1-2014|82|28|2|2014|Frosted Flakes(R) Cereal|0.7485|2|57.50|30.00|12.50|
|10056-1-2015|82|28|15|2015|"Frosted Flakes, 23 oz, produced in Lancaster, PA (one carton)"|0.7485|2|57.50|30.00|12.50|
|10222-1-2013|83|28|8|2013|Office Chair|20.68|73|80.63|17.36|2.01|
|10261-1-2017|14|16|25|2017|Multifunction Printers|110.0|1488|30.65|5.51|63.84|
|10261-2-2017|14|16|25|2017|Multifunction Printers|110.0|1818|25.08|4.51|70.41|
|10261-3-2017|14|16|25|2017|Multifunction Printers|110.0|2274|20.05|3.61|76.34|
|10324-1-2016|15|16|19|2016|KURALON  fiber|1500.0|10000|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|
|10418-1-2013|84|9|19|2013|Portland Cement|1000.0|1102|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|
|10661-10-2014|85|28|11|2014|Regular Straight 505® Jeans – Steel (Water<Less™)|0.7665|15|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|
|10661-10-2015|85|28|6|2015|Regular Straight 505® Jeans – Steel (Water<Less™)|0.7665|15|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|N/a (product with insufficient stage-level data)|


***Bảng industry_groups***
```sql
SELECT *
FROM industry_groups
LIMIT 10;
```
|id|industry_group|
|--|--------------|
|1|"Consumer Durables, Household and Personal Products"|
|2|"Food, Beverage & Tobacco"|
|3|"Forest and Paper Products - Forestry, Timber, Pulp and Paper, Rubber"|
|4|"Mining - Iron, Aluminum, Other Metals"|
|5|"Pharmaceuticals, Biotechnology & Life Sciences"|
|6|"Textiles, Apparel, Footwear and Luxury Goods"|
|7|Automobiles & Components|
|8|Capital Goods|
|9|Chemicals|
|10|Commercial & Professional Services|

***Bảng companies***
```sql
SELECT *
FROM companies
LIMIT 10;
```
|id|company_name|
|--|------------|
|1|"Autodesk, Inc."|
|2|"Casio Computer Co., Ltd."|
|3|"Cisco Systems, Inc."|
|4|"CNX Coal Resources, LP"|
|5|"Coca-Cola Enterprises, Inc."|
|6|"Compañía Española de Petróleos, S.A.U. CEPSA"|
|7|"Daikin Industries, Ltd."|
|8|"Elitegroup computer systems co., Ltd."|
|9|"Fuji Xerox Co., Ltd."|
|10|"Gamesa Corporación Tecnológica, S.A."|

***Bảng countries***
```sql
SELECT *
FROM countries
LIMIT 10;
```
|id|country_name|
|--|------------|
|1|Australia|
|2|Belgium|
|3|Brazil|
|4|Canada|
|5|Chile|
|6|China|
|7|Colombia|
|8|Finland|
|9|France|
|10|Germany|

***Data Structure***
![https://lms.swisscoding.edu.vn/course/view.php?id=80&section=114](https://github.com/doanquynh1704/Carbon_emission_analysis/blob/main/Database%20diagram.png)

### Kết quả phân tích
##### Những sản phẩm nào đóng góp nhiều nhất vào lượng khí thải carbon? 
Top 10 sản phẩm có tổng lượng PCF cao nhất
```sql
SELECT 
         product_name, 
         SUM(carbon_footprint_pcf) AS 'Total PCF'
FROM product_emissions
GROUP BY 
          product_name
ORDER BY 
           SUM(carbon_footprint_pcf) DESC
LIMIT 10;
```
|product_name|Total PCF|
|------------|---------|
|Wind Turbine G128 5 Megawats|3718044|
|Wind Turbine G132 5 Megawats|3276187|
|Wind Turbine G114 2 Megawats|1532608|
|Wind Turbine G90 2 Megawats|1251625|
|TCDE|198150|
|Land Cruiser Prado. FJ Cruiser. Dyna trucks. Toyoace.IMV def unit.|191687|
|Retaining wall structure with a main wall (sheet pile): 136 tonnes of steel sheet piles and 4 tonnes of tierods per 100 meter wall|167000|
|Electric Motor|160655|
|Audi A6|111282|
|Average of all GM vehicles produced and used in the 10 year life-cycle.|100621|
