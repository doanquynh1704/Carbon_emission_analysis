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

SELECT *
FROM product_emissions
LIMIT 10;

***Bảng industry_groups***

SELECT *
FROM industry_groups
LIMIT 10;

***Bảng companies***

SELECT *
FROM companies
LIMIT 10;

***Bảng countries***

SELECT *
FROM countries
LIMIT 10;

***Data Structure***
![https://lms.swisscoding.edu.vn/course/view.php?id=80&section=114](https://github.com/doanquynh1704/Carbon_emission_analysis/blob/main/Database%20diagram.png)
