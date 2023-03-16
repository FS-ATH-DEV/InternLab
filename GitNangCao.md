
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

#### IV ) Đẩy nhánh lên github.
```bash
git push -u origin localBranch 
```
Hoặc dùng lệnh này nếu muốn push nhánh hiện tại lên
```bash
git push -u origin HEAD 
```

#### V ) Xóa một branch.
*Xóa branch ở local:*
```bash
git branch -d localBranchName 
```
*Xóa branch ở remote:*
```bash
git push origin -D remoteBranchName 
```
*Khi ai đó xóa nhánh trên remote những gõ `git branch -r` vẫn show ra origin branch đó thì ta có thể thực hiện đồng bộ hóa bằng câu lệnh dưới đây*
```bash
git fetch -p 
```
`-p` nghĩa là "**prune**" sau khi sử dụng câu lệnh git trên những branch không còn trên remote sẽ đồng bộ và xóa khỏi local của bạn.


#### VI ) Git Merge gộp nhánh.
Nếu trong quá trình merge có bị conflict thì thao tác theo thứ tự

1. Tìm file conflict trong tab source và fix nó.
2. Sau khi fix hết các file bị conflict rồi thì dùng `git add .` hoặc add từng file
3. Tiến hành thêm commit cho những file vừa fix conflict bằng câu lệnh `git commit --no-edit`, nếu muốn edit commit thì `git merge --continue`, còn nếu muốn tự viết commit thì cứ `git commit -m 'thông điệp'` như thường
4. push hết lên với câu lệnh `git push`

Nếu merge xong rồi mới nhận ra mình không cần merge nữa thì có thể dùng `git reset --hard <commit-của bạn-trước-khi-merge>`. Cách này áp dụng cho cả đã push code hay chưa push đều được.

> Tips: `git pull` là sự kết hợp giữa `git fetch` và `git merge`. Trong thực tế thì mình dùng `git pull` chứ ít khi dùng `git merge` vì mình luôn muốn fetch data mới nhất từ origin về rồi mới merge.
>
> Bạn cũng có thể tạo merge request (một số chỗ gọi là pull request) bằng git server như Github thay vì dùng câu lệnh. Những merge request này được tạo ra để phục vụ việc team review và approve code.

#### VII ) Git Rebase.

