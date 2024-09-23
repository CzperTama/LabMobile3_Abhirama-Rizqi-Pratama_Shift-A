# LabMobile3_Abhirama-Rizqi-Pratama_Shift-A

Nama    : Abhirama Rizqi Pratama
Nim     : H1D022099
Shift Lama : D
Shift Baru : A

# Tugas 3
1. Pendaftaran (registerpage.dart):
    Ketika pengguna mendaftar, nama mereka disimpan menggunakan SharedPreferences:
    dartCopyFuture<void> _register() async {
    if (_formKey.currentState!.validate()) {
    final prefs = await SharedPreferences.getInstance();
    await prefs.setString('name', _nameController.text);
    // ... (data lain juga disimpan)

2. Login (loginpage.dart):
    Ketika pengguna berhasil login, mereka diarahkan ke HomePage:
    dartCopyif (_usernameController.text == savedUsername && _passwordController.text == savedPassword) {
    Navigator.pushReplacement(
    context,
    MaterialPageRoute(builder: (context) => const HomePage()),
    );
    }

3. HomePage (homepage.dart):
    HomePage adalah StatefulWidget yang memuat nama pengguna saat inisialisasi:
    dartCopyclass _HomePageState extends State<HomePage> {
    String? name;
    
    @override
    void initState() {
    super.initState();
    _loadName();
    }
    
    Future<void> _loadName() async {
    final prefs = await SharedPreferences.getInstance();
    setState(() {
    name = prefs.getString('name');
    });
    }

4. Kemudian, dalam method build, nama tersebut ditampilkan:
    dartCopyText(
    name ?? 'User',
    style: const TextStyle(fontSize: 20, color: Colors.white),
    ),

Screenshot
![SSLoginPage.png](assets%2Fimg%2FSSLoginPage.png)
![SSRegisterPage.png](assets%2Fimg%2FSSRegisterPage.png)
![SSHomePage.png](assets%2Fimg%2FSSHomePage.png)
![SSAboutPage.png](assets%2Fimg%2FSSAboutPage.png)
![SSSideMenu.png](assets%2Fimg%2FSSSideMenu.png)
