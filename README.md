# DA-project

## Mục tiêu
**PROJECT NAME: PHÂN TÍCH HÀM LƯỢNG DINH DƯỠNG VÀ XÂY DỰNG MÔ HÌNH DỰ BÁO LƯỢNG CALO CÓ TRONG CÁC MÓN ĂN**
- Phân tích hàm lượng các chất dinh dưỡng có trong các danh mục món ăn, từ đó nhận ra giá trị dinh dưỡng của các nhóm món ăn giúp xây dựng một chế độ ăn uống lành mạnh.
- Xây dựng mô hình dự báo dự báo hàm lượng calo có trong các món ăn mới.
## Dataset sử dụng
[LINK TO DATASET](https://www.kaggle.com/datasets/shrutisaxena/food-nutrition-dataset/)

**Lưu ý**: dataset đã được tôi chỉnh sửa (các lỗi chính tả ở tên cột) và xoá bớt một vài cột để thuận tiện trong quá trình phân tích.
### Tổng quan dataset
Dataset này chứa dữ liệu về hàm lượng dinh dưỡng của nhiều loại thực phẩm được phân thành nhiều danh mục khác nhau.

**Mô tả các cột:** 

- **Category**: danh mục mà món ăn này thuộc về.
- **Description**: mô tả đầy đủ về món ăn này, bao gồm danh mục và danh mục phụ của chúng (được ngăn cách bởi dấu phẩy, tên danh mục chính được viết ở đầu).
- **Carbohydrate (tính bằng g)**: hay còn gọi là đường bột (gồm đường và chất xơ). Carbohydrate là nguồn năng lượng chính cho cơ thể. Khi vào cơ thể, carbohydrate sẽ được chuyển hóa thành glucose, cung cấp năng lượng cho mọi hoạt động sống, từ suy nghĩ đến hành động.
- **Cholesterol (tính bằng mg)**: cholesterol là thành phần cấu trúc của màng tế bào, giúp duy trì tính ổn định và linh hoạt của màng. Là nguyên liệu để sản xuất các hormone steroid như cortisol, estrogen, testosterone, đóng vai trò quan trọng trong quá trình sinh trưởng, phát triển và sinh sản. Cholesterol dưới da khi tiếp xúc với ánh nắng mặt trời sẽ được chuyển hóa thành vitamin D, giúp cơ thể hấp thu canxi. Giúp cơ thể hấp thụ chất béo từ thức ăn.
- **Fiber (tính bằng g)**: chất xơ giúp cải thiện hệ tiêu hoá, kiểm soát cân nặng, giảm lượng cholesterol xấu, tốt cho tim mạch, ngăn ngừa ung thư, tăng cường miễn dịch. 
- **Calorie (calo)**: tổng lượng calo mà món ăn thuộc danh mục này cung cấp cho cơ thể. 
- **Manganese (tính bằng mg)**: mangan giúp xương chắc khoẻ, não bộ khoẻ mạnh, chống oxy hoá, đại tràng khoẻ mạnh, điều hoà đường huyết.
- **Niacin (tính bằng mg)**: vitamin B3, giúp giảm mỡ máu, cải thiện lưu thông máu, hỗ trợ hệ thần kinh, bảo vệ da, tốt cho hệ tiêu hoá.
- **Pantothenic Acid (tính bằng mg)**: vitamin B5, giúp cơ thể chuyển hóa chất béo, protein và carbohydrate thành năng lượng. Nó tham gia vào quá trình sản xuất các hormone steroid, như cortisol và testosterone. Giúp tăng cường hệ miễn dịch, giúp cơ thể chống lại nhiễm trùng. Có tác dụng dưỡng ẩm và làm mềm da, giúp giảm viêm và kích ứng da. Duy trì chức năng bình thường của hệ thần kinh, giảm căng thẳng và mệt mỏi.
- **Protein (tính bằng g)**: protein cung cấp năng lượng cho cơ thể, vận chuyển các chất đến các tế bào trong cơ thể, tạo nên kháng thể chống lại bệnh tật, cấu tạo nên các hormone giúp điều hoà quá trình trao đổi chất, tăng trưởng, sinh sản. 
- **Retinol (tính bằng mcg)**: một dạng vitamin A, giúp duy trì sức khoẻ thị giác, hỗ trợ hệ miễn dịch, tốt cho phụ nữ đang mang thai và sức khoẻ sinh sản, duy trì làn da khoẻ mạnh.
- **Riboflavin (tính bằng mg)**: vitamin B2, giúp chuyển hoá carbohydrate, protein và chất béo thành năng lượng, bảo vệ mắt khỏi các tổn thương do ánh sáng mạnh và ngăn ngừa các bệnh về mắt như đục thủy tinh thể, tăng cường sức khoẻ của da và ngăn bệnh về da, hỗ trợ hễ thần kinh, cải thiện tâm trạng và giảm stress.
- **Selenium (tính bằng mcg)**: selen, tăng cường miễn dịch, chống oxy hoá, bảo vệ tuyến giáp, chống lão hoá, cải thiện sức khoẻ tim mạch.
- **Sugar total (tính bằng g)**: lượng đường mà món ăn cung cấp.
- **Thiamin (tính bằng mg)**: vitamin B1, giúp duy trì sức khỏe đường tiêu hóa, hỗ trợ chức năng tim bằng cách giúp duy trì nhịp tim đều đặn, cần thiết cho việc truyền các xung thần kinh, giúp duy trì chức năng não bộ và hệ thần kinh khỏe mạnh, chuyển hóa carbohydrate thành glucose, cung cấp năng lượng cho các hoạt động hàng ngày.
- **Monounsaturated Fat (tính bằng g)**: chất béo không bão hoà đơn, một loại chất béo lành mạnh thường thấy ở thực vật. Giảm lượng cholesterol xấu và tăng lượng cholesterol tốt, bảo vệ tim mạch. Giảm viêm. Cải thiện sức khoẻ não bộ, ngăn bệnh Alzheimer.
- **Polyunsaturated Fat (tính bằng g)**: chất béo không bão hoà đa, là một chất béo lành mạnh thường thấy ở các loài cá béo và hạt, dầu thực vật. Giúp giảm nguy cơ bệnh tim mạch, cải thiện não bộ, giảm viêm, cải thiện sức khoẻ da, kiểm soát cân nặng, tăng cường miễn dịch.
- **Saturated fat (tính bằng g)**: chất béo bão hoà, một loại chất béo thường được xem là kẻ thù đối với sức khoẻ. Thường thấy ở các sản phẩm làm từ sữa, các món ăn liên quan đến thịt đỏ. Làm tăng lượng cholesterol xấu, mất kiểm soát cân nặng, tăng nguy cơ mắc bệnh tiểu đường và tim mạch.
- **Total lipid (tính bằng g)**: tổng lượng chất béo mà món ăn cung cấp.
- **Calcium (tính bằng mg)**: canxi, canxi kết hợp với photpho tạo nên cấu trúc xương và răng. Hỗ trợ hoạt động của cơ bắp. Điều hòa nhịp tim. Tham gia vào quá trình đông máu, giúp cơ thể hàn gắn vết thương. Giúp truyền các tín hiệu thần kinh, đảm bảo các hoạt động của cơ thể diễn ra bình thường.
- **Copper (tính bằng mg)**: đồng, giúp cơ thể chuyển hóa thức ăn thành năng lượng. Hỗ trợ quá trình sản xuất hemoglobin, giúp vận chuyển oxy đến các tế bào. Duy trì tính đàn hồi của động mạch và hỗ trợ chức năng tim. Tham gia vào việc sản xuất các chất dẫn truyền thần kinh, giúp truyền tín hiệu thần kinh. Giúp duy trì sức khỏe của xương. Giúp tăng cường hệ miễn dịch, bảo vệ cơ thể khỏi nhiễm trùng. Bảo vệ tế bào khỏi tổn thương do gốc tự do gây ra.
- **Iron (tính bằng mg)**: sắt, giúp hình thành hồng cầu, cung cấp năng lượng, hỗ trợ hệ miễn dịch, phát triển não bộ.
- **Magnesium (tính bằng mg)**: magie, giúp điều hoà hoạt động thần kinh, tăng cường sức khoẻ tim mạch, sức khoẻ xương, sản xuất năng lượng, cải thiện chức năng cơ bắp.
- **Phosphorus (tính bằng mg)**: phốt pho, kết hợp với canxi giúp xương và răng chắc khoẻ. Là thành phần cấu tạo nên DNA và RNA – những phân tử mang thông tin di truyền. Là một thành phần quan trọng của adenosine triphosphate (ATP), phân tử cung cấp năng lượng cho các hoạt động của tế bào. Duy trì cân bằng axit-base trong cơ thể và tham gia vào quá trình lọc máu của thận. Tham gia vào quá trình co cơ, dẫn truyền thần kinh và hoạt động của các enzyme.
- **Potassium (tính bằng mg)**: kali, giúp điều hòa lượng nước trong tế bào và ngoài tế bào, duy trì huyết áp ổn định. Duy trì nhịp tim đều đặn và ổn định, ngăn ngừa rối loạn nhịp tim. Tham gia vào quá trình truyền dẫn tín hiệu thần kinh, giúp cơ thể phản ứng nhanh với các kích thích. Giúp cơ bắp co giãn bình thường, hỗ trợ các hoạt động hàng ngày. Giúp duy trì sức khỏe của xương, ngăn ngừa loãng xương.
- **Sodium (tính bằng mg)**: natri, giúp điều hòa lượng nước trong và ngoài tế bào, giúp duy trì huyết áp ổn định. Tham gia vào quá trình truyền dẫn tín hiệu thần kinh, giúp cơ thể phản ứng nhanh với các kích thích. Giúp cơ bắp co giãn, hỗ trợ các hoạt động hàng ngày. Giúp cơ thể hấp thu một số chất dinh dưỡng như glucose.
- **Zinc (tính bằng mg)**: kẽm, giúp tăng cường hệ miễn dịch, giúp cơ thể chống lại các vi khuẩn, virus và các tác nhân gây bệnh khác. Tham gia vào quá trình phân chia và phát triển tế bào, đặc biệt quan trọng đối với trẻ em trong giai đoạn tăng trưởng. Kẽm cần thiết cho việc duy trì cảm giác ở vị giác và khướu giác. Đóng vai trò quan trọng trong quá trình sinh sản ở cả nam và nữ. Giúp cơ thể tăng cường sản sinh collagen, làm lành các vết thương, giảm viêm và bảo vệ da khỏi tác hại của ánh nắng mặt trời. Hỗ trợ chức năng não bộ, cải thiện trí nhớ và khả năng học tập.
- **Vitamin A - RAE (tính bằng mcg)**: vitamin A - rae, rất cần thiết cho việc duy trì thị lực khỏe mạnh, đặc biệt là trong điều kiện ánh sáng yếu. Giúp tăng cường hệ miễn dịch, giúp cơ thể chống lại các bệnh nhiễm trùng. Duy trì làn da khỏe mạnh, ngăn ngừa mụn trứng cá, làm chậm quá trình lão hóa da. Giúp bảo vệ các niêm mạc như niêm mạc mắt, đường hô hấp, đường tiêu hóa. Cần thiết cho sự phát triển của tế bào, đặc biệt là ở trẻ em. Đóng vai trò quan trọng trong quá trình sinh sản ở cả nam và nữ.
- **Vitamin B12 (tính bằng mcg)**: vitamin B12 cùng với folate giúp cơ thể sản xuất hồng cầu, ngăn ngừa thiếu máu. Tham gia vào việc tạo ra myelin – một chất béo bao bọc và bảo vệ các tế bào thần kinh. Giúp chuyển hóa thức ăn thành năng lượng, cung cấp năng lượng cho các hoạt động hàng ngày. Giảm nguy cơ mắc các bệnh tim mạch như đột quỵ, đau tim. Giúp cải thiện tâm trạng, giảm nguy cơ trầm cảm.
- **Vitamin B6 (tính bằng mg)**: vitamin B6, tham gia vào quá trình chuyển hóa các chất dinh dưỡng protein, carbohydrate và chất béo thành năng lượng, giúp cơ thể hoạt động hiệu quả. Giúp cơ thể sản xuất hemoglobin - thành phần chính của hồng cầu, giúp vận chuyển oxy đi khắp cơ thể. Tham gia vào việc sản xuất các chất dẫn truyền thần kinh như serotonin và dopamine, giúp điều hòa tâm trạng, cải thiện giấc ngủ và giảm căng thẳng. Giúp tăng cường hệ miễn dịch, giúp cơ thể chống lại các tác nhân gây bệnh. Giúp duy trì làn da khỏe mạnh, tóc bóng mượt và móng chắc khỏe.
- **Vitamin C (tính bằng mg)**: giúp tăng cường hệ miễn dịch, chữa lành vết thương, tăng cường khả năng hấp thụ sắt, chống oxy hoá, giảm nguy cơ mắc bệnh tim mạch, cải thiện sức khoẻ da, hỗ trợ hệ thần kinh.
- **Vitamin E (tính bằng mg)**: giúp chống oxy hoá, bảo vệ da, sức khoẻ tim mạch, hỗ trợ hệ thần kinh, cải thiện thị lực, tăng cường miễn dịch.
- **Vitamin K (tính bằng mcg)**: tham gia vào quá trình đông máu, giúp máu đông lại khi bị thương, tăng cường sức khoẻ xương, điều hoà canxi.  

## Key insights

Sau khi phân tích tập dữ liệu trên, tôi đã rút ra được các insight sau:

- Nhóm các món ăn ngũ cốc, thịt đỏ (bò, heo, gà, ...), kẹo chứa rất nhiều calo.
- Ngũ cốc chứa rất nhiều carbohydrate và lượng đường, chất xơ. Bánh kẹo cũng chứa rất nhiều đường.
- Protein và cholesterol chứa nhiều nhất trong các món thịt đỏ.
- Khoáng chất có nhiều trong các loại thịt đỏ, soup, và ngũ cốc.
- Các món thịt (bò, heo, cừu, gà) và các món bánh kẹo, phomai rất nhiều chất béo.
- Vitamin nhóm B được tìm thấy nhiều nhất ở ngũ cốc, thịt đỏ.
- Vitamin E chứa nhiều trong các loại hạt, ngũ cốc.
- Vitamin C chứa nhiều trong ớt, trái cây có vị chua, nước trái cây.
- Vitamin K chứa nhiều trong các loại gia vị, rau xanh.
- Vitamin A có nhiều trong các loại ngũ cốc, và thịt đỏ.

## Giả thuyết dựa trên các key insights

Từ các phân tích về mối tương quan, tôi có một số giả thuyết sau: 

- Thức ăn càng nhiều đường và calo thì lượng carbohydrate rất cao.
- Nhóm các thức ăn chứa càng nhiều Niacin thì càng nhiều các vitamin nhóm B.
- Càng nhiều calo thì lượng chất béo càng cao và ngược lại. 

## Recommendations
- Đối với những người bị béo phì hoặc đang giảm cân, thì việc cắt giảm lượng calo và chất béo (từ động vật, chất béo bão hoà), cholesterol trong các món ăn là rất cần thiết. Nên ăn nhiều rau xanh và chất béo thực vật.
- Đối với những người có đường huyết cao thì việc bổ xung chất xơ, protein, chất béo lành mạnh là rất tốt vì các chất này giúp ổn định đường huyết. Rau xanh và các loại hạt là các món ăn đề xuất.
