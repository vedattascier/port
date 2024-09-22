# Sunucu Komut Fonksiyonu

<p>Bu proje, port numarasını girerek Python HTTP sunucusunu başlatmanıza olanak tanıyan bir Bash fonksiyonu sunar. Port numarası girilmezse, varsayılan olarak port 80 kullanılır. Fonksiyon <code>sudo</code> yetkisi ile çalıştırılır.</p>

## Özellikler

<ul>
    <li><strong>Port Numarası Girişi:</strong> Port numarasını belirleyerek Python HTTP sunucusu başlatabilirsiniz.</li>
    <li><strong>Varsayılan Port:</strong> Port numarası girilmezse varsayılan olarak port 80 kullanılır.</li>
    <li><strong><code>sudo</code> İle Çalıştırma:</strong> Gerekli izinlerle sunucu başlatılır.</li>
</ul>

## Kurulum

### 1. `.bashrc` veya `.zshrc` Dosyasını Düzenleme

<p>Fonksiyonu kullanabilmek için <code>.bashrc</code> veya <code>.zshrc</code> dosyanıza ekleyin:</p>

<ul>
    <li><strong>Bash için:</strong>
        <pre><code>nano ~/.bashrc</code></pre>
    </li>
    <li><strong>Zsh için:</strong>
        <pre><code>nano ~/.zshrc</code></pre>
    </li>
</ul>

### 2. Fonksiyonu Ekleyin

<p>Aşağıdaki fonksiyonu dosyanıza ekleyin:</p>

<pre><code>sunucu() {
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
</code></pre>

### 3. Dosyayı Kaydedin ve Terminali Yeniden Yükleyin

<ul>
    <li><strong>Bash için:</strong>
        <pre><code>source ~/.bashrc</code></pre>
    </li>
    <li><strong>Zsh için:</strong>
        <pre><code>source ~/.zshrc</code></pre>
    </li>
</ul>

## Kullanım

<p>Terminalde aşağıdaki komutu çalıştırarak fonksiyonu kullanabilirsiniz:</p>

<pre><code>port
</code></pre>

<p>Bu komutu yazdığınızda port numarasını girmenizi isteyen bir mesaj göreceksiniz. Port numarasını girdikten sonra veya varsayılan olarak port 80'i kullanarak Python HTTP sunucusu <code>sudo</code> ile başlatılır.</p>

## Katkıda Bulunma

<p>Katkıda bulunmak isterseniz, lütfen bir pull request oluşturun veya önerilerinizi doğrudan paylaşın.</p>

## Lisans

<p>Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için <code>LICENSE</code> dosyasına göz atabilirsiniz.</p>
