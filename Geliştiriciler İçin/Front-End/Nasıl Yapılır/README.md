![](https://i.imgur.com/lnLCnfj.png)
<h1 align="center">
Vite ile Vue Projesi Oluşturmak
</h1>

> <p align="center">Burada gördüğün her şeyi, hatta daha fazlasını <a href="https://vitejs.dev/guide/">resmi Vite dökümanından</a> inceleyebilirsin. ^.^</p>

<br/><br/>

## Vite ne? Neden Vite?

Vite bir derleme aracı. Derleme aracı ne diye sorarsan; projemiz için çıktı alacağımız zaman bu derleyiciler kodumuzu derleyip, dönüştürüyorlar. Kabaca, bizim yazdığımız kodları tarayıcının anlayacağı kodlara dönüştürüyorlar. Bunu yaparken tarayıcılar arasındaki uyumluluk da göz önünde bulunduruyor.

Standart olarak derleyiciler olarak Webpack, Babel, Parcel gibi araçlar kullanıyordu. Ancak projeler büyümeye, karmaşıklaşmaya başladı ve dolayısıyla projeleri derlemek ve hatta localde çalıştırmak hayli ağırlaştı. Evan You (Vue'nun yaratıcısı) ise daha verimli ve güçlü bir derleyici oluşturmaya karar verdi ve Vite ortaya çıktı. Vite; Webpack, Rollup ve Parcel gibi araçlardan güç alarak ağır projelerin altından kalkması hedeflendi. Aynı zamanda Vite; sadece Vue ile de değil, React ve Vanilla JavaScript ile de kullanılabiliyor. Vite hakkında çok daha detaylı ve teknik bilgiye erişmek istiyorsan resmi dökümantasyonuna bakmalısın. Biz sadece kullanmaya başlamadan önce kabac anlatmak istedik.

<br/><br/>

## Adım #1: Vite için gerekli komutlar
Vite'in ne olduğunu ve bize ne sağladığını temel olarak anladığımıza göre, artık Vite ile Vue projemizi oluşturacak komutları öğrenebiliriz.

Öncelikle senden bir terminal açmanı isteyeceğim çünkü `npm` komutunu kullanacağız. Biz terminal olarak [Tabby](https://tabby.sh "Tabby") öneriyoruz. Yine de sen bilirsin "tabby".  :sweat_smile:  Ama bu bir örnek olduğu için şimdilik `cmd (Komut İstemcisi)` üzerinden göstereceğiz.

Kalbimiz gibi tertemiz konsolumuzu açtıktan sonra, projemizi oluşturacağımız alana gitmemiz gerekiyor. Ben bu örnekte projemizi masaüstüne oluşturmaki istiyoruz. Bu yüzden de `cd Desktop` ifadesini giriyorum. Buradaki `cd` ifadesinin anlamı: "Change Directory"'dir.

![](https://i.imgur.com/8iEjFxM.png)

İstediğimiz alana gittikten sonra projemizi yüklemek için gerekli Vite kodlarını çalıştırabiliriz.

<br/><br/>

## Adım #2: Kurulum için gerekli komutlar

| NPM kullanıyorsan  | Yarn kullanıyorsan  |  PNPM kullanıyorsan |
| :------------: | :------------: | :------------: |
| `npm create vite@latest`  | `yarn create vite`  | `pnpm create vite`  |

Npm için olan komutu kullandıktan sonra bize projemizin isminin ne olacağını soruyor:

![](https://i.imgur.com/5zbYtw8.png)

Projemizin ismini girip "enter" tuşuna bastıktan sonra bizden bir template yani bir iskelet seçmemizi istiyor. Bu örneğin başrolü Vue. Dolayısıyla Vue'yu seçeceğiz. Bunu da konsolda da belirtildiği gibi aşağı ve yukarı ok tuşlarıyla yapacağız. Ardından "enter" tuşuna basacağız.

![](https://i.imgur.com/kWw4z9P.png)

Bir sonraki adımda ise bize saf JavaScript mi, TypeScript mi, Nuxt mı yoksa özelleştirilebilir bir varyant mı kullanacağımızı soruyor. Biz ise JavaScript'i seçiyoruz.

![](https://i.imgur.com/qkYJniB.png)

<br/><br/>

## Adım #2.1: Kurulum için kısayol komutları
------------


> Önemli Not:
>
> Bu işlemleri tek bir satırda yapabiliriz. Bunun için bir kısayol komutu var. Eğer her şeyi tek seferde halletmek istiyorsan aşağıdaki komutları kullanabilirsin:
>
> **npm 6.x** sürümü için:
> `npm create vite@latest (projenin ismi) --template (template ismi)`
>
> **npm 7+** sürümü için (ekstra - - var):
>`npm create vite@latest (projenin ismi) -- --template (template ismi)`
>
> **yarn** için:
> `yarn create vite (projenin ismi) --template (template ismi)`
>
>**pnpm** için:
>`pnpm create vite (projenin ismi) --template (template ismi)`
>
>Hazır templateleri de şu tabloda veriyorum:

 | JavaScript ile  | TypeScript ile  |
 | :------------: | :------------: |
 | vanilla  | vanilla-ts  |
 | vue  | vue-ts  |
 | react  | react-ts  |
 | preact  | preact-ts  |
 | lit  | lit-ts  |
 | svelte  | svelte-ts  |

>  Hangi teknoloji ile çalışmak istiyorsan, bu tablodaki karşılıklarını yazarak projeyi çabucak kurabilirsin.
> Örnek:
>
>`npm create vite@latest ornek-proje --template react`

------------

<br/><br/>

## Adım #3: Kurulum sonrası gerekli komutlar

Bu işlemlerden sonra projemiz oluşturulmuş oluyor. Proje oluşturulduktan sonra ise bize gerekli adımları belirtiyor.

| <img width="441" height="1"> | |
| :------------: | :------------: |
| Adımlar | Açıklama |
|  `cd vite-test`  | İlk başta girdiğimiz proje isminde bir klasör oluşturuldu. Bu komutla birlikte onun içine giriyoruz.  |
| `npm install`  | Her şeyin hızlı olması adına Vite, içindeki paketleri bir anda yüklemiyor. Biz, üstteki komutla birlikte oluşturduğumuz klasörün içine girip, bu komutla birlikte gerekli paketleri yüklüyoruz. |
| `npm run dev` | Gerekli yüklemeler yapıldıysa, bu komutla birlikte projemizi localhost'ta çalıştırıyoruz. |

Bize söylendiği gibi yapıyor ve `cd vite-test` yazarak klasörümüzün içine gidiyoruz.

![](https://i.imgur.com/hlm58S4.png)

Daha sonra ise `npm install` yazarak ikinci adımı tamamlıyoruz.

![](https://i.imgur.com/2iphyV9.png)

> Bu işlem zaman alabilir. Yükleme hızı donanımdan donanıma değişiklik gösterecektir.

<br/><br/>

## Adım #3.1: Projeyi ayağa kaldırmak (localhost)

Gerekli yüklemelerden sonra ise `npm run dev` diyerek projemizi, localhost'umuzda çalıştırıyoruz.

![](https://i.imgur.com/UCQmsb9.png)

Her şey düzgünce çalıştıysa aşağıdaki gibi bir ekran göreceğiz:

![](https://i.imgur.com/Y1eQIZd.png)

Burada `Local: http://localhost:5173/` ibaresini görüyoruz. Buradaki URL, bizim projemizin URL'si. Bunu kopyalayıp herhangi bir tarayıcıya yapıştırıyoruz ve bizi projenin hazır iskeleti karşılıyor:

![](https://i.imgur.com/DP26CgZ.png)

Baaak, bu da klasör yapısı: :innocent:

![](https://i.imgur.com/gYh5vHb.png)

Hepsi bu kadaaaar.  :innocent: Vite ilgili yapacağımız her şey bu. Gerektiği zamanda kendi config dosyasından ayarlamalar yapabiliriz ancak basitçe her şey bu. Şimdi her zaman olduğu gibi kodlarımızı yazmaya başlayabiliriz.

Eğer anlamadığın bir yer varsa, lütfen takım arkadaşlarından yardım almaktan çekinme.
