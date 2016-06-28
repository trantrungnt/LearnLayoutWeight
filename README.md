# Learn Layout_Weight and Weight_Sum in LinearLayout

##Chú ý khi sử dụng code
+ Thuộc tính weight_sum khai báo trong LinearLayout cha có thể hiểu là: thuộc tính này chia tổng số phần của của Layout Cha
Ở đây, ta chia LinearLayout cha theo chiều rộng thành tổng là 5 phần (weight_sum = 6). Trong LinuearLayout con, ta chia theo chiều height thì cho height=0 và sử dụng layout_weight để chia từng phần theo cho từng LinearLayout con tự động theo chiều rộng (LinearLayout 1 ta cho chiếm 3 phần theo chiều Height, LinearLayout 2 ta cho chiếm 1 phần theo chiều Height, vì tổng là 6 phần nên còn thừa 2 phần của LinearLayout cha)
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FF0000"
    android:weightSum="6"
    android:padding="5dp">
    <LinearLayout
        android:background="#0000FF"
        android:layout_height="0dp"
        android:layout_width="match_parent"
        android:layout_weight="3" />
    <LinearLayout
        android:background="#00FF00"
        android:layout_height="0dp"
        android:layout_width="match_parent"
        android:layout_weight="1" />
</LinearLayout>
```

+ Cho 2 Textview trong 1 LinearLayout và căn theo chiều ngang horizontal (trong đó, mỗi Textview chiếm 1 phần trong giao diện để chứa nội dung)
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="horizontal"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:text="small"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:textColor="@android:color/background_light"
        android:background="@android:color/holo_green_dark" />
    <TextView
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:textColor="@android:color/background_light"
        android:background="@android:color/holo_orange_dark"
        android:text="A very very long text that needs to wrap.Nguyen Tran Trung is ok"
     />
</LinearLayout>
```


##Tham khảo
+ [Các trường hợp sử dụng thuộc tính Layout_Weight trong LinearLayout](http://dulieu.tailieuhoctap.vn/books/cong-nghe-thong-tin/lap-trinh-di-dong/file_goc_778780.pdf)
