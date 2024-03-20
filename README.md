# Hoạt động của Git
![github](https://github.com/phuccoderr/github-demo-phuc/assets/124669538/c1d5e7fe-54ab-4d18-a70f-d704b6706c61)
# Câu lệnh up lên git bình thường
~~~
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin https://github.com/phuccoderr/tesst.git
git pull --rebase  origin master (nếu cần thiết )
git push -u origin master
~~~
# Những lệnh Git cơ bản thường dùng
- Git version:
~~~
git --v
~~~
- Git config:
~~~
git config --g user.name "Dev name"
git config --g user.email "Dev email"
git config --list
~~~
- Git help:
~~~
git help -a OR git help --all (  Hướng dẫn bạn có thể làm được những gì, tất cả các lệnh có thể. )
git config --help ( Đưa bạn tới trang hướng dẫn chính thống của Git. )
git command -help ( Xem tất cả các tùy chọn có sẵn cho lệnh cụ thể )
~~~
- Git mkdir:
~~~
git mkdir folder_name  ( Tạo repository trong hệ thống local. )
cd folder_name ( Di chuyển đến folder_name repository vừa tạo ra. )
~~~
- Git remote:
~~~
git remote add origin <url> ( Liên kết đến remote repository (local & GitHub) )
git remote set-url <name> <new url> ( Thay đổi địa chỉ của remote repository đã Liên kết vào địa chỉ của <new url>. )
git remote rename <old> <new> ( Thay đổi tên của remote repository đã Liên kết. )
~~~
- Git init:
~~~
git init (Khởi tạo git trong thư mục dự án của bạn)
~~~
- Git status:
~~~
git status
git status --short
(Kiểm tra trạng thái của kho lưu trữ)
?? - Tập tin không bị theo dõi
A - Tệp được thêm vào giai đoạn
M - Tệp đã sửa đổi
D - Các tệp đã xóa
~~~
- Git add:
~~~
git add . OR git add --all
git add index.html (có thể chỉ định trực tiếp tên tệp cần add)
~~~
- Git commit:
  - Git commit: Ghi lại các thay đổi vào kho lưu trữ. (Cần thêm các thông điệp rõ ràng vào mỗi mục commit)
  - Cách đặt tên branch hay commit nên rõ ràng, thể hiện branch đó, commit đó thực hiện feature gì hay là fix bug gì... (thường thì sẽ theo quy định của công ty)
~~~
git commit -m "Thông điệp của bạn"
~~~
- Git diff:
~~~
git diff ( So sánh sự khác biệt kể từ lần commit cuối cùng của bạn. )
git log ( Xem lịch sử làm việc với git (lịch sử commit) )
~~~
- Git push:
~~~
git push -u origin branch_name ( Push (đẩy) branch vào remote repository. )
git push ( Push (đẩy) tất cả mọi thay đổi (đã commit) lên remote repository. )
git push -d origin branch_name ( Xóa một branch trên remote repository. )
git push -f origin branch_name ( Push force sẽ apply toàn bộ log ở local của bạn lên branch ở repo, bất chấp log 2 nơi khác nhau. (Xóa vĩnh viễn branch cũ Push branch mới. Dễ gây conflict cho người khác cẩn trọng trước khi dùng) )
~~~
- Git branch:
~~~
git branch -M branch_name (main) ( Đổi tên nhánh chính )
git branch ( Kiểm tra các nhánh hiện có của bạn ở local. )
git branch -c branch_name OR git checkout -b branch_name (Tạo và chuyển luôn sang nhánh mới) ( Tạo một nhánh có tên “branch_mane” và hợp nhất (merge) nó với nhánh chính. )
git branch -d branch_name ( Xóa một nhánh tại local có tên: "branch_mane" (branch đã được hợp nhất (push) vào remote repository) )
git branch -D branch_mane ( Xóa một nhánh tại local có tên: "branch_mane" (branch đã commit nhưng chưa hợp nhất vào remote repository) )
git branch -a ( Kiểm tra các branch hiện có trên remote repo của bạn. )
~~~
- Git checkout:
~~~
git checkout -b branch_name (Tạo và chuyển luôn sang nhánh mới)
git checkout branch_name ( Lệnh trên giúp di chuyển không gian làm việc, kiểm tra tệp giữa các branch_name )
~~~
- Git fetch:
  - Git fetch cho phép CẬP NHẬT để xem điều gì đã thay đổi trên GitHub của bạn.
  - Lệnh fetch (xác nhận nội dung thay đổi trong branch của remote repository) nhưng nội dung branch của local repository không bị thay đổi.
~~~
git fetch origin
~~~
- Git merge:
~~~
git checkout branch_name1 (Nhánh nhận hợp nhất or nhánh hiện tại)
git merge branch_name2 (Nhánh chỉ định hợp nhất) (Nhánh hiện tại là nhánh bạn đang đứng, nhánh chỉ định là nhánh sau lệnh $ git merge)
~~~
- Git pull:
~~~
git pull origin main ( Git pull kéo tất cả các thay đổi từ main về local. )
git pull ( Git pull kéo tất cả các thay đổi từ branch_mane về local. )
git pull origin ( Git pull kéo tất cả các thay đổi từ kho lưu trữ từ xa vào branch bạn đang làm việc. (pull là sự kết hợp của 2 lệnh khác nhau: fetch và merge) )
git pull --rebase (Cach pull chống xung đột)
~~~
- Git clone:
~~~
git clone <url>  (Địa chỉ dự án bạn muốn Clone) ( Clone dự án có sẵn trên GitHub. )
git clone <url> folder_name ( Clone đồng thời đổi tên dự án theo ý bạn khi save vào local. )
~~~
- Git stash:
~~~
git stash save # OR $ git stash ( Lưu lại công việc đang làm ở branch này để chuyển sang branch khác (Khi bạn chưa muốn commit code) )
git stash list ( Xem lại lịch sử thay đổi. )
git stash show stash@{n} ( Xem lại lịch sử thay đổi cụ thể của lần stash save{n}. )
git stash apply stash@{1} ( Apply thay đổi của lần stash save{n}. )
git stash clear ( Xoá toàn bộ stash. )
~~~~
  
