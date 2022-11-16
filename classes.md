#Java Sınıfları

(Classes)

Java’da sınıf (class)  kavramını doğada cins isimlere benzetebiliriz. Bir cins kendi başına belirli bir nesne değildir; ancak belirli türden nesnelerin ortak özelliklerini belirten soyut bir kavramdır. Örneğin, ağaç bir cins isimdir. Ama bahçedeki elma-ağacı ya da sokaktaki çınar-ağacı belirli varlıklardır. Onlar, ağaç sınıfının birer nesnesidir (üyesidir). Cinsler alt-cinslere ayrılabilir. Alt-cinsler, üst-cinslerin özelikleri yanında kendilerine has başka özelikler de taşırlar. Örneğin, memeli-hayvanlar geniş bir sınıftır. Filler, kaplanlar, şempanzeler, balinalar, insanlar vb. memeliler sınıfının (üst-sınıf) birer alt-sınıfıdır. Alt-sınıftakiler, üst-sınıfın özeliklerini taşımakla birlikte, birbirlerinden kesinlikle farklıdırlar.  Her cinsin ve her alt-cinsin kendine özgü özelikleri (nitelikler ve davranışlar) vardır. Bu özelikler, onları diğer cinslerden ayırır.

Java’da sınıfları doğadaki cinsler gibi düşürsek, konuyu kavramamız kolaylaşacaktır. Java sınıfı, tıpkı bir cinste olduğu gibi, ortak özelikleri belirlenmiş bir topluluğun adıdır. Bir java sınıfının niteliklerini değişkenlerle (attributes, fields), davranışlarını metotlarla (fonksiyon, procedure) belirleriz. Başka bir deyişle, istediğimiz özeliklerini belirterek bir sınıf (cins-isim) tanımlarız. Bu sınıfın nitelikleri  değişkenlerle (attributes, fields) ve davranışları metotlarla (fonksiyon, procedure) ortaya konulur. Kısaca, bir java sınıfı kendi özniteliklerini belirleyen değişkenleri ve fonksiyonları içeren bir birimdir. Bu nedenle, Pascal ve C gibi yapısal dillerdeki yapı (record, struct) kavramının bir genellemesidir. Record ve struct yalnızca değişkenler içerebilir. Fonksiyon ve procedure’ler onların dışında kalır. Java sınıfı ise, değişkenler yanında fonksiyonları da içeren daha genel bir yapıya sahiptir. Bir sınıf içindeki fonksiyonlar o sınıfın değişkenlerine erişebildiği gibi, farklı sınıflar arasında da iletişim sağlanabilmektedir.

Sınıf ve alt-sınıfların tanımı, bütünüyle programcının gereksemelerine göre yapılabilir. Alt-sınıflardan başka alt-sınıflar üretilebilir. Böylece en üst-sınıftan başlayarak en alt-sınıfa ulaşan hiyerarşik bir yapıya sahip olurlar. En alttaki sınıf, kendisinin üstünde olan bütün sınıfların özniteliklerini taşır. Buna kalıtım (inheritance) özeliği diyoruz. Bu özelik, Java’nın üstün özeliklerinden birisidir ve ilerideki konularda nasıl işe yaradığını göreceğiz.

Java programları sınıf (class) lardan oluşur. Bütün sınıflar aynı yapıya sahiptirler. Aralarındaki farkı yaratan şey, içerdikleri değişkenler ve metotlardır. Bazıları hiç değişken ve/veya metot içermez, bazıları az, bazıları çok değişken ve  metot içerebilir.

Uyarı : Bir sınıftaki değişkenler o sınıfın niteliklerini, metotlar ise o sınıfın davranışlarını belirler. Bu nedenle, sun da dahil olmak üzere bazı kaynaklarda değişken terimi yerine nitelem (attribute), fonksiyon ve procedure yerine de metot terimi kullanılır. Biz de bu derslerde genellikle bu geleneğe uyacağız. Ama, özellikle değişkeni ve fonksiyonu vurgulamak gerektiğinde bu gelenekten biraz sapabileceğiz.

Sınıf (Class) Yapısı

Java’da sınıf (class) yapısı için sözdizimi şöyledir:

      [Erişim_nitelemi] class ad {

            Class’ın tanımı

      }

Yapının açıklaması:

 [Erişim_belirteci](Access-modifier):     Class’a kimlerin erişebileceğini belirten bir nitelemdir. Bu nitelemleri ve yaptıkları işleri yeri geldikçe örnekler üzerinde açıklayacağız.

class               Sınıf tanımında mutlaka kullanılması gereken anahtar bir sözcüktür; derleyiciye bir class tanımı yapıldığını bildirir.

