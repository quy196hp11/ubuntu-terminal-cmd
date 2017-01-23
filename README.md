# ubuntu-terminal-cmd
Tổng hợp các lệnh thường dùng trên Ubuntu

I. Các lệnh quản lí tập tin:
1. Tạo tập tin và thư mục:
cp  file1 file2                        chép tập tin file1 sang file2
cp  file /folfer                      chép tập tin file vào thư mục folder
cp -r folder1 folder2          chép toàn bộ nội dung của thư mục folder1 vào folder2
rsync -a folder1 folder2   đồng bộ nội dung thư mục « folder1» sang thư mục « folder2»
mv file1 file2                        chuyển tên tập tin file1 thành tên file2
mv folder1 folder2              chuyển tên thư mục folder1 thành folder2
mv file folder                       chuyển tập tin file vào thư mục folder
mv file1 folder2/file2         chuyển file1 vào thư mục thư mục folder2 đồng thời đổi tên tập tin thành file2
mkdir folder                        tạo ra thư mục folder
mkdir -p folder1/folder2  tạo ra thư mục cha folder1 và thư mục con folder2 cùng lúc
rm file                                     xóa bỏ tập tin file trong thư mục hiện hành
rmdir folder                         xóa bỏ thư mục trống mang tên folder
rm -rf folder                         xóa bỏ thư mục mang tên folder với tất cả các tập tin trong thư mục
ln -s file link                         tạo ra một liên kết mang tên link đến tập tin file (nối tắt)
find folder -name file         tìm tập tin mang tên file trong thư mục folder kể cả trong các thư mục con
diff file1 file2                        so sánh nội dung của 2 tập tin hoặc của 2 thư mục

2. Xem và chỉnh sửa nội dung các tập tin văn bản:
cat file                                    xem nội dung của tập tin file trên màn hình ở dạng mã ASCII
more file                               xem nội dung của tập tin file trên màn hình theo chế độ từng trang một : ấn phím « Enter » để xuống 1 dòng; ấn phím « Space » để sang thêm 1 trang ; ấn phím « q » để thoắt.
less file                               « less » giống như « more », nhưng cho phép dùng phím [Page Down]
head -n file                        xem số n dòng đầu tiên của tập tin file
tail -n file                           xem số n dòng cuối cùng của file
vi file                                    soạn tập tin file dùng trình soạn vi
nano file                             soạn tập tin file dùng trình soạn nano
gedit file                             soạn tập tin file dùng trình soạn gedit

grep keyword file             tìm và hiển thị các dòng chứa từ keyword trong tập tin file
grep -r string folder        tìm nội dung string trong tất cả các tập tin có trong thư mục folder
lệnh > file                            ghi kết quả của lệnh lệnh trong tập tin file
lệnh >> file                         bổ sung kết quả của lệnh lệnh ở phần cuối của tập tin file

3. Di chuyển, liệt kê tập tin và thư mục:
pwd                                     hiển lên tên thư mục đang làm việc hiện hành
cd                                         di chuyển sang thư mục « /home/người_dùng »
cd ~ /Desktop                   di chuyển sang thư mục « /home/người_dùng/Desktop »
cd ..                                     di chuyển sang thư mục cha (ngay trên thư mục hiện hành)
cd /usr/apt                       di chuyển sang thư mục « /usr/apt »
ls -l                                      folder liệt kê danh mục tập tin trong thư mục folder
ls -a                                     liệt kê tất cả các tập tin, kể cả các tập tin ẩn (thường có tên bắt đầu bằng một dấu chấm)
ls -d                                    liệt kê tên các thư mục nằm trong thư mục hiện hành
ls -t                                     xếp lại các tập tin theo ngày đã tạo ra, bắt đầu bằng những tập tin mới nhất
ls -S                                    xếp lại các tập tin theo kích thước, từ to nhất đến nhỏ nhất
ls -l | more                      liệt kê theo từng trang một, nhờ tiện ích « more »
dir                                      giống như lệnh ls dùng để liệt kê tập tin và thư mục

