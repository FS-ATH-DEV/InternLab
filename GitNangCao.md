
<h1 style="color: green">GIT BRANCH</h1>

#### I ) Tạo và di chuyển đến các nhánh
- *tạo và di chuyển*: `git checkout -b` tên nhánh muốn tạo và di chuyển.
- *tạo*: `git branch`~ tên nhánh muốn tạo.
- *di chuyển*: `git checkout ` tên nhánh muốn di chuyển hoặc `git switch`.

<span style="color: red; font-weight: 600"># NOTE:</span> 

> Có thể thay thế `git checkout` thành `git switch`



#### II ) Hiển thị các nhánh đang có ở local và remote
- **local**: git branch
- **remote**: git branch -r
- **both**: git branch -a
<p style="color: red; font-weight: 600"># NOTE:</p> 

> Khi `git branch -r` không hiển thị ở local nếu muốn cập nhật trên github `git fetch`.

#### III ) Đổi tên nhánh.

Nếu bạn tạo tên nhánh bị sai, bạn cũng có thể sửa lại tên nhánh hiện tại bằng cách

```bash
git branch -m TenMoi
```

Cách trên chỉ áp dụng khi nhánh hiện tại của bạn là nhánh sai và bạn muốn đổi tên nhánh hiện tại. Trong trường hợp bạn muốn đổi tên nhánh nào đó không nhất thiết là nhánh hiện tại thì bạn phải ghi rõ tên nhánh cũ và nhánh mới như dưới đây

```bash
git branch -m TenNhanhCu TenNhanhMoi
```

Các bạn đổi tên branch thì chỉ đổi được ở dưới local repo, nếu branch đó đã xuất hiện ở trên remote repo thì khi bạn push nó sẽ tạo một branch mới trên remote repo