Ad                   Her class’a bir ad verilir. Class adlarını büyük harfle başlatmak bir gelenektir. Buna karşılık, değişken adları, paket adları ve interface adları küçük harfle başlatılır. Böylece, kaynak programa bakan herkes, neyin class olduğunu hemen anlayabilir. Bu java programcıları arasındaki bir sözleşmedir ve bu sözleşmenin java derleyicisi bakımından bir anlamı yoktur. Sözleşme, yalnızca programcıların kaynak programı okuyup anlamasını kolaylaştırır.

{ }                    Class’ın yapısı bu parantezler içinde kurulur; yani class’ın nitelemleri ve metotları tanımlanır. Bunların   nasıl yapıldığını adım adım göreceğiz.

Java dili büyük-küçük harf ayrımına duyarlıdır. Anahtar sözcüklerde bu ayrıma dikkat edilmezse, program derlenemez. Bunun yanında, kaynak programın, okur tarafından kolay anlaşılması için konulmuş bazı kurallar vardır. Bir tür gelenek halini alan bu kurallar, derleyici açısından zorunlu olmasa bile, program yazanların bunlara uyması istenir. Bunlar, java programcıları arsındaki yazısız bir antlaşma hükümleridir.  Böylece, kaynak programı okuyan herkes, programın yapısını daha kolay kavrayabilir. Bu kuralları, yeri geldikçe örnekler üzerinde açıklayacağız. Şimdi, basit birkaç kuralı söylemek gerekiyor.

Uyarı

1.                   Java’da adlar (değişken, metot, class, interface, paket adları) bir karakterle başlar, karakter veya rakamlarla devam edebilir. Her ad tek sözcükten oluşur; yani ad olan sözcük boşluk içeremez. Örneğin, Yolcu 12 Treni  bir ad olamaz. Bunu Yolcu_12_treni ya da Yolcu12Treni gibi yazmak gerekir.

2.                İki ya da daha çok sözcüğün birleştirilmesiyle bir ad yaratılıyorsa, adlar arasına alt-çizgi (_) simgesi konulur ya da bitişik yazılıp sözcüklerin her birisi büyük harfle başlatılabilir. Örnekler: Mavi_Yolcu_Treni, MaviYolcuTreni.

3.                Class_adları büyük harfle başlar, küçük harflerle ya da rakamlarla devam eder. Örnekler:  Tren, Mavi_Tren, Mavi_Yolcu_Treni, MaviYolcuTreni.

4.                Değişken, metot, interface ve paket adları küçük harfle başlar.  Örnekler:  tren, mavi_Tren, mavi_Yolcu_Treni, maviYolcuTreni.

5.                Sabitlenmiş değişkenler büyük harflerle yazılır. Örnek: PI=3.14159.

 

Hemen belirtelim ki, java dili, bir programcının gerekseme duyacağı genel türden class’ları ön-tanımlı olarak içerir. Java’nın içerdiği ve Java API (Application Programmer’s Interface) denilen bu class’ların dökümanları http://java.sun.com/j2se/1.3/docs/api/ web sitesinden her an görülebilir. Programcı bu class’ları doğrudan kullanabildiği gibi, dilerse onların alt-class’larını üretebilir ya da kendi istediği class’ları serbestçe yazabilir. Bu durumuyla, java dili, programcıya olağanüstü kolaylık ve özgürlük sunmaktadır.

Basiti anlamak zordur!

Aşağıdaki class, programcının yazdığı basit bir class’tır. Bu örnek, aslında java dilinin özelliklerini göstermekten daha çok, o özelikleri saklamaktadır. Ama, her dil öğretiminde olduğu gibi, konuya sistematik yaklaşmak yerine pedagojik yaklaşmak daha verimlidir. Bu nedenle, konuyu, basitten karmaşığa giden adımlarla izleyerek, sonunda asıl sistematik yapıya ulaşacağız.

Jprog01 sınıfı, java API kütüphanesinde yer alan java.lang paketi içindeki System class’ını ve java.io paketi içindeki PrintStream alt-class’ını kullanmaktadır. Aşağıdaki açıklamaları izleyebilmeleri için, öğrencilerin java API dokümanlarına bakmaları önerilir.  

Jprog01 class’ı içinde programcının tanımladığı hiçbir değişken veya metot yoktur. Bunun yerine java API ‘den alınan System sınıfını ve main() metodunu kullanmaktadır. Ayrıca main() metodunun çağırdığı System.out.println() fonksiyonu, parametre olarak bir metin (string) içerdiği için, String class’ını çağırmaktadır.  Bütün bu işleri, java kendiliğinden yapmaktadır. Programcıya düşen tek iş aşağıdaki basit programı yazmaktır.  Bu program, aslında bir class yazmaktan ibarettir.