4. Nén và giải nén tập tin và thư mục:
tar xvf archive.tar           giải phóng các tập tin có trong tập tin « archive.tar », đồng thời hiển thị các tên tập tin
tar xvfz archive.tar.gz           giải nén các tập tin có trong tập tin « archive.tar.gz » dùng « gzip » và « tar »
tar jxvf archive.tar.bz2          giải nén các tập tin có trong tập tin « archive.tar.bz2 » dùng « bzip » và « tar »
tar cvf archive.tar file1 file2   tạo ra một tập tin archive.tar chứa các tập tin file1, file2
tar cvfz archive.tar.gz folder  tạo một tập tin « archive.tar.gz » dùng « gzip » để chứa toàn bộ thư mục folder
gzip file.txt                                   tạo tập tin nén « file.txt» sang « file.txt.gz»
gunzip file.txt.gz                        giải nén tập tin « file.txt.gz »
bzip2 file.txt                                tạo tập tin nén « file.txt.bz2 »
bunzip2 file.txt.bz2                   giải nén tập tin « file.txt.bz2 »

5. Thiết lập quyền truy cập tập tin thư mục:
chown username                      file xác định người chủ của tập tin file là người dùng mang tên « username »
chown -R username folder    xác định người chủ của thư mục folder, kể cả các thư mục con (-R) là người dùng « username»
chgrp group file                        chuyển tập tin file thành sở hữu của nhóm người dùng mang tên group
chmod u+x file                        giao (+) quyền thực thi (x) tập tin file cho người dùng (u)
chmod g-w                               file loại bỏ (-) quyền ghi (w) file của nhóm (g)
chmod o-r file                         loại bỏ (-) quyền đọc (r) tập tin file của những người dùng khác (o)
chmod a+rw file                    giao (+) quyền đọc (r) và ghi (w) file cho mọi người (a)
chmod -R a+rx folder          giao (+) quyền đọc (r) và vào bên trong thư mục (x) folder, kể cả tất cả các thư mục con của nó (-R), cho tất cả mọi người (a)

II. Các lệnh quản lí hệ thống:
1. Các lệnh quản lí cơ bản:
sudo command                       thực hiện lệnh command với tư cách người siêu dùng (root)
gksudo command                  giống với sudo nhưng dùng cho các ứng dụng đồ hoạ
sudo -k                                     chấm dứt chế độ dùng lệnh có chức năng của người siêu dùng
uname -r                                 cho biết phiên bản của nhân Linux
shutdown -h now                khởi động lại máy tính ngay lập tức
lsusb                                         liệt kê các thiết bị usb có mặt trong máy tính
lspci                                          liệt kê các thiết bị pci có trên máy tính
time command                    cho biết thời gian cần thiết để thực hiện xong lệnh command
command1 | command2   chuyển kết quả của lệnh command1 làm đầu vào của lệnh command2
clear                                         xoá màn hình của cửa sổ « Thiết bị cuối » (terminal)

