<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trình quét mã vạch & QR Code</title>
    <!-- Tích hợp Tailwind CSS để có giao diện đẹp mắt -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Tùy chỉnh giao diện cho trình quét */
        #reader {
            width: 100%;
            max-width: 500px;
            border-radius: 0.75rem; /* 12px */
            border: 2px solid #e5e7eb; /* gray-200 */
            overflow: hidden;
            margin: 0 auto;
        }
        /* Ẩn nút "Start Scanning" mặc định của thư viện */
        #html5-qrcode-button-camera-start, #html5-qrcode-button-camera-stop {
            display: none !important;
        }
    </style>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">

    <div class="w-full max-w-2xl mx-auto p-4 md:p-8 bg-white rounded-2xl shadow-xl text-center">
        <header class="mb-6">
            <h1 class="text-3xl md:text-4xl font-bold text-gray-800">Trình quét mã vạch & QR Code</h1>
            <p class="text-gray-500 mt-2">Di chuyển máy ảnh của bạn đến mã vạch hoặc mã QR để quét.</p>
        </header>

        <main>
            <!-- Vùng hiển thị camera -->
            <div id="reader-container" class="mb-4">
                <div id="reader"></div>
            </div>

            <!-- Nút điều khiển -->
            <div id="controls" class="flex justify-center space-x-4 mb-6">
                <button id="startButton" class="px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-75 transition duration-300">
                    Bắt đầu quét
                </button>
                <button id="stopButton" class="px-6 py-3 bg-red-600 text-white font-semibold rounded-lg shadow-md hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-opacity-75 transition duration-300 hidden">
                    Dừng quét
                </button>
            </div>

            <!-- Vùng hiển thị kết quả -->
            <div id="result-container" class="bg-gray-50 p-6 rounded-lg border border-gray-200">
                <h2 class="text-xl font-semibold text-gray-700 mb-2">Kết quả</h2>
                <div id="result" class="text-lg text-gray-900 break-words min-h-[3rem] flex items-center justify-center">
                    <span class="text-gray-400">Chưa có kết quả...</span>
                </div>
                 <button id="copyButton" class="mt-4 px-4 py-2 bg-green-500 text-white font-medium rounded-lg shadow-sm hover:bg-green-600 focus:outline-none focus:ring-2 focus:ring-green-400 focus:ring-opacity-75 transition duration-300 hidden">
                    Sao chép kết quả
                </button>
            </div>
        </main>
    </div>

    <!-- Thư viện html5-qrcode -->
    <script src="https://unpkg.com/html5-qrcode" type="text/javascript"></script>
    <script>
        document.addEventListener('DOMContentLoaded', (event) => {
            const startButton = document.getElementById('startButton');
            const stopButton = document.getElementById('stopButton');
            const resultDiv = document.getElementById('result');
            const readerDiv = document.getElementById('reader');
            const copyButton = document.getElementById('copyButton');
            let html5QrcodeScanner = null;

            // Hàm xử lý khi quét thành công
            const onScanSuccess = (decodedText, decodedResult) => {
                console.log(`Scan result: ${decodedText}`, decodedResult);
                
                // Hiển thị kết quả
                resultDiv.innerHTML = `<a href="${decodedText}" target="_blank" class="text-blue-600 hover:underline">${decodedText}</a>`;
                
                // Hiển thị nút sao chép
                copyButton.classList.remove('hidden');

                // Tự động dừng quét sau khi thành công
                stopScanning();
            };

            // Hàm xử lý khi quét lỗi (không phải lỗi thực sự, chỉ là không tìm thấy mã)
            const onScanFailure = (error) => {
                // Thường không cần làm gì ở đây, vì nó sẽ được gọi liên tục.
                // console.warn(`Code scan error = ${error}`);
            };

            // Hàm bắt đầu quét
            const startScanning = () => {
                // Khởi tạo trình quét
                html5QrcodeScanner = new Html5Qrcode("reader");

                const config = { 
                    fps: 10, 
                    qrbox: { width: 250, height: 250 },
                    // Chỉ quét khi camera hiển thị đầy đủ
                    rememberLastUsedCamera: true
                };

                // Bắt đầu quét với camera sau (environment)
                html5QrcodeScanner.start(
                    { facingMode: "environment" },
                    config,
                    onScanSuccess,
                    onScanFailure
                ).then(() => {
                    // Cập nhật giao diện nút
                    startButton.classList.add('hidden');
                    stopButton.classList.remove('hidden');
                    resultDiv.innerHTML = '<span class="text-gray-400">Đang tìm mã...</span>';
                    copyButton.classList.add('hidden');
                }).catch(err => {
                    console.error("Không thể bắt đầu quét", err);
                    resultDiv.innerHTML = `<span class="text-red-500">Lỗi: Không thể truy cập máy ảnh. Vui lòng cấp quyền.</span>`;
                });
            };

            // Hàm dừng quét
            const stopScanning = () => {
                if (html5QrcodeScanner && html5QrcodeScanner.isScanning) {
                    html5QrcodeScanner.stop().then(() => {
                        console.log("Dừng quét thành công.");
                    }).catch(err => {
                        console.error("Lỗi khi dừng quét", err);
                    }).finally(() => {
                        // Cập nhật giao diện nút
                        startButton.classList.remove('hidden');
                        stopButton.classList.add('hidden');
                        html5QrcodeScanner = null;
                        // Xóa canvas video
                        readerDiv.innerHTML = '';
                    });
                }
            };
            
            // Hàm sao chép vào clipboard
            const copyToClipboard = () => {
                const textToCopy = resultDiv.querySelector('a')?.innerText || resultDiv.innerText;
                if(textToCopy) {
                    const tempInput = document.createElement('textarea');
                    tempInput.value = textToCopy;
                    document.body.appendChild(tempInput);
                    tempInput.select();
                    try {
                        document.execCommand('copy');
                        copyButton.innerText = 'Đã sao chép!';
                        setTimeout(() => { copyButton.innerText = 'Sao chép kết quả'; }, 2000);
                    } catch (err) {
                        console.error('Không thể sao chép', err);
                        copyButton.innerText = 'Lỗi sao chép';
                    }
                    document.body.removeChild(tempInput);
                }
            };

            // Gán sự kiện cho các nút
            startButton.addEventListener('click', startScanning);
            stopButton.addEventListener('click', stopScanning);
            copyButton.addEventListener('click', copyToClipboard);
        });
    </script>
</body>
</html>