1.  class Jprog01

2.  {

3.    public static void main(String[] args)

4.      {

5.           System.out.println("Ankara Türkiye\’nin başkentidir.");

6.      }

7.  }

Bu programın çıktısı şudur:

                Ankara Türkiye’nin başkentidir.

Çok basit görünen bu programın açıklanması zor değilse bile, çok uzundur ve java programının bir çok özeliklerini taşır. Bir java programının (sınıfının) nasıl çalıştığını göstereceği için bu uzun açıklamaya girmekte yarar görüyoruz. Java'ya yeni başlayan öğrenciler bu açıklamayı anlayamazlarsa üzülmesinler. Ama dersler ilerledikten sonra, geri dönüp mutlaka okumalı ve her satırını anlamalıdırlar. Çünkü, bu açıklamaları kavrayamayan öğrenci, javayı henüz kavrayamamış demektir.

1.     Satır: Her java programı bir sınıf (class) dır. O nedenle, hepsi class anahtar sözcüğünü izleyen bir ad ile başlar.  (örneğimiz için  class Jprog01 dir). Bazan class anahtar sözcüğünün önüne belirteçler gelebilir. Onları ileride yeri geldikçe açıklayacağız.

2.     Satır: Java sınıfının tanımı { } parantezi içinde yer alan ana blok içine konur. 2-inci satırda açılan { parantezi 7-inci satırda kapanmaktadır. Bu ana bloktur. Bu blokun içine başka bloklar girebilir. Her blokun kendine özgü { } parantezleri vardır. Açılan her parantez kapatılmalıdır. İç-içe bloklar oluşturulduğunda, parantezler en içten başlayarak dışa doğru karşılıklı olarak eşleşirler. Örnekteki 3-üncü satırda başlayan iç blok 6-ıncı satırda bitmektedir. 3 ile 6-ıncı satırlarda yer alan { } parantezler birbirini eşler ve bir iç-blok oluşturur. 2-inci ve 7-inci satırlardaki { } parantezleri birbirine eştir ve en dış bloku (ana blok) oluşturur. Bir sınıf içinde istenildiği kadar iç-içe bloklar oluşturulabileceği gibi, birbirinin içinde olmayan bloklar da oluşturulabilir. Ama bütün bloklar, sınıfın sınırlarını belirleyen ana blok içinde olmak zorundadır.

3.     Satır:  Bu satır main() adlı bir metot (fonksiyon) tanımlamaktadır. public saklı sözcüğü, bir erişim belirtkesidir, bu metoda her sınıfın ulaşabileceğini belirtir. Gündelik konuşmamızdaki halka açık deyimine benzer bir işleve sahiptir. Herkes ona erişebilir.  static saklı sözcüğünün java'da çok işlevsel bir anlamı vardır. Şimdilik, bu belirtkenin, main() metodu için ana bellekte bir yer ayırdığını ve onun başka bir kopyasının yapılmasına izin vermediğini söylemekle yetinelim.  static saklı sözcüğünün yaptığı işin ayrıntılarını zamanla daha iyi kavrayacağız.  void saklı sözcüğü  main() metodunun (fonksiyonunun) değer bölgesinin olmadığını (boş küme) belirtir. Bu metot bir iş yapar, ama bir değer almaz. Bazı java metotlarının değer bölgesi vardır, bazılarının yoktur (boştur). Son olarak  main(String[] args) simgelerini açıklayalım. Her dilde olduğu gibi, java'da da sınıfın her üyesinin bir adı vardır.  3-üncü satır bir metot tanımlamaktadır. Bu metot elbette sınıfın bir üyesi olmaktadır ve bir adı olmalıdır. Bu metodun adı  main()'dir. Java'da bütün uygulama programları bir main() metodu ile çalışır. Her uygulama programında yalnızca bir tane main() metodu vardır ve daima 3-üncü satırdaki gibi yazılır. Tabii, her uygulama programı farklı işler yapacağından, hepsinin main() metodunun tanımı farklı olacaktır. Bu metodun tanımı main(){...}'e ait {...}bloku içinde yapılır. Ama bütün main()metotlarının adları, nitelemleri ve parametre türü hepsinde aynıdır. Parantez içindeki  String[] args ifadesi bir değişken (parametre) bildirimidir. Metotların değişkenlerine parametre diyoruz. Böylece, bu değişkenleri sınıf ve blok içlerinde tanımlanan öteki değişkenlerden ayırmamız kolaylaşıyor. Değişkenin adı args , tipi ise String[]'dir. String Java'da metin (text) işlemlerini yapmamızı sağlayan kullanışlı bir sınıf (class) dır. Bununla çok sık karşılaşacak ve onun bir çok hünerini zamanla öğreneceğiz. Şimdilik, Pascal ve C gibi dillerde karakter arraylari olarak yapılan metin (string) işlemlerini java'da String sınıfı ile yaptığımızı söyleyelim. String 'in sonuna [] köşeli parantezleri eklenince, elde edilen String[] simgesi, öğeleri  String tipinden olan bir dizi (array) belirtir.  Demek ki  args değişkeni öğeleri String tipinden olan bir arraydir.  Bunu daha çok açıklamak için, gerekli ön bilgilere sahip olmayı sabırla beklemeliyiz.           

4.     Satır:   Bu satırda  metodunun bloku {  parantezi ile başlamaktadır. Blok 6-ıncı satırda bitmektedir, bir iç bloktur. Bu iç blokta main metodunun tanımı yapılmaktadır.

5.     Satır: Bu satırın açıklanması için gerekli olan bilgileri java API dökümanlarından alabiliriz. Dökümanlarda java.lang paketinin içine bakarsak, System sınıfını (class) görebiliriz.

java.lang.Object

  java.lang.System

 

public final class System

extends Object

 

Dördüncü satırdaki public erişim belirteci System sınıfına her sınıfın erişebileceğini söylüyor. final nitelemesi ise, System sınıfının değiştirilemez (sabit) olduğunu söylüyor. extends Object ifadesi, System sınıfının Object sınıfından üretildiğini söylüyor; yani onun bir alt sınıfı olduğunu söylüyor. Object sınıfı bütün sınıfların üst-sınıfıdır.

Açıklamayı sürdürebilmek için, önce programın üçüncü satırında yer alan out ‘un ne olduğunu sonra da println() metodunun tanımını bulmalıyız. 

Bunun için, API dökümanında java.lang paketi içinde yer alan System sınıfının değişkenlerine (attributes, fields) bakalım. System sınıfının PrintStream tipinden err ve out adlı iki değişkeni ile InputStream  tipinden in adlı bir değişkeni olduğunu görürüz. Adlarından da anlaşılacağı üzere, out değişkeni çıkış akımlarını, in değişkeni giriş akımlarını düzenler. err değişkeni ise, oluşabilecek hataları bildirir. API dökümanında out değişkenine tıklarsak, onun açık tanımını görebiliriz: 

public static final PrintStream out

Bu değişkenin aldığı public static final nitemleri , sırasıyla, şu anlamlara gelir:

public    out değişkeni herkese açıktır. Her class bu değişkene ulaşabilir.

static    out değişkeni için sistem ana bellekte bir yer açmıştır ve kullanılmaya hazırdır. Onu ayrıca programcının yaratmasına gerek yoktur. Doğrudan kullanılabilir durumdadır.

final       out değişkeni sabittir, program içinde değeri değiştirilemez. 

System sınıfı içindeki out değişkeni static olduğundan, ona erişmek için

System.out                                                    (1)

yazmak yeterlidir. Son olarak, programın üçüncü satırında yer alan out.println() metodunun tanımını aramalıyız.  Bunun için out değişkeninin ait olduğu PrintStream  sınıfını bulmalıyız. Bu sınıf java.io paketi içindedir ve hiyerarşik tanımı şöyledir:

java.lang.Object

  java.io.OutputStream

      java.io.FilterOutputStream

          java.io.PrintStream

 

Bu hiyerarşiden anlaşılacak şey, PrintStream sınıfının Object sınıfından türetilen üçüncü aşamadaki bir alt-sınıf olduğudur. Bu sınıfın tanımı, hiyerarşik olarak şu tanımlardan çıkar:

public abstract class OutputStream

extends Object

 

public class FilterOutputStream

extends OutputStream

public class PrintStream

extends FilterOutputStream

API dökümanında  PrintStream sınıfının metotları arasında

        public void println(String x)

adlı bir metodu olduğunu görürüz. Bu metot, parametre olarak aldığı bir x metnini standart çıkışa (ekran) yazar. Parametre olarak tırnak içinde yazdığımız

"Ankara Türkiye\’nin başkentidir."

metni, java için String tipinden bir parametredir (String tipinden x değişkenidir). println() metodunun görevi bu parametreyi (nesneyi) byte akışı biçiminde standart çıkışa (ekran) göndermektir.  Böylece,

System.out.println("Ankara Türkiye\’nin başkentidir.")

deyimi bizim için bir anlam kazanmıştır.  

 