2. Quản lí các gói phần mềm:
/etc/apt/sources.list        tập tin xác định nguồn các kho phần mềm để tải xuống nhằm cài mới hoặc cập nhật hệ thống
apt-get update                    cập nhật danh sách các gói phần mềm căn cứ vào các kho phần mềm có trong tập tin sources.list
apt-get upgrade                 cập nhật các gói phần mềm đã cài rồi
apt-get dist-upgrade        nâng cấp phiên bản Ubuntu đang có đến phiên bản mới tiếp theo
apt-get install soft              cài phần mềm soft đồng thời giải quyết các gói phần mềm phụ thuộc
apt-get remove soft           loại bỏ phần mềm soft cũng như tất cả các gói phần mềm trực thuộc
apt-get remove –purge soft     loại bỏ phần mềm soft kể cả tập tin cấu hình của phần mềm soft
apt-get autoclean             xoá bỏ các bản sao chép của những gói phần mềm đã bị loại bỏ
apt-cache dumpavail      hiện thị danh sách các gói phần mềm đang có
apt-cache search soft      cho biết danh sách các gói phần mềm có tên, hoặc có phần mô tả, chứa chuỗi soft
apt-cache show soft         hiện thị phần mô tả của gói phần mềm soft
apt-cache showpkg soft  hiện thí các thông tin của gói phần mềm soft
apt-cache depends soft   liệt kê các gói phần mềm cần thiết cho gói phần mềm soft
apt-cache rdepends soft   liệt kê các gói phần mềm cần đến gói phần mềm soft
apt-file update                    cập nhật thông tin căn cứ vào danh sách nguồn phần mềm trong tập tin sources.list
apt-file search file               xác định tập tin file thuộc gói phần mềm nào
apt-file list soft                     liệt kê các tập tin có trong gói phần mềm soft
deborphan                            liệt kê các gói phần mềm « mồ côi »
alien -di paquet.rpm        chuyển phần mềm paquet.rpm thành gói phần mềm dạng Debian paquet.deb (-d) và thực hiện cài đặt luôn (-i)
dpkg -i paquet.deb            cài đặt phần mềm paquet.deb (không giải quyết các gói phụ thuộc)
dpkg -c paquet.deb           liệt kê nội dung của gói paquet.deb
dpkg -I paquet.deb           hiển thị thông tin của gói paquet.deb
Chú ý : cần cài các gói phần mềm apt-file, alien và deborphan nếu muốn dùng chúng.

3. Quản lí tiến trình:
ps -ef                                       hiện thị tất cả các tiến trình đã được thực hiện(pid et ppid)
ps aux                                     hiện thị chi tiết các tiến trình
ps aux | grep soft               hiện thị các tiến trình liên quan đến chương khởi động soft
kill pid                                   báo chấm dứt tiến trình mang số pid
kill -9 pid                             yêu cầu hệ thống chấm dứt tiến trình pid
xkill                                       chấm dứt một ứng dụng theo dạng đồ hoạ (ấn chuột vào cửa sổ của ứng dụng)

4. Quản lí mạng
/etc/network/interfaces   thông tin cấu hình của các bộ phần giao diện (interfaces)
uname -a                                  hiện thị tên của máy tính trong mạng (hostname)
ping địa chỉ IP                          thử nối mạng đến máy có địa chỉ IP
ifconfig -a                                hiển thị thông tin về tất cả các giao diện mạng đang có
ifconfig eth0 địa chỉ IP          xác định địa chỉ IP cho giao diện cạc mạng eth0
ifdown eth0                           ngưng hoạt động giao diện cạc mạng eth0
ifconfig eth0 down
ifup eth0                                kích hoạt giao diện cạc mạng eth0
ifconfig eth0 up
poweroff -i                           ngưng hoạt động tất cả các nối mạng
route add default gw địa chỉ IP    xác định địa chỉ IP của máy làm cổng dẫn đến bên ngoài mạng cục bộ
route del default               bỏ địa chỉ IP mặc định để ra khỏi mạng cục bộ

5. Phân vùng ổ cứng:
/etc/fstab                             chứa các thông tin về các ổ cứng và hệ thống tập tin được gắn tự dộng
fdisk -l                                 hiện thị các phân vùng tích cực
mkdir /media/diskusb     tạo thư mục để gắn hệ thống tập tin của thiết bị diskusb
mount /media/cleusb         gắn hệ thống tập tin diskusb
umount /media/cleusb      tách ra hệ thống tập tin diskusb
mount -a                              gắn, tách ra hoăc gắn lại tất cả các
mount -a -o remount    ổ/thiết bị có trong tập tin « /etc/fstab »
fdisk /dev/hda1                 tạo mới và bỏ phân vùng trên ổ cứng IDE thứ nhất
mkfs.ext3 /dev/hda1    tạo một hệ thống tập tin « ext3 » trên phân vùng « /dev/hda1 »
mkfs.vfat /dev/hda1       tạo một hệ thống tập tin « fat32 » trên phân vùng « /dev/hda1 »
