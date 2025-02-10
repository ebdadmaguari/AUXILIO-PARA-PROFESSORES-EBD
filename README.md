
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simpósio EBD 2025 - Inscrição</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.17.0/xlsx.full.min.js"></script>
    <script src="https://unpkg.com/sweetalert2@11"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/imask/6.4.3/imask.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
</head>
<body class="min-h-screen bg-gradient-to-br from-blue-50 via-white to-blue-50">
    <!-- Receipt Template (Hidden) -->
    <div id="receipt" class="hidden">
        <div class="p-8 bg-white" style="width: 210mm;">
            <div class="text-center mb-8">
                <img 
                    src="c:\Users\MIDIAN\Desktop\EBD 2024\Logos\IMG_20230124_205859_973ioio.jpg"
                    alt="EBD Logo" 
                    class="w-32 h-32 mx-auto mb-4 rounded-full object-cover"
                />
                <h1 class="text-3xl font-bold text-gray-900">Comprovante de Inscrição</h1>
                <p class="text-lg text-gray-600">Simpósio EBD 2025</p>
            </div>
            <div class="space-y-4 text-gray-700">
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <p class="font-semibold">Nome:</p>
                        <p id="receipt-name" class="text-gray-600"></p>
                    </div>
                    <div>
                        <p class="font-semibold">Email:</p>
                        <p id="receipt-email" class="text-gray-600"></p>
                    </div>
                    <div>
                        <p class="font-semibold">Congregação:</p>
                        <p id="receipt-congregation" class="text-gray-600"></p>
                    </div>
                    <div>
                        <p class="font-semibold">Grupo:</p>
                        <p id="receipt-group" class="text-gray-600"></p>
                    </div>
                    <div>
                        <p class="font-semibold">Campo:</p>
                        <p id="receipt-field" class="text-gray-600"></p>
                    </div>
                    <div>
                        <p class="font-semibold">Telefone:</p>
                        <p id="receipt-phone" class="text-gray-600"></p>
                    </div>
                    <div>
                        <p class="font-semibold">Data da Inscrição:</p>
                        <p id="receipt-date" class="text-gray-600"></p>
                    </div>
                </div>
                <div class="mt-8 border-t border-gray-200 pt-6">
                    <div class="flex justify-between items-center text-lg">
                        <span class="font-semibold">Valor da Inscrição:</span>
                        <span class="text-green-600 font-bold">R$ 50,00</span>
                    </div>
                    <div class="flex justify-between items-center mt-2">
                        <span class="font-semibold">Status:</span>
                        <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm font-medium">
                            PAGO
                        </span>
                    </div>
                </div>
                <div class="mt-12 text-center">
                    <p class="text-sm text-gray-500">Este documento é seu comprovante oficial de inscrição e pagamento.</p>
                    <p class="text-sm text-gray-500">Simpósio EBD 2025 - Todos os direitos reservados</p>
                </div>
            </div>
        </div>
    </div>

    <div class="container mx-auto px-4 py-12">
        <div class="max-w-2xl mx-auto">
            <!-- Header Card -->
            <div class="bg-white rounded-2xl shadow-xl p-8 mb-8">
                <div class="text-center">
                    <img 
                        src="c:\Users\MIDIAN\Desktop\EBD 2024\Logos\IMG_20230124_205859_973ioio.jpg"
                        alt="EBD Logo" 
                        class="w-32 h-32 mx-auto mb-6 rounded-full object-cover shadow-lg ring-4 ring-blue-50"
                    />
                    <h1 class="text-4xl font-bold text-gray-900 mb-2">Simpósio EBD 2025</h1>
                    <p class="text-gray-600">Formulário de Inscrição</p>
                </div>
            </div>

            <!-- Registration Form Card -->
            <div class="bg-white rounded-2xl shadow-xl p-8">
                <form id="registrationForm" class="space-y-6">
                    <div class="space-y-6">
                        <!-- Nome Completo -->
                        <div class="form-group">
                            <label for="name" class="block text-sm font-medium text-gray-700 mb-2">
                                Nome Completo
                            </label>
                            <div class="relative rounded-md shadow-sm">
                                <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                                    <i data-lucide="user" class="h-5 w-5 text-gray-400"></i>
                                </div>
                                <input
                                    type="text"
                                    id="name"
                                    class="pl-10 block w-full rounded-lg border-gray-300 bg-gray-50 focus:ring-blue-500 focus:border-blue-500 transition-colors"
                                    required
                                />
                            </div>
                        </div>

                        <!-- Email (New Field) -->
                        <div class="form-group">
                            <label for="email" class="block text-sm font-medium text-gray-700 mb-2">
                                Email
                            </label>
                            <div class="relative rounded-md shadow-sm">
                                <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                                    <i data-lucide="mail" class="h-5 w-5 text-gray-400"></i>
                                </div>
                                <input
                                    type="email"
                                    id="email"
                                    class="pl-10 block w-full rounded-lg border-gray-300 bg-gray-50 focus:ring-blue-500 focus:border-blue-500 transition-colors"
                                    required
                                />
                            </div>
                        </div>

                        <!-- Congregação -->
                        <div class="form-group">
                            <label for="congregation" class="block text-sm font-medium text-gray-700 mb-2">
                                Congregação
                            </label>
                            <div class="relative rounded-md shadow-sm">
                                <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                                    <i data-lucide="church" class="h-5 w-5 text-gray-400"></i>
                                </div>
                                <input
                                    type="text"
                                    id="congregation"
                                    class="pl-10 block w-full rounded-lg border-gray-300 bg-gray-50 focus:ring-blue-500 focus:border-blue-500 transition-colors"
                                    required
                                />
                            </div>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <!-- Grupo -->
                            <div class="form-group">
                                <label for="group" class="block text-sm font-medium text-gray-700 mb-2">
                                    Grupo
                                </label>
                                <div class="relative rounded-md shadow-sm">
                                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                                        <i data-lucide="users" class="h-5 w-5 text-gray-400"></i>
                                    </div>
                                    <select
                                        id="group"
                                        class="pl-10 block w-full rounded-lg border-gray-300 bg-gray-50 focus:ring-blue-500 focus:border-blue-500 transition-colors"
                                    >
                                    </select>
                                </div>
                            </div>

                            <!-- Campo -->
                            <div class="form-group">
                                <label for="field" class="block text-sm font-medium text-gray-700 mb-2">
                                    Campo
                                </label>
                                <div class="relative rounded-md shadow-sm">
                                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                                        <i data-lucide="map-pin" class="h-5 w-5 text-gray-400"></i>
                                    </div>
                                    <input
                                        type="text"
                                        id="field"
                                        class="pl-10 block w-full rounded-lg border-gray-300 bg-gray-50 focus:ring-blue-500 focus:border-blue-500 transition-colors"
                                        required
                                    />
                                </div>
                            </div>
                        </div>

                        <!-- Telefone -->
                        <div class="form-group">
                            <label for="phone" class="block text-sm font-medium text-gray-700 mb-2">
                                Telefone
                            </label>
                            <div class="relative rounded-md shadow-sm">
                                <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                                    <i data-lucide="phone" class="h-5 w-5 text-gray-400"></i>
                                </div>
                                <input
                                    type="tel"
                                    id="phone"
                                    class="pl-10 block w-full rounded-lg border-gray-300 bg-gray-50 focus:ring-blue-500 focus:border-blue-500 transition-colors"
                                    required
                                />
                            </div>
                        </div>
                    </div>

                    <button
                        type="submit"
                        class="w-full flex justify-center items-center py-3 px-4 border border-transparent rounded-lg shadow-sm text-sm font-medium text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition-colors"
                    >
                        <i data-lucide="check-circle" class="h-5 w-5 mr-2"></i>
                        Realizar Inscrição
                    </button>
                </form>
            </div>
        </div>
    </div>

    <!-- Payment Modal -->
    <div id="paymentModal" class="hidden fixed inset-0 bg-black bg-opacity-50 backdrop-blur-sm flex items-center justify-center p-4 z-50">
        <div class="bg-white rounded-2xl max-w-lg w-full p-8 relative">
            <button
                onclick="closePaymentModal()"
                class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 focus:outline-none"
                aria-label="Fechar"
            >
                <i data-lucide="x" class="h-6 w-6"></i>
            </button>

            <div class="text-center mb-8">
                <div class="bg-blue-50 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                    <i data-lucide="qr-code" class="h-8 w-8 text-blue-600"></i>
                </div>
                <h2 class="text-2xl font-bold text-gray-900">Pagamento PIX</h2>
                <p class="text-gray-600 mt-1">Valor a pagar: <span class="font-semibold">R$ 50,00</span></p>
            </div>

            <div class="space-y-6">
                <!-- PIX Key Section -->
                <div class="bg-gray-50 p-6 rounded-xl">
                    <h3 class="font-medium text-gray-900 mb-3">Chave PIX (Telefone):</h3>
                    <div class="flex items-center justify-between bg-white p-4 rounded-lg border border-gray-200">
                        <span class="font-mono text-lg">(11) 98765-4321</span>
                        <button
                            onclick="copyPixKey()"
                            class="text-blue-600 hover:text-blue-800 focus:outline-none"
                            aria-label="Copiar chave PIX"
                        >
                            <i data-lucide="copy" class="h-5 w-5"></i>
                        </button>
                    </div>
                    <div class="mt-3 text-sm text-gray-600">
                        <p>Nome: João da Silva</p>
                        <p>Banco: Banco XYZ</p>
                    </div>
                </div>

                <!-- QR Code Section -->
                <div class="text-center">
                    <h3 class="font-medium text-gray-900 mb-4">QR Code PIX</h3>
                    <div class="bg-white p-4 rounded-xl inline-block shadow-sm">
                        <img
                            src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=00020126580014BR.GOV.BCB.PIX0136123e4567-e89b-12d3-a456-4266554400005204000053039865802BR5913Joao%20da%20Silva6008BRASILIA62070503***63041D3D"
                            alt="QR Code PIX"
                            class="w-48 h-48"
                        />
                    </div>
                </div>

                <!-- Upload Section -->
                <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-medium text-gray-900 mb-4">Após realizar o pagamento:</h3>
                    <div>
                        <label class="block w-full">
                            <input
                                type="file"
                                id="proofFile"
                                class="hidden"
                                accept="image/*"
                                onchange="handleProofUpload(event)"
                            />
                            <button
                                onclick="document.getElementById('proofFile').click()"
                                class="w-full flex items-center justify-center px-4 py-3 rounded-lg text-sm font-medium text-white bg-green-600 hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors"
                            >
                                <i data-lucide="upload" class="h-5 w-5 mr-2"></i>
                                Enviar Comprovante
                            </button>
                        </label>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Initialize Lucide icons
        lucide.createIcons();

        // Store registrations data
        let registrations = [];

        // Populate group select
        const groupSelect = document.getElementById('group');
        for (let i = 1; i <= 20; i++) {
            const num = i.toString().padStart(2, '0');
            const option = document.createElement('option');
            option.value = num;
            option.textContent = `Grupo ${num}`;
            groupSelect.appendChild(option);
        }

        // Phone mask
        const phoneInput = document.getElementById('phone');
        IMask(phoneInput, {
            mask: '(00) 00000-0000'
        });

        // Form submission
        document.getElementById('registrationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            if (!validateForm()) {
                Swal.fire({
                    icon: 'error',
                    title: 'Campos Obrigatórios',
                    text: 'Por favor, preencha todos os campos do formulário.',
                    confirmButtonColor: '#3B82F6'
                });
                return;
            }

            document.getElementById('paymentModal').classList.remove('hidden');
        });

        // Validate form
        function validateForm() {
            const requiredFields = ['name', 'email', 'congregation', 'field', 'phone'];
            return requiredFields.every(field => document.getElementById(field).value.trim() !== '');
        }

        // Close payment modal
        function closePaymentModal() {
            document.getElementById('paymentModal').classList.add('hidden');
        }

        // Copy PIX key
        async function copyPixKey() {
            try {
                await navigator.clipboard.writeText('11987654321');
                Swal.fire({
                    icon: 'success',
                    title: 'Chave PIX Copiada!',
                    toast: true,
                    position: 'top-end',
                    showConfirmButton: false,
                    timer: 3000,
                    timerProgressBar: true
                });
            } catch (err) {
                console.error('Failed to copy PIX key:', err);
            }
        }

        // Handle proof upload with new features
        function handleProofUpload(event) {
            if (event.target.files?.[0]) {
                closePaymentModal();
                
                // Get form data
                const formData = {
                    name: document.getElementById('name').value,
                    email: document.getElementById('email').value,
                    congregation: document.getElementById('congregation').value,
                    group: document.getElementById('group').value,
                    field: document.getElementById('field').value,
                    phone: document.getElementById('phone').value,
                    date: new Date().toLocaleString()
                };

                // Store registration data
                registrations.push(formData);

                // Generate receipt
                generateReceipt(formData);

                // Generate PDF receipt
                generatePDF(formData).then(pdfBlob => {
                    // Send WhatsApp message with receipt
                    const phoneNumber = formData.phone.replace(/\D/g, '');
                    const whatsappUrl = `https://wa.me/55${phoneNumber}?text=${encodeURIComponent(
                        'Obrigado pela sua inscrição no Simpósio EBD 2025! Segue seu comprovante de inscrição.'
                    )}`;
                    window.open(whatsappUrl, '_blank');

                    // Export to Excel
                    exportToExcel(formData);
                });

                Swal.fire({
                    icon: 'success',
                    title: 'Inscrição Confirmada!',
                    text: 'O comprovante foi enviado para seu WhatsApp e email.',
                    showConfirmButton: false,
                    timer: 3000,
                    timerProgressBar: true
                });

                document.getElementById('registrationForm').reset();
            }
        }

        // Generate PDF receipt
        async function generatePDF(data) {
            generateReceipt(data);
            const receipt = document.getElementById('receipt');
            receipt.style.display = 'block';
            
            const pdfOptions = {
                margin: 1,
                filename: `comprovante_inscricao_${data.name.replace(/\s+/g, '_')}.pdf`,
                image: { type: 'jpeg', quality: 0.98 },
                html2canvas: { scale: 2 },
                jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };

            try {
                const pdf = await html2pdf().set(pdfOptions).from(receipt).save();
                receipt.style.display = 'none';
                return pdf;
            } catch (error) {
                console.error('Error generating PDF:', error);
                receipt.style.display = 'none';
            }
        }

        // Export to Excel (single file)
        async function exportToExcel(newRegistration) {
            try {
                let allRegistrations = [];
                
                // Try to load existing data from localStorage
                const existingData = localStorage.getItem('registrations');
                if (existingData) {
                    allRegistrations = JSON.parse(existingData);
                }
                
                // Add new registration
                allRegistrations.push(newRegistration);
                
                // Save updated data to localStorage
                localStorage.setItem('registrations', JSON.stringify(allRegistrations));
                
                // Create Excel file with all registrations
                const ws = XLSX.utils.json_to_sheet(allRegistrations);
                const wb = XLSX.utils.book_new();
                XLSX.utils.book_append_sheet(wb, ws, "Inscrições");
                
                // Save the file
                XLSX.writeFile(wb, "inscricoes_simposio_ebd_2025.xlsx");
            } catch (error) {
                console.error('Error saving to Excel:', error);
                
                // If error occurs, at least save to localStorage
                localStorage.setItem('registrations', JSON.stringify([newRegistration]));
            }
        }

        // Generate receipt
        function generateReceipt(data) {
            document.getElementById('receipt-name').textContent = data.name;
            document.getElementById('receipt-email').textContent = data.email;
            document.getElementById('receipt-congregation').textContent = data.congregation;
            document.getElementById('receipt-group').textContent = `Grupo ${data.group}`;
            document.getElementById('receipt-field').textContent = data.field;
            document.getElementById('receipt-phone').textContent = data.phone;
            document.getElementById('receipt-date').textContent = data.date;
        }
    </script>
</body>
</html>
