# Redux

## Khái niệm

- Redux là một predictable state manager tool cho các ứng dụng js.
- Nó giúp các ứng dụng hoạt động 1 cách nhất quán, chạy trong các môi trường khác nhau( client, server and native) và dễ dàng để test.
- Redux ra đời lấy cảm hứng từ tư tưởng của ngôn ngữ Elm và kiến trúc Flux của FB
- Với Redux, state của ứng dụng được giữ trong 1 nơi được gọi là store và mỗi component đều có thể access bất kỳ state nào mà chúng muốn từ store này.
- Cách mà Redux hoạt động là khá đơn giản. Nó có 1 store lưu trữ toàn bộ state của app. Mỗi component có thể access trực tiếp đến state được lưu trữ thay vì phải sent drop down props từ component này đến component khác
- Redux có 3 thành phần : Actions, Store, Reducers

## Tại sao nên dùng Redux

- Quản lý Global state
	- Các components tại mọi nơi trong ứng dụng có thể truy xuất và cập nhật
	- Giải quyết vấn đề của React khi muốn truyền dữ liệu vào các cấp con cháu
- Dễ dàng debug
- Xữ lý caching dữ liệu từ server

## Vì sao phải sử dụng Redux Toolkit?

- Sinh ra để giải quyết các vấn đề đối với Redux Core
	- Việc cấu hình(config) Redux phức tạp
	- Phải cài thủ công nhiều packages để Redux có thể hoạt động hiệu quả
	- Redux yêu cầu rất nhiều boilerplate code ( những code lặp đi lặp lại )


## Khi nào nên sử dụng Redux?

- Redux sẽ rất hữu dụng đối với các trường hợp sau đây : 
	- Dự án có số lượng lớn state và các state được sử dụng nhiều nơi
	- State được cập nhật thường xuyên 
	- Logic code cập nhật state phức tạp
	- Ứng dụng có số lượng code trung bình hoặc lớn và có nhiều người làm chung
	- Cần debug và muốn xem cách state được cập nhật tại bất kì khoảng thời gian nào
	- Note: không phải lúc nào cũng nên sử dụng Redux

## Actions

- Được hiểu đơn giản là các events. 
- Chúng là cách chúng ta gửi data (user vs app, API calls, từ form submission) từ app đến redux store 
- Actions được gửi bằng cách sử dụng store.dispatch() method.
- Chúng phải có 1 type property để biểu lộ loại action để thực hiện.
- Chúng phải có 1 payload để chứa thông tin
- Actions được tạo thông qua 1 action creator
 

## Reducers

- Là các function nguyên thủy chúng lấy state hiện tại của app, thực hiện 1 action và trả về 1 state mới
- Những states này được lưu như những objects và chúng định rõ cách state của 1 ứng dụng thay đổi trong việc phản hồi 1 action được gửi đến store
- Những quy ước:
	- Giá trị state mới luôn luôn được tính toán dựa trên giá trị của state trước đó
	- Chúng ta không bao giờ được thay đổi trực tiếp giá trị của state hiện tại mà ta phải tạo ra 1 bản copy và cập nhật vào
	- Không được có 1 đoạn code bất đồng bộ nào trong reducer

##  Store

- Store lưu trạng thái của ứng dụng và nó là duy nhất trong bất kì một ứng dụng redux nào	
- Có thể access các state được lưu, update state, đăng ký hoặc hủy đăng ký các listeners thông qua helper methods