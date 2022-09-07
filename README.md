# laravel9_get_current_logged_in_user_data
Bài đăng này sẽ cung cấp cho bạn một ví dụ về laravel 9 lấy id người dùng đã đăng nhập hiện tại. Ở đây bạn sẽ học cách lấy id người dùng hiện tại trong laravel 9.. Trong bài viết này, chúng tôi sẽ triển khai lấy dữ liệu người dùng hiện tại laravel 9. Bạn chỉ cần thực hiện một số bước để có được email người dùng hiện tại trong laravel 9. Trong hướng dẫn này, tôi sẽ cung cấp cho bạn bốn cách để lấy chi tiết người dùng đăng nhập hiện tại trong xem tệp và tệp bộ điều khiển, vì vậy chúng ta hãy xem các ví dụ sau như bên dưới: 
1) Laravel 9 Lấy người dùng hiện tại trong Bộ điều khiển bằng Trình trợ giúp 
2) Laravel 9 Nhận Người dùng hiện tại trong Bộ điều khiển bằng cách sử dụng Mặt tiền 
3) Laravel 9 Nhận Người dùng hiện tại trong Chế độ xem Blade bằng Trình trợ giúp 
4 ) Laravel 9 Lấy người dùng hiện tại trong View Blade bằng cách sử dụng Facade 
Vì vậy, hãy xem tôi đã thêm hai cách để lấy dữ liệu người dùng hiện tại trong ứng dụng laravel 9.
## 1:  Laravel 9 Get Current User in Controller using Helper
- Ở đây, chúng ta sẽ lấy dữ liệu người dùng hiện tại bằng cách sử dụng auth () trong laravel 9
```Dockerfile
<?php
  
namespace App\Http\Controllers;
  
use Illuminate\Http\Request;
  
class UserController extends Controller
{
    /**
     * Display a listing of the resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function index(Request $request)
    {
   
        /* Current Login User Details */
        $user = auth()->user();
        var_dump($user);
      
        /* Current Login User ID */
        $userID = auth()->user()->id; 
        var_dump($userID);
          
        /* Current Login User Name */
        $userName = auth()->user()->name; 
        var_dump($userName);
          
        /* Current Login User Email */
        $userEmail = auth()->user()->email; 
        var_dump($userEmail);
    }
}
```
## 2: Laravel 9 Get Current User in Controller using Facade
- Tại đây, chúng ta sẽ lấy dữ liệu người dùng hiện tại bằng cách sử dụng Auth front trong laravel 9.
```Dockerfile
<?php
  
namespace App\Http\Controllers;
  
use Illuminate\Http\Request;
use Auth;
  
class UserController extends Controller
{
    /**
     * Display a listing of the resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function index(Request $request)
    {
        /* Current Login User Details */
        $user = Auth::user();
        var_dump($user);
      
        /* Current Login User ID */
        $userID = Auth::user()->id; 
        var_dump($userID);
          
        /* Current Login User Name */
        $userName = Auth::user()->name; 
        var_dump($userName);
          
        /* Current Login User Email */
        $userEmail = Auth::user()->email; 
        var_dump($userEmail);
    }
}
```
## 3: Laravel 9 Get Current User in View Blade using Helper
- Ở đây, chúng tôi sẽ lấy dữ liệu người dùng hiện tại bằng cách sử dụng trình trợ giúp auth () trong laravel 9.
```Dockerfile
<p> User ID: {{ auth()->user()->id }} </p>
<p> User Name: {{ auth()->user()->name }} </p>
<p> User Email: {{ auth()->user()->email }} </p>
```
## 4: LLaravel 9 Get Current User in View Blade using Facade
- Tại đây, chúng tôi sẽ lấy dữ liệu người dùng hiện tại bằng Auth Facade trong laravel 9.
```Dockerfile
<p> User ID: {{ Auth::user()->id }} </p>
<p> User Name: {{ Auth::user()->name }} </p>
<p> User Email: {{ Auth::user()->email }} </p>
```
