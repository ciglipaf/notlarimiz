# Git Komutları

Şuraya bakarlar. ☻

`--help`
	- komut satırından, ilgili komut ile ilgili açıklamaların görüntülenmesini sağlar, örneğin **git --help** veya daha da özel olarak **git clone --help** gibi.

`git clone git@github.com:ciglipaf/basliyoruz.git`
	- repository kopyalandı.

`git checkout -b sahur`
	 - **-b** ile sahur branchı oluşturuldu, checkout ile sahur branchına geçiş yapıldı.

`git branch`
	- branchlar görüntülendi.

`git branch -D iftar``
	- iftar branch'ı oluşturuldu.

`git add . `
	- değişiklik yapılan dosyaları, git'in stage etmesini söylüyoruz,
	- **.** kullanınca bulunulan klasör ve alt klasördeki bütün dosyaları kabul ediyor.

`git commit`
	- git'in stage ettiği değişiklikleri işler, yani add yaptığımızda bu değişikliği istediğimizi belirtiyoruz, commit ettiğimizde bu değişikliği işliyoruz.

`git push origin iftar`
	- değişiklikler, origin alias'ının gösterdiği url'ye iftar branch'ı olarak yüklenir.

`git commit -a`
	- önce **git add .** ile ekleyip sonra **git commit** etmek yerine, direkt olarak bu komutu kullanabiliriz.

`git fetch`
	- değişiklikleri bilgisayara çekiyor ama istemiyor, yani değişikliği istemiş gibi kabul edebiliriz, add komutunda olduğu gibi.

`git merge`
	- bilgisayara çekilen yani repository url'sinden istemiş olduğumuz değişiklikleri işliyor. Dosyalarımız repository'e göre güncellenmiş oluyor.

`git pull`
	- önce **git fetch** ve sonra **git merge** yapmak yerine direkt bu komutu kullanabiliriz.

`git reset --merge`
	- merge edilen dosyalar resetlendi.

`git status`
	- dosyalarda değişiklikler vs varsa görüntüler.

`git stash`
	- commit edilmemiş değişikliklerimizi stash adı verilen buffer'a atar ve branch'ımızdan siler. Yani bir bakıma yaptığımız değişiklikten emin değiliz ve commit etmeyeceğiz ama silmek de istemiyoruz, buffer'da yedekliyoruz, zamanı gelince kullanabiliriz.

`git checkout -b ramazan `
	- ramazan adlı bir branchı önce **-b** ile oluşturup sonra checkout ile geçiş yaptık. Böylece önce branch komutuyla oluşturup sonra checkout kullanmaya gerek kalmadı.

`git log`
	- yaptığımız işlemleri gösteriyor, hani şu hep unuttuğun mesajlar var ya, heh işte onlar burada gözüküyor :p

`git log --pretty=oneline`
	- linux komutlarında **-** tek bir tire ilgili komutun seçeneklerini(options) verir. **--** iki tire ise **-** tek tireden farklı olarak verdiği seçenekleri kalıp olarak görür. Şöyle ki yukarıdaki pretty seçeneği tek tire olsaydı shell bunu **p,r,e,t,t,y** olacak şekilde bir çok seçenek olarak algılardı ancak bizim istediğimiz "pretty" adlı seçenek. Eğer birden fazla tek harfli seçenek kullanmak istersek tek tireden yararlanabilirz, mesela **a**, **b**, **c** seçeneklerinin de işlemesin istiyoruz, her biri ayrı bir işe yarıyor, **a** numaraları göster, **b** tarihleri göster vs gibi, o zaman **-abc** yazabiliriz. Bu komutta log işlemi her biri tek satırda olacak şekilde gösteriliyor.

`git log --pretty=oneline --until='21 hours ago'`
	- bir seçenek daha ekledik log komutuna, bu şekilde başka seçenekler de ekleyerek sonucu daraltabiliriz. Son 21 saatte olan logları her biri tek satır olacak şekilde gösteriyor.

`git config --list`
	- git ayarlarımızı listeler.  Şimdilik bizi ilgilendiren name, email gibi basit ayarlar, onları yapılandırmayı da öğrenelim.

`git config --global user.name cmlonder`
	- ayaralarımızı listelediğimizde **user.name = ...** diye bir alan gördük, yani bu seçeneği değiştirebiliriz. Bir çok yol var, diyelim sadece çalıştığın repository'nin kullanıcı adı ayarını değiştireceksin o zaman **--global** yerine **--local** kullanırsan, hani gizli dosya vardı ya **.git** diye, onun içine girersen "config" dosyası var, o bizim ayarlarımızı local olarak tutuyor, bunu değiştirmiş olursun ama globali değiştirirsen her proje için bu bu set ettiğin kullanıcı adını kullanacak olursun, localler de default olarak bunu alır zaten.

`git log --pretty=format:'%h %ad | %s [%an]' --graph --date=short`
	- uu biraz detaylı, şimdi pretty yapıyorduk zaten, daha güzel gösteriyor terminal çıktısını. Bunu bir de formatlıyoruz:
	**%h**
		- commitimizin hash'inin kısaltılmışı
	**%ad**
		- author date, commit ettiğimiz tarih
	|
		- ekranda yazıları ayırdık, sadece şekil amaçlı
	**%s**
		- yazdığımız yorumlar
	**%an**
		- yazar adı, köşeli parantez içinde gösteriliyor bu şekilde girdiğmiiz için parametreyi
	**--graph**
		- commitleri ASCII formatında ağaç şeklinde gösterir
	**--date=short**
		- tarihi gösterir, kısa formda.

`git add submodule git@github.com:ciglipaf/basliyoruz/wiki.git`
	- bu sayede, **basliyoruz** repository'imizin bağımsız oluşturduğumuz **wiki** repository'sini **submodule** olarak eklemiş olduk. basliyoruz'un dosyalar kısmına, bu wiki sayfasına yönlendiren bir link ve modulumuzun github tarafından takibini sağlayacak olan **.gitmodules** dosyası oluşmuş oldu.


[faydalı kaynak](https://services.github.com/kit/downloads/github-git-cheat-sheet.pdf)
