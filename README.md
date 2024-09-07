Bash Port Komut Fonksiyonu
Bu proje, kullanıcıların port numarasını girerek Python HTTP sunucusunu başlatmalarına olanak tanıyan bir Bash fonksiyonu sunar. Port numarası girilmezse, varsayılan olarak port 80 kullanılır. Fonksiyon, sudo yetkisi ile çalıştırılır, böylece gerekli izinler sağlanır.

Özellikler
Port numarasını belirleyerek Python HTTP sunucusu başlatır.
Port numarası girilmezse varsayılan olarak port 80 kullanılır.
sudo ile çalıştırılarak gerekli izinler sağlanır.
Kurulum
1. Bash veya Zsh Konfigürasyon Dosyasını Düzenleme
Fonksiyonu kullanmak için .bashrc veya .zshrc dosyanıza ekleyin:

Bash için:

bash
Kodu kopyala
nano ~/.bashrc
Zsh için:

bash
Kodu kopyala
nano ~/.zshrc
2. Fonksiyonu Ekleyin
Aşağıdaki fonksiyonu dosyanıza ekleyin:

bash
Kodu kopyala
port() {
    # Port numarasını girme işlemi
    echo -n "Port numarasını girin (varsayılan 80): "
    read port_number

    # Eğer port numarası girilmediyse varsayılan olarak 80 kullan
    if [ -z "$port_number" ]; then
        port_number=80
    fi

    # sudo ile Python HTTP sunucusunu başlat
    echo "Sunucu $port_number portunda başlatılıyor..."
    sudo python3 -m http.server $port_number
}
3. Dosyayı Kaydedin ve Terminali Yeniden Yükleyin
Bash için:

bash
Kodu kopyala
source ~/.bashrc
Zsh için:

bash
Kodu kopyala
source ~/.zshrc
Kullanım
Fonksiyonu çalıştırmak için terminale aşağıdaki komutu yazın:

bash
Kodu kopyala
port
Komutu çalıştırdığınızda port numarasını girmenizi isteyen bir mesaj göreceksiniz. Port numarasını girdikten sonra veya bir şey girmezseniz, Python HTTP sunucusu belirtilen portta sudo ile başlatılacaktır.

Katkıda Bulunma
Katkıda bulunmak isterseniz, lütfen bir pull request oluşturun veya önerilerinizi doğrudan paylaşın.

Lisans
Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasına bakabilirsiniz.
