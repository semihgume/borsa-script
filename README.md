## Borsa İstanbul Hissesinin Anlık Verilerini Çekme Scripti

- Bu bash scripti, Hürriyet Bigpara'nın API'sini kullanarak Borsa İstanbul'da listelenen bir hissenin anlık verilerini çekmek için tasarlanmıştır.
- Çekilen veriler arasında hisse sembolü, açıklama, açılış fiyatı, alış fiyatı, satış fiyatı, yüzdesel değişim ve son işlem tarihi bulunmaktadır.
- API'den alınan veriler, jq aracı kullanılarak işlenir ve ekrana düzenli bir şekilde yazdırılır.
- API'nin sağladığı veriler 15 dakika gecikmelidir!

### Gerekli Araçlar

Bu scriptin doğru çalışabilmesi için aşağıdaki araçların yüklü olması gerekmektedir:

- **cURL:** HTTP istekleri yapmak için kullanılır.
- **jq:** JSON verilerini işlemek için kullanılır.

Not: Scriptin doğru çalışabilmesi için 'curl' ve 'jq' araçlarının yüklü olduğundan emin olunmalıdır.

### Kullanım

1. Repoyu kopyalayın:
    ```bash
    git clone https://github.com/semihgume/borsa-script.git
    cd borsa-script
    ```

2. Scripte çalıştırma izni verin:
    ```bash
    chmod +x borsa
    ```

3. Scripti çalıştırın:
    ```bash
    ./borsa <hisse_sembolu>
    ```

Not: Scripti herhangi bir dizinden çalıştırmak istiyorsanız, `borsa` dosyasını `/usr/bin/` dizinine taşıyabilir ve doğrudan kullanabilirsiniz.
```bash
sudo cp borsa /usr/bin/
borsa <hisse_sembolu>
```


NOT: Hürriyet Bigpara'nın API'si tam verimli çalışmadığı için bazen 401 hata kodu döndürmektedir. Bir kaç dakika bekledikten sonra tekrar deneyebilirsiniz.
