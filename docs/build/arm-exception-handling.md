---
title: ARM özel durum Işleme
ms.date: 07/11/2018
ms.assetid: fe0e615f-c033-4ad5-97f4-ff96af45b201
ms.openlocfilehash: c55baf453c1879f1e0a857cc746bba7802d69f88
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303280"
---
# <a name="arm-exception-handling"></a>ARM özel durum Işleme

ARM 'de Windows, zaman uyumsuz donanım tarafından oluşturulan özel durumlar ve zaman uyumlu yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme mekanizmasını kullanır. Dile özgü özel durum işleyicileri dil Yardımcısı işlevleri kullanılarak Windows yapılandırılmış özel durum işlemenin üzerine kurulmuştur. Bu belge, ARM 'de Windows 'da özel durum işlemeyi ve Microsoft ARM Assembler ve MSVC derleyicisi tarafından oluşturulan kod tarafından kullanılan dil yardımcılarını açıklar.

## <a name="arm-exception-handling"></a>ARM özel durum Işleme

ARM 'de Windows, [yapılandırılmış özel durum işleme](/windows/win32/debug/structured-exception-handling) (SEH) sırasında yığın geri sarımı denetlemek için *bırakma kodlarını* kullanır. Geriye doğru izleme kodları, yürütülebilir görüntünün. xdata bölümünde depolanan baytların bir dizisidir. İşlev işlem ve epıg kodu, bir soyut bir şekilde işlev işlemini anlatmaktadır, böylece bir işlevin prolog 'nin etkileri çağıranın yığın çerçevesine geri sarıya hazırlanmaya hazırlanmak üzere geri alınabilir.

ARM EABI (katıştırılmış uygulama ikili arabirimi), geriye doğru izleme kodları kullanan bir özel durum izleme modeli belirtir, ancak Windows 'ta SEH geri sarma için yeterli değildir bir işlevin epıg. Windows ayrıca, bir sargı denetimini, ARM EABı 'da birleştirilmiş olan işlev düzeyinde geriye doğru ve dile özgü kapsam geri sarıya ayırır. Bu nedenlerden dolayı ARM 'de Windows, geriye doğru izleme verileri ve yordamı için daha fazla ayrıntı belirler.

### <a name="assumptions"></a>Varsayımlar

ARM 'de Windows için yürütülebilir görüntüler taşınabilir yürütülebilir (PE) biçimini kullanır. Daha fazla bilgi için bkz. [MICROSOFT PE ve COFF belirtimi](https://go.microsoft.com/fwlink/p/?linkid=84140). Özel durum işleme bilgileri görüntünün. pdata ve. xdata bölümlerinde depolanır.

Özel durum işleme mekanizması ARM 'de Windows için ABı izleyen kod hakkında bazı varsayımlar yapar:

- Bir işlevin gövdesinde bir özel durum oluştuğunda, bu, prolog işlemlerinin geri alınmadığına veya epıg işlemlerinin ileri bir şekilde gerçekleştirildiğine önemli değildir. Her ikisi de özdeş sonuçlar üretmelidir.

- Prologues ve epıtes birbirini yansıtmaya eğilimlidir. Bu, geriye doğru izlemeyi anlatmak için gereken meta verilerin boyutunu azaltmak için kullanılabilir.

- İşlevler görece küçük olma eğilimindedir. Çeşitli iyileştirmeler, verilerin verimli bir şekilde paketlenmesi için bunu kullanır.

- Bir durum, bir başlangıç üzerine yerleştirilmişse, bu durum, epıg 'deki her yönergeye eşit olarak uygulanır.

- Yığın işaretçisi (SP), prolog 'daki başka bir kasada kaydedildiyse, bu kayıt işlevin tamamında değişmeden kalmalıdır, böylece özgün SP herhangi bir zamanda kurtarılabilir.

- SP başka bir kayda kaydedilmediği takdirde, tüm düzenleme işlemi tamamen bir başlangıç ve epıg dahilinde gerçekleşmelidir.

- Herhangi bir yığın çerçevesini geriye doğru bırakmak için bu işlemler gereklidir:

  - R13 (SP) öğesini 4 baytlık artışlarla ayarlayın.

  - Bir veya daha fazla tamsayı kaydı açılır.

  - Bir veya daha fazla VFP (sanal kayan nokta) kaydı açılır.

  - Rastgele bir yazmaç değerini R13 (SP) öğesine kopyalayın.

  - Küçük bir azaltma sonrası işlemi kullanarak SP 'yi yığından yükleyin.

  - İyi tanımlanmış birkaç çerçeve türünden birini ayrıştırın.

### <a name="pdata-records"></a>. pdata kayıtları

Bir PE biçimli görüntüde. pdata kayıtları, yığın işleme işlevinin her birini tanımlayan sabit uzunluklu öğelerin sıralı dizisidir. Diğer işlevleri çağırmayan işlevler olan yaprak işlevleri, yığını işlediklerinde. pdata kayıtları gerektirmez. (Yani, yerel depolama gerektirmez ve geçici olmayan kayıtları kaydetmek veya geri yüklemek zorunda kalmaz.). Bu işlevlerin kayıtları, alan kazanmak için. pdata bölümünde atlanabilir. Bu işlevlerden birindeki bir geriye doğru izleme işlemi, çağrıyı yapana ilerlemek için yalnızca bağlantı kaydındaki (LR) geri dönüş adresini program sayacına (PC) kopyalayabilir.

ARM için tüm. pdata kayıtları 8 bayt uzunluğundadır. Bir kaydın genel biçimi, işlevin göreli sanal adresini (RVA) ilk 32 bitlik sözcüğe, sonra da değişken uzunluklu bir. xdata bloğuna yönelik bir işaretçi ya da kurallı bir işlevi açıklayan bir paketlenmiş sözcük içeren ikinci bir kelime ile başlar Bu tabloda gösterildiği gibi, geriye doğru sarma sırası:

|Sözcük boşluğu|Bits|Amaç|
|-----------------|----------|-------------|
|0|0-31|*Işlev başlangıç RVA* , işlevin başlangıcına ait 32 bitlik RVA 'ya sahiptir. İşlev Thumb kodu içeriyorsa, bu adresin düşük bitinin ayarlanması gerekir.|
|1\.|0-1|*Bayrak* , ikinci. pdata sözcüğünün kalan 30 bitini nasıl yorumlayacağını belirten 2 bitlik bir alandır. *Bayrak* 0 ise, kalan bit bir *özel durum bilgisi RVA* (düşük iki bit örtülü 0) oluşturur. *Bayrak* sıfır olmayan bir değer ise, kalan bitler *paketlenmiş bir geriye doğru izleme veri* yapısı oluşturur.|
|1\.|2-31|*Özel durum BILGISI RVA* veya *paketlenmiş bırakma verileri*.<br /><br /> *Özel durum BILGISI RVA* ,. xdata bölümünde depolanan değişken uzunluklu özel durum bilgisi yapısının adresidir. Bu veriler 4 bayt hizalı olmalıdır.<br /><br /> *Paketlenmiş geriye doğru Izleme verileri* , bir işlevden geri dönmek için gereken işlemlerin sıkıştırılmış bir açıklamasıdır; kurallı bir form kabul edilir. Bu durumda, hiçbir. xdata kaydı gerekli değildir.|

### <a name="packed-unwind-data"></a>Paketlenmiş geriye doğru Izleme verileri

Prologues ve epıtes işlevleri aşağıda açıklanan kurallı biçimde izlenen işlevler için, paketlenmiş geriye doğru izleme verileri kullanılabilir. Bu,. xdata kaydına yönelik gereksinimi ortadan kaldırır ve geriye doğru izleme verileri sağlamak için gereken alanı önemli ölçüde azaltır. Kurallı işlem ve epingues, özel durum işleyicisi gerektirmeyen basit bir işlevin ortak gereksinimlerini karşılayacak şekilde tasarlanmıştır ve kurulum ve test işlemlerini standart sırada gerçekleştirir.

Bu tabloda, paketlenmiş geri bırakma verilerine sahip bir. pdata kaydının biçimi gösterilmektedir:

|Sözcük boşluğu|Bits|Amaç|
|-----------------|----------|-------------|
|0|0-31|*Işlev başlangıç RVA* , işlevin başlangıcına ait 32 bitlik RVA 'ya sahiptir. İşlev Thumb kodu içeriyorsa, bu adresin düşük bitinin ayarlanması gerekir.|
|1\.|0-1|*Bayrak* , bu anlamlara sahip 2 bitlik bir alandır:<br /><br />-00 = paketlenmiş bırakma verileri kullanılmıyor; kalan BITS. xdata kaydına işaret.<br />-01 = paketlenmiş bırakma verileri.<br />-10 = işlevin hiçbir şekilde kabul edildiği varsayılabileceği paketlenmiş geri açılım verileri. Bu, işlevin başlangıcına bitişik olmayan işlev parçalarını açıklamak için yararlıdır.<br />-11 = ayrılmış.|
|1\.|2-12|*Işlev uzunluğu* , tüm işlevin uzunluğunu 2 ' ye bölünen bayt cinsinden sağlayan 11 bitlik bir alandır. İşlev 4K bayttan büyükse, bunun yerine tam bir. xdata kaydı kullanılmalıdır.|
|1\.|13-14|*Ret* , işlevin nasıl dönüşdiğini belirten 2 bitlik bir alandır:<br /><br />-00 = pop {PC} aracılığıyla geri dön (Bu durumda *L* bayrağı biti 1 olarak ayarlanmalıdır).<br />-01 = 16 bit dal kullanarak döndürün.<br />-10 = 32 bitlik bir dal kullanarak geri döndürün.<br />-11 = hiç bir ön uç yok. Bu, yalnızca bir prolog içerebilen, ancak epıg başka bir yerde olan bitişik olmayan bir işlev parçasını açıklamak için yararlıdır.|
|1\.|15|*H* , "ana" işlevin (R0-R3), işlevin başlangıcında göndererek (-) işlevinin kayıt yapıp kullanmadığını belirten 1 bitlik bir bayraktır ve döndürmeden önce 16 baytlık yığını kaldırır. (0 = ana kayıt kayıtları, 1 = ev kayıtları.)|
|1\.|16-18|*Reg* , son kaydedilen geçici kayıt dizinini gösteren 3 bitlik bir alandır. *R* biti 0 ise, yalnızca tamsayı Yazmaçları kaydedilir ve R4-RN aralığında olduğu varsayılır; burada N, 4 + *reg*' e eşittir. *R* bit 1 ise, yalnızca kayan nokta kayıtları kaydedilir ve D8-DN aralığında oldukları varsayılır; burada N, 8 + *reg*' e eşittir. *R* = 1 ve *reg* = 7 ' nin özel birleşimi hiçbir kayıt kaydedilmez.|
|1\.|19|*R* , kayıtlı geçici kayıtların tamsayı Yazmaçları (0) veya kayan nokta Yazmaçları (1) olup olmadığını gösteren 1 bitlik bir bayraktır. *R* 1 olarak ayarlanmışsa ve *reg* alanı 7 olarak ayarlanırsa, geçici olmayan kayıtlar itilmedi.|
|1\.|20|*L* , Işlevin, *reg* alanı tarafından belirtilen DIĞER yazmaçlarla birlikte g/geri yükleme yapıp kullanmadığını belirten 1 bitlik bir bayrak. (0 = kaydetme/geri yükleme değil, 1 = kaydet/geri yükle.)|
|1\.|21|*C* , işlevin hızlı yığın yürümesi için bir çerçeve zinciri ayarlamaya yönelik ek yönergeler içerip içermediğini belirten 1 bitlik bir bayraktır (1) veya (0). Bu bit ayarlandıysa, R11, kaydedilen tamsayı olmayan kayıtların listesine örtülü olarak eklenir. ( *C* bayrağı kullanılırsa aşağıdaki kısıtlamalara bakın.)|
|1\.|22-31|*Stack ayarlaması* , bu işlev için ayrılan yığının bayt sayısını belirten 10 bitlik bir alandır. Ancak, yalnızca 0x000-0x3F3 arasındaki değerler doğrudan kodlanabilir. 4044 bayttan fazlasını ayıran işlevlerin tam bir. xdata kaydı kullanması gerekir. *Yığın ayar* alanı 0x3F4 veya daha büyükse, düşük 4 bit özel anlam taşır:<br /><br />-Bit 0-1, yığın ayarlamasının (1-4) eksi 1 kelimelerin sayısını belirtir.<br />-Bit 2, bu ayarlamayı gönderim işleminde birleştirirse 1 olarak ayarlanır.<br />Epııte bu ayarlamayı bu ayarlamayı bir araya alıyorsa-bit 3, 1 olarak ayarlanır.|

Yukarıdaki kodlamalarda olası artıklıkları nedeniyle bu kısıtlamalar geçerlidir:

- *C* bayrağı 1 olarak ayarlandıysa:

   - Çerçeve zinciri hem R11 hem de LR gerektirdiğinden *L* bayrağı da 1 olarak ayarlanmalıdır.

   - R11, *reg*tarafından tanımlanan kayıt kümesine dahil edilmemelidir. Diğer bir deyişle, R4-R11 itilmesi durumunda *reg* yalnızca r4-r10 ' i tanımlıyor çünkü *C* bayrağı R11 ' ı gösterir.

- *Ret* alanı 0 olarak ayarlandıysa, *L* bayrağının 1 olarak ayarlanması gerekir.

Bu kısıtlamaları ihlal etmek desteklenmeyen bir diziye neden olur.

Aşağıdaki tartışmanın amaçları doğrultusunda, *yığın ayarlamalarından*iki sözde bayrak türetilir:

- *PF* veya "prolog katlaması", *yığın Ayarlanmesinin* 0x3F4 veya daha büyük olduğunu ve bit 2 ' nin ayarlandığını gösterir.

- *EF* veya "epıg katlaması", *yığın ayarlamalarının* 0x3F4 veya daha büyük ve bit 3 ' ün ayarlandığını gösterir.

Kurallı işlevler için prologues, en fazla 5 yönerge içerebilir (3A ve 3B birbirini dışlamalı olduğuna dikkat edin):

|Yönergenin|Şu durumlarda işlem kodu varsayılır:|Boyut|Ml|Bırakma kodları|
|-----------------|-----------------------------------|----------|------------|------------------|
|1\.|*H*= = 1|16|`push {r0-r3}`|04|
|2|*C*= = 1 veya *L*= = 1 veya *R*= = 0 ya da PF = = 1|16/32|`push {registers}`|80-BF/D0-DF/EC-ED|
|3A@@|*C*= = 1 ve (*L*= = 0 ve *R*= = 1 ve PF = = 0)|16|`mov r11,sp`|C0-CF/FB|
|3B|*C*= = 1 ve (*L*= = 1 veya *R*= = 0 veya PF = = 1)|32|`add r11,sp,#xx`|FC|
|4|*R*= = 1 ve *reg* ! = 7|32|`vpush {d8-dE}`|E0-E7|
|5|*Stack ayarla* ! = 0 ve PF = = 0|16/32|`sub sp,sp,#xx`|00-7F/E8-EB|

Yönerge 1, *H* bit 1 olarak ayarlandıysa her zaman vardır.

Çerçeve zincirlemesini ayarlamak için, *C* bit ayarlandıysa yönerge 3A veya 3B vardır. R11 ve LR dışında bir kayıt yoksa, 16 bit `mov`. Aksi takdirde, 32 bitlik bir `add`.

Katsız bir ayarlama belirtilirse, yönerge 5 açık yığın ayarlamadır.

Yönergeler 2 ve 4, bir gönderme gerekli olup olmadığına göre ayarlanır. Bu tablo, *C*, *L*, *R*ve *PF* alanlarına göre hangi yazmaçların kaydedileceğini özetler. Her durumda, *N* , *reg* + 4 ' e eşittir, *E* de *reg* + 8 ' e eşittir ve *S* şuna eşittir (~*Stack ayarlaması*) & 3.

|C|L|R|PF|Gönderilen tamsayı Yazmaçları|VFP kayıtları gönderildi|
|-------|-------|-------|--------|------------------------------|--------------------------|
|0|0|0|0|R4-r*N*|yok|
|0|0|0|1\.|r*S*-r*N*|yok|
|0|0|1\.|0|yok|D8-d*E*|
|0|0|1\.|1\.|r*S*-R3|D8-d*E*|
|0|1\.|0|0|R4-r*N*, LR|yok|
|0|1\.|0|1\.|r*S*-r*N*, LR|yok|
|0|1\.|1\.|0|LR|D8-d*E*|
|0|1\.|1\.|1\.|r*S*-R3, LR|D8-d*E*|
|1\.|0|0|0|R4-r*N*, R11|yok|
|1\.|0|0|1\.|r*S*-r*N*, R11|yok|
|1\.|0|1\.|0|r11|D8-d*E*|
|1\.|0|1\.|1\.|r*S*-R3, R11|D8-d*E*|
|1\.|1\.|0|0|R4-r*N*, R11, LR|yok|
|1\.|1\.|0|1\.|r*S*-r*N*, R11, LR|yok|
|1\.|1\.|1\.|0|R11, LR|D8-d*E*|
|1\.|1\.|1\.|1\.|r*S*-R3, R11, LR|D8-d*E*|

Kurallı işlevler için epıtes benzer bir biçimde, ancak ters ve bazı ek seçeneklerle birlikte izler. Epıg en fazla 5 yönerge uzunluğunda olabilir ve kendi formu, her zaman bir başlangıç biçimi tarafından tamamen dikte edilir.

|Yönergenin|Şu durumlarda işlem kodu varsayılır:|Boyut|Ml|
|-----------------|-----------------------------------|----------|------------|
|6|*Stack ayarla*! = 0 ve *EF*= = 0|16/32|`add   sp,sp,#xx`|
|7|*R*= = 1 ve *reg*! = 7|32|`vpop  {d8-dE}`|
|8|*C*= = 1 veya (*L*= = 1 ve *H*= = 0) ya da *R*= = 0 veya *EF*= = 1|16/32|`pop   {registers}`|
|9A|*H*= = 1 ve *L*= = 0|16|`add   sp,sp,#0x10`|
|9B|*H*= = 1 ve *L*= = 1|32|`ldr   pc,[sp],#0x14`|
|10A|*Ret*= = 1|16|`bx    reg`|
|10B|*Ret*= = 2|32|`b     address`|

Yönerge 6, katsız bir düzeltme belirtilmişse açık yığın ayarlamadır. *PF* , *EF*'ten bağımsız olduğundan, yönerge 5 ' in 6 ' dan veya bunun tersi olmadan kullanılabilmesi mümkündür.

7\. ve 8. yönergeler, yığından hangi yazmaçların geri yüklendiğini belirleyen aynı mantığı kullanır, ancak bu iki değişiklikle: ilk olarak, *PF*'Nin yerine *EF* kullanılır; İkincisi, *ret* = 0 ise, kayıt LISTESINDE LR bilgisayar ile değiştirilmiştir ve epıte sona erer.

*H* ayarlandıysa, her iki yönerge 9A veya 9B vardır. Of yönergesi, *l* 0 olduğunda, LR 'in yığında olmadığını belirtmek için kullanılır. Bu durumda, yığın el ile ayarlanır ve açık bir dönüş belirtmek için *ret* 1 veya 2 olmalıdır. Yönerge 9B, *L* 1 olduğunda, ön tarihte erken bir başlangıç olduğunu göstermek ve yığını aynı anda döndürmek ve ayarlamak için kullanılır.

Epıg zaten bitdiyse, bir 16 bit veya 32 bitlik dalı, *ret*değerine göre göstermek için, her iki yönerge 10A veya 10B vardır.

### <a name="xdata-records"></a>. xdata kayıtları

Paketlenmiş bırakma biçimi, bir işlevin geri sarılini anlatmak için yetersizse, değişken uzunluklu bir. xdata kaydı oluşturulmalıdır. Bu kaydın adresi. pdata kaydının ikinci sözcüğündeki saklanır. . Xdata biçimi, dört bölümden oluşan, paketlenmiş değişken uzunlukta bir kelime kümesidir:

1. . Xdata yapısının genel boyutunu açıklayan ve anahtar işlev verileri sağlayan 1 veya 2 sözcüklü bir üst bilgi. İkinci kelime yalnızca *Epıg Count* ve *Code Words* alanlarının her ikisi de 0 olarak ayarlandığında vardır. Alanlar bu tabloda bölünür:

   |Word|Bits|Amaç|
   |----------|----------|-------------|
   |0|0-17|*Işlev uzunluğu* , işlevin toplam uzunluğunu bayt cinsinden belirten ve 2 ' ye bölünen 18 bitlik bir alandır. Bir işlev 512 KB 'tan büyükse, işlevi anlatmak için birden çok. pdata ve. xdata kaydı kullanılmalıdır. Ayrıntılar için bu belgenin büyük Işlevler bölümüne bakın.|
   |0|18-19|Sunucular *, kalan* XData 'ın sürümünü açıklayan 2 bitlik bir alandır. Şu anda yalnızca sürüm 0 tanımlı; 1-3 değerleri ayrılmıştır.|
   |0|20|*X* , varlık (1) veya Devamsızlık (0) özel durum verilerinin olduğunu gösteren 1 bitlik bir alandır.|
   |0|21|*E* , tek bir ön uç tanımlayan bilgilerin, daha sonra ek kapsam sözcükleri gerektirmek yerine üst bilgiye (1) paketlendiğini belirten 1 bitlik bir alandır (0).|
   |0|22|*F* , bu kaydın bir işlev parçasını (1) veya tam işlevi (0) açıklar olduğunu gösteren 1 bitlik bir alandır. Bir parça, hiçbir işlem olmaması ve tüm prolog işlemenin yoksayılması anlamına gelir.|
   |0|23-27|*Epıg sayısı* , *E* -bit durumuna bağlı olarak iki anlamı olan 5 bitlik bir alandır:<br /><br /> - *E* 0 ise, bu alan 3. bölümde açıklanan toplam özel durum kapsamları sayısıdır. İşlevde 31 ' den fazla kapsam varsa, bu alan ve *kod kelimeleri* alanı her ikisi de bir uzantı sözcüğünün gerekli olduğunu göstermek için 0 olarak ayarlanmalıdır.<br />- *E* 1 ise, bu alan tek başına bir ön izleme kodunun dizinini tanımlar.|
   |0|28-31|*Kod sözcükleri* , Bölüm 4 ' teki tüm bırakma kodlarını içermesi için gereken 32 bitlik sözcüklerin sayısını belirten 4 bitlik bir alandır. 63 ' den fazla bırakma kodu baytı için 15 ' ten fazla sözcük gerekliyse, bir uzantı sözcüğünün gerekli olduğunu göstermek için bu alanın ve *Epıg Count* alanının her ikisi de 0 olarak ayarlanmalıdır.|
   |1\.|0-15|*Genişletilmiş* ön ek sayısı, alışılmadık çok sayıda epıte daha fazla alan sağlayan 16 bitlik bir alandır. Bu alanı içeren uzantı sözcüğü yalnızca ilk üstbilgi kelimesinin *Epıg Count* ve *Code Words* alanlarının her ikisi de 0 olarak ayarlandığında bulunur.|
   |1\.|16-23|*Genişletilmiş kod sözcükleri* , alışılmadık çok sayıda bırakma kodu sözcüklerini kodlamak için daha fazla alan sağlayan 8 bitlik bir alandır. Bu alanı içeren uzantı sözcüğü yalnızca ilk üstbilgi kelimesinin *Epıg Count* ve *Code Words* alanlarının her ikisi de 0 olarak ayarlandığında bulunur.|
   |1\.|24-31|Ayrılmış|

1. Özel durum verileri (üstbilgideki *E* biti 0 olarak ayarlandıysa), bir sözcüğe paketlenmiş ve başlangıç sapmasını artırma sırasına göre depolanan epıg kapsamları hakkında bilgi listesidir. Her kapsam şu alanları içerir:

   |Bits|Amaç|
   |----------|-------------|
   |0-17|*Epıg başlangıç boşluğu* , başlangıç sayısının, işlevin başlangıcına göre 2 ' ye bölünen bayt cinsinden sayısını açıklayan 18 bitlik bir alandır.|
   |18-19|*Res* , gelecekteki genişlemeye ayrılmış 2 bitlik bir alandır. Değeri 0 olmalıdır.|
   |20-23|*Koşul* , epıg 'nin yürütüldüğü koşulu veren 4 bitlik bir alandır. Koşulsuz olarak, "Always" belirten, 0xE olarak ayarlanmalıdır. (Epıg tamamen koşullu veya tamamen koşulsuz olmalıdır ve Thumb-2 modunda, epıg, It Opcode 'dan sonraki ilk yönergeyle başlar.)|
   |24-31|*Epıg başlangıç dizini* , bu ön eki açıklayan ilk bırakma kodunun bayt dizinini gösteren 8 bitlik bir alandır.|

1. Epıg kapsamları listesi oluşturulduktan sonra, bu makaledeki geriye doğru Izleme kodları bölümünde ayrıntılı olarak açıklanan bırakma kodlarını içeren bir bayt dizisi gelir. Bu dizi, sonda en yakın tam sözcük sınırına doldurulur. Baytlar, küçük endian modunda doğrudan getiribilecekleri şekilde küçük endian sırasıyla depolanır.

1. Başlıktaki *X* alanı 1 ise, geriye doğru izleme kodu baytları, özel durum işleyicisi bilgileri izler. Bu, özel durum işleyicisinin adresini içeren bir *özel durum IŞLEYICI RVA* ve ardından, özel durum işleyicisi için gereken veri miktarı (değişken uzunluklu) tarafından hemen oluşur.

. Xdata kaydı, izleyen ve değişken boyutlu özel durum verilerinin uzunluğunu dahil değil, ilk 8 baytı getirmek ve kaydın tam boyutunu hesaplamak mümkün olacak şekilde tasarlanmıştır. Bu kod parçacığı, kayıt boyutunu hesaplar:

```cpp
ULONG ComputeXdataSize(PULONG *Xdata)
{
    ULONG EpilogueScopes;
    ULONG Size;
    ULONG UnwindWords;

    if ((Xdata[0] >> 23) != 0) {
        Size = 4;
        EpilogueScopes = (Xdata[0] >> 23) & 0x1f;
        UnwindWords = (Xdata[0] >> 28) & 0x0f;
    } else {
        Size = 8;
        EpilogueScopes = Xdata[1] & 0xffff;
        UnwindWords = (Xdata[1] >> 16) & 0xff;
    }

    if (!(Xdata[0] & (1 << 21))) {
        Size += 4 * EpilogueScopes;
    }
    Size += 4 * UnwindWords;
    if (Xdata[0] & (1 << 20)) {
        Size += 4;
    }
    return Size;
}
```

Prolog ve her bir epıg 'nin bırakma kodlarına bir dizini olsa da, tablo aralarında paylaşılır. Hepsi aynı bırakma kodlarını paylaşabildiklerinden, yaygın olmayan bir durumdur. Belirtilen en büyük dizin 255 olduğundan ve belirli bir işlev için mümkün olan toplam bırakma kodu sayısını sınırladığından, bu durum için derleyici yazıcılarının iyileştirmenize önerilir.

### <a name="unwind-codes"></a>Bırakma kodları

Geriye doğru izleme kodları dizisi, işlemin geri alınması gereken sırada, prolog 'nin etkilerini tam olarak nasıl geri alınacağını açıklayan bir yönerge dizileri havuzudur. Geriye doğru izleme kodları, bayt dizesi olarak kodlanan bir mini yönerge kümesidir. Yürütme tamamlandığında, çağırma işlevine döndürülen adres, LR kaydına, geçici olmayan tüm Yazmaçları ise işlevin çağrıldığı zaman değerlerine geri yüklenir.

Özel durumların yalnızca bir işlev gövdesinde gerçekleşmesi ve bir prolog ya da epinin içinde hiç olması garanti edildiği durumlarda, yalnızca bir geriye doğru sıralama işlemi gereklidir. Ancak, Windows unsargı modeli kısmen yürütülen bir prolog veya epıg içinden geriye doğru izleme olanağı gerektirir. Bu gereksinime uyum sağlamak için, geriye doğru izleme kodları, prolog ve EPG 'deki ilgili işlem koduna yönelik belirsiz bir bire bir eşlemeye sahip olacak şekilde dikkatlice tasarlanmıştı. Bu çeşitli etkilere sahiptir:

- Bırakma kodlarının sayısını sayarak, prolog ve epıg 'nin uzunluğunu hesaplamak mümkündür. 16 bit ve 32 bit opkodlara yönelik ayrı eşlemeler olduğundan, bu, değişken uzunluklu Thumb-2 yönergeleriyle bile mümkündür.

- Bir epıg kapsamının başlangıcından geçen yönergelerin sayısını sayarak, geriye doğru izleme kodlarının sayısını atlayıp bir sıranın geri kalanını yürüterek, bu da bir sıra geri kalanı yürütülecektir.

- İşlem, işlem tamamlanmadan önce gelen yönergelerin sayısını sayarak, geriye doğru bırakma kodlarının sayısını atlayıp, yalnızca yürütmeyi tamamlamış olan prolog bölümlerinin geri alınması için sıranın geri kalanını yürütür.

Aşağıdaki tabloda, bırakma kodlarından opkodlara eşleme gösterilmektedir. En yaygın olarak kullanılan kodlar yalnızca bir bayttır, daha az yaygın olarak iki, üç veya dört bayt gerektirir. Her kod, en önemli bayttan en az önemli bayta depolanır. Bu geriye doğru izleme kodları, kısmen yürütülen prologues ve epıtes 'in geriye doğru bir şekilde yürütülmesine izin vermek için, bu bırakma kodları, bir prolog ve epıg içindeki Opcode 'lar için bire bir eşlemeye sahip olacak şekilde tasarlandığından, geriye doğru izleme kodu yapısı ARM EABı 'da açıklanan kodlamadan farklıdır.

|Bayt 1|Byte 2|Byte 3|Bayt 4|Opsize|Açıklama|
|------------|------------|------------|------------|------------|-----------------|
|00-7F||||16|`add   sp,sp,#X`<br /><br /> Burada X (kod & 0x7F) \* 4|
|80-BF|00-FF|||32|`pop   {r0-r12, lr}`<br /><br /> Code & 0x1FFF kodunda karşılık gelen bit ayarlandıysa, & 0x2000 ve R0-R12 kodu posoında LR eksik|
|C0-CF||||16|`mov   sp,rX`<br /><br /> Burada X kod & 0x0F|
|D0-D7||||16|`pop   {r4-rX,lr}`<br /><br /> Burada X (kod & 0x03) + 4 ve LR, kod & 0x04 ise|
|D8-DF||||32|`pop   {r4-rX,lr}`<br /><br /> Burada X (kod & 0x03) + 8 ve LR, kod & 0x04 ise|
|E0-E7||||32|`vpop  {d8-dX}`<br /><br /> Burada X, (kod & 0x07) + 8|
|E8-EB|00-FF|||32|`addw  sp,sp,#X`<br /><br /> Burada X şeklindedir (kod & 0x03FF) \* 4|
|EC-ED|00-FF|||16|`pop   {r0-r7,lr}`<br /><br /> Bu kod & 0x0100 ve R0-R7 kodu, karşılık gelen bit & kodda ayarlandıysa "0x00FF"|
|PROFIL|00-0F|||16|Microsoft'a özgü|
|PROFIL|10-FF|||16|Kullanılabilir|
|AŞV|00-0F|||32|`ldr   lr,[sp],#X`<br /><br /> Burada X (kod & 0x000F) \* 4|
|AŞV|10-FF|||32|Kullanılabilir|
|F0-F4||||-|Kullanılabilir|
|F5|00-FF|||32|`vpop  {dS-dE}`<br /><br /> burada S (kod & 0x00F0) > > 4 ve E kod & 0x000F|
|F6|00-FF|||32|`vpop  {dS-dE}`<br /><br /> burada S ((kod & 0x00F0) > > 4) + 16 ve E 'dir (kod & 0x000F) + 16|
|F7|00-FF|00-FF||16|`add   sp,sp,#X`<br /><br /> Burada X (kod & 0x00FFFF) \* 4|
|F8|00-FF|00-FF|00-FF|16|`add   sp,sp,#X`<br /><br /> Burada X (kod & 0x00FFFFFF) \* 4|
|F9|00-FF|00-FF||32|`add   sp,sp,#X`<br /><br /> Burada X (kod & 0x00FFFF) \* 4|
|BELIRLEDIĞINIZ|00-FF|00-FF|00-FF|32|`add   sp,sp,#X`<br /><br /> Burada X (kod & 0x00FFFFFF) \* 4|
|ARIAL||||16|nop (16 bit)|
|FC||||32|nop (32-bit)|
|FD||||16|Son + 16-bit NOP, epıg|
|KARAKTERLER||||32|son + 32 bitlik NOP, epıg|
|BENZERI||||-|end|

Bu, bir geriye doğru izleme kodu *kodundaki*her bir bayt için onaltılık değerlerin aralığını, *Opsize* ve karşılık gelen orijinal yönerge yorumunu gösterir. Boş hücreler daha kısa bırakma kodlarını gösterir. Birden çok bayt kapsayan büyük değerlere sahip yönergelerde, en önemli bitler önce depolanır. *Opsize* alanı her Thumb-2 işlemiyle ilişkili örtük Opcode boyutunu gösterir. Farklı kodlarla tablodaki görünen yinelenen girişler, farklı Opcode boyutlarını ayırt etmek için kullanılır.

Geriye doğru izleme kodları, kodun ilk baytlık her ikisi de kodun baytındaki toplam boyutu ve yönerge akışındaki karşılık gelen Opcode boyutunu söylerken tasarlanmıştır. İşlem veya başlangıç boyutunu hesaplamak için, sıranın başından sonuna kadar geriye doğru izleme kodları yapın ve ilgili Opcode 'ın ne kadar süreyle olduğunu anlamak için bir arama tablosu veya benzer bir yöntem kullanın.

Geriye doğru izleme kodları 0xFD ve 0xFE, normal bitiş kodu 0xFF ile eşdeğerdir, ancak epıg durumunda 16 bit ya da 32 bit olan bir ek NOP işlem kodunun hesabıdır. Prologues için, 0xFD, 0xFE ve 0xFF kodları tam olarak eşdeğerdir. Bu hesaplar, eşdeğer bir prolog yönergesine sahip olmayan `bx lr` veya `b <tailcall-target>`ortak bir genel bakış bitleridir. Bu, geri bırakma sıralarının, prolog ve epengues arasında paylaşılabilmesi olasılığını artırır.

Çoğu durumda, prolog ve tüm epenler için aynı bırakma kodları kümesini kullanmak mümkün olmalıdır. Ancak, kısmen yürütülen prologues ve epıtes 'nin geriye doğru listesini işlemek için, sıralama veya davranışta değişen birden fazla bırakma kodu sırası olması gerekebilir. Bu nedenle, her bir epıg 'nin yürütme işlemini nereden başlayabileceğiniz göstermek için geriye doğru bırakma dizisine sahip olduğu.

### <a name="unwinding-partial-prologues-and-epilogues"></a>Kısmi prologues ve Epıletler 'in geriye doğru sıkıştırması

En yaygın geri sarma, özel durumun işlevin gövdesinde gerçekleştiği ve tüm epenlerden uzakta olması durumdur. Bu durumda, unwinder dizin 0 ' dan başlayan geri açılım dizisindeki kodları yürütür ve bir bitiş Opcode saptanana kadar devam eder.

Bir prolog veya epıg yürütülürken bir özel durum oluştuğunda, yığın çerçevesi yalnızca kısmen oluşturulur ve unwinder doğru şekilde geri almak için tam olarak nelerin yapıldığını belirlemelidir.

Örneğin, bu prolog ve epıg sırasını göz önünde bulundurun:

```asm
0000:   push  {r0-r3}         ; 0x04
0002:   push  {r4-r9, lr}     ; 0xdd
0006:   mov   r7, sp          ; 0xc7
...
0140:   mov   sp, r7          ; 0xc7
0142:   pop   {r4-r9, lr}     ; 0xdd
0146:   add   sp, sp, #16     ; 0x04
0148:   bx    lr
```

Her Opcode seçeneğinin yanında, bu işlemi anlatmak için uygun geriye doğru izleme kodu bulunur. Prolog için bırakma kodları sırası, son yönergeyi saymadan, epıg için bırakma kodlarının bir yansıtma görüntüsüdür. Bu durum yaygın bir durumdur ve, prolog 'nin bırakma kodlarından her zaman ters sırada depolanmak üzere kabul edilmesi nedenidir. Bu, bize ortak bir bırakma kodları kümesi sağlar:

```asm
0xc7, 0xdd, 0x04, 0xfd
```

0xFD kodu, epıg 'nin 1 16-bit yönergesinin, prolog 'den daha uzun olduğu anlamına gelen sıranın sonuna yönelik özel bir koddur. Bu, geriye doğru izleme kodları paylaşımını mümkün kılar.

Örnekte, prolog ve epıg arasındaki işlev gövdesi yürütülürken bir özel durum oluşursa, epıg kodu içindeki 0 uzaklığında, geriye doğru izleme durumuyla başlar. Bu, örnekte 0x140 ' ın sapmasını karşılık gelir. Temizlik yapılmadığından, unwinder tam geriye doğru sırayı yürütür. Bunun yerine, özel durum, epıg kodunun başlangıcından sonraki bir yönerge oluşursa, unwinder ilk bırakma kodunu atlayarak başarıyla geriye doğru geri alabilir. İşlem kodları ve bırakma kodları arasında bire bir eşleme verildiğinde, epıg 'de yönerge *n* ' den geriye doğru geri dönmek için, unwinder ilk *n* bırakma kodunu atmalıdır.

Benzer mantık, prolog için ters bir şekilde çalışmaktadır. İşlem için 0 ' dan geriye doğru kaydıysanız, hiçbir şeyin yürütülmesi gerekmez. İçindeki bir yönergeden geri doğru bir şekilde geçiş yaptıysanız, işlem geri sarma kodları ters sırada depolandığından, geriye doğru izleme sırası uçtan bir geriye doğru izleme kodu başlatmalıdır. Genel durumda, prolog 'daki yönerge *n* ' den geri sarısı, kod listesinin sonundaki *n* geriye doğru izleme kodlarından yürütülmeye başlamamalıdır.

Prolog ve epıg bırakma kodları her zaman tam olarak eşleşmez. Bu durumda, bırakma kodu dizisinin çeşitli kod dizilerini içermesi gerekebilir. Kodların işlenmesine başlama sapmasını öğrenmek için şu mantığı kullanın:

1. İşlevin gövdesinin içinden geri sarılırsa, 0 dizininden bırakma kodlarını yürütmeye başlayın ve bir bitiş işlem koduna ulaşılana kadar devam edin.

2. Bir epınm içinden geriye doğru geri sarılıyorsanız, epıg kapsamı tarafından sunulan epıg 'e özgü başlangıç dizinini kullanın. BILGISAYARıN, epıg 'nin başından itibaren kaç bayt olduğunu hesaplayın. Tüm önceden yürütülmüş yönergelerin hesaba gelene kadar geriye doğru izleme kodları üzerinden ileri atlayın. Bu noktadan başlayarak geriye doğru izleme sırasını yürütün.

3. Log 'nin içinden geriye doğru geri geçiş yaptıysanız, bırakma kodlarında 0 dizininden başlayın. Sıradaki prolog kodunun uzunluğunu hesaplayın ve sonra BILGISAYARıN bir süre sonundan itibaren kaç bayt olduğunu hesaplayın. Yürütülemeyen yönergelerin tümü için hesap tamamlanana kadar geriye doğru izleme kodları üzerinden ileri atlayın. Bu noktadan başlayarak geriye doğru izleme sırasını yürütün.

Prolog 'nin bırakma kodları her zaman dizide ilk olmalıdır. Bunlar aynı zamanda gövdeden geri doğru bir şekilde geçiş yapmak için kullanılan kodlardır. Epıg özgü kod dizileri, başlangıç kodu sırasından hemen sonra gelmelidir.

### <a name="function-fragments"></a>İşlev parçaları

Kod iyileştirmesi için bir işlevi bitişik olmayan parçalara bölmek faydalı olabilir. Bu işlem tamamlandığında, her işlev parçası kendi ayrı. pdata — ve muhtemelen. xdata — kaydı gerektirir.

İşlevin başlangıcında olduğu ve bölünemeyeceği varsayıldığında, dört işlev parçası durumu vardır:

- Yalnızca prolog; diğer parçalarla tüm epgular.

- Prolog ve bir veya daha fazla epengues; diğer parçalarla daha fazla epenler.

- Prolog veya EPIO 'lar yok; diğer parçalarla bir veya daha fazla ependen sorumlu.

- Yalnızca epengues; prolog ve büyük olasılıkla diğer parçalardan ek epenler.

İlk durumda, yalnızca prolog 'nin açıklanmalıdır. Bu, normal olarak genel olarak açıklanarak ve hiç bir başlangıç değeri olmadığını göstermek için 3 ' ün bir *ret* değeri belirtilerek Compact. pdata formunda yapılabilir. Full. xdata formunda bu, dizin 0 ' da her zamanki gibi prolog bırakma kodları eklenerek ve bir epıg sayısı 0 olarak belirtilerek yapılabilir.

İkinci durum, normal bir işlev gibidir. Parçada yalnızca bir tane varsa ve parçanın sonunda ise, bir Compact. pdata kaydı kullanılabilir. Aksi takdirde, tam bir. xdata kaydı kullanılmalıdır. Epıg başlangıcı için belirtilen uzaklıklarla, işlevin orijinal başlangıcına değil, parçanın başlangıcına göre olduğunu unutmayın.

Üçüncü ve dördüncü durumlar, ilk ve ikinci durumların, sırasıyla, bir prolog içermediği durumlar haricinde çeşitlerdir. Bu durumlarda, açığa çıkabilecek başlangıçtan önce kod olduğunu ve işlevin gövdesinin bir parçası olarak kabul edildiği varsayılır ve bu durum normalde, prolog 'un etkilerini geri alarak kaçınılırdı. Bu nedenle, gövdenin başlangıcında nasıl geriye doğru bir geriye doğru bir geri alma yapılıp yapılmayacağını belirleyen bir sözde prolog ile kodlanmış olması gerekir. Alternatif olarak, bu sözde prolog, eşdeğer işlemleri kabul ettiğinden, epıg ile aynı geriye doğru izleme kodları kullanılarak açıklanabilir.

Üçüncü ve dördüncü durumlarda, sahte prolog 'nin varlığı, Compact. pdata kaydının *bayrak* alanı 2 ' ye ayarlanarak veya. xdata üstbilgisindeki *F* bayrağını 1 ' e ayarlayarak belirtilir. Her iki durumda da kısmi bir başlangıç geri bırakma denetimi yok sayılır ve tüm epıg olmayan kaynaklar dolu olarak kabul edilir.

#### <a name="large-functions"></a>Büyük Işlevler

Parçalar,. xdata üstbilgisindeki bit alanları tarafından uygulanan 512 KB sınırından daha büyük işlevleri tanımlamaya yönelik olarak kullanılabilir. Çok büyük bir işlevi anlatmak için, bunu 512 KB 'tan küçük parçalara kesmeniz yeterlidir. Her parça birden çok parçaya bölünemeyecek şekilde ayarlanmalıdır.

Yalnızca işlevin ilk parçasında bir prolog bulunur; diğer tüm parçalar hiçbir bir başlangıç olmadan işaretlenir. EPIO 'lar sayısına bağlı olarak, her parça sıfır veya daha fazla epgues içerebilir. Bir parçadaki her bir epıg kapsamının, işlevin başlangıcına değil, parçanın başlangıcına göre başlangıç sapmasını belirttiğinden emin olmak için aklınızda bulundurun.

Bir parçanın hiç bir başlangıç süresi yoksa ve hiçbir kaynak yoksa, işlevin gövdesinin içinden geriye doğru nasıl geri alınacağını betimleyen kendi. pdata — ve muhtemelen. xdata — için de kayıt gerekir.

#### <a name="shrink-wrapping"></a>Küçültme-kaydırma

İşlev parçalarının daha karmaşık bir özel durumu, *küçültme-sarmalama*, kayıt kaydetme gerektirmeyen basit servis taleplerini iyileştirmek için, kaydın başından sonra işlevin başlangıcından daha sonraki bir şekilde kaydedilmesini sağlayan bir tekniktir. Bu, yığın alanını ayıran, ancak en az sayıda kayıt kaydeden ve ek kayıtları kaydeden ve geri yükleyen bir iç bölgenin bulunduğu bir dış bölge olarak açıklanabilir.

```asm
ShrinkWrappedFunction
    push   {r4, lr}          ; A: save minimal non-volatiles
    sub    sp, sp, #0x100    ; A: allocate all stack space up front
    ...                      ; A:
    add    r0, sp, #0xE4     ; A: prepare to do the inner save
    stm    r0, {r5-r11}      ; A: save remaining non-volatiles
    ...                      ; B:
    add    r0, sp, #0xE4     ; B: prepare to do the inner restore
    ldm    r0, {r5-r11}      ; B: restore remaining non-volatiles
    ...                      ; C:
    pop    {r4, pc}          ; C:
```

Daraltma Sarmalanan işlevler genellikle, ek kayıt için alanın önceden ayrılması, normal bir prolog 'da kaydedilir ve ardından kayıt işlemini `push`yerine `str` veya `stm` kullanarak kaydeder. Bu, işlevin özgün prolog öğesinde tüm yığın işaretçisi işlemesini korur.

Örnek küçültme Sarmalanan işlev, açıklamalarda bir, B ve C olarak işaretlenen üç bölgeye bölünmemelidir. İlk A bölgesi, diğer geçici olmayan kaydetme işlemi boyunca işlevin başlangıcını ele alır. Bir. pdata veya. xdata kaydı, bu parçayı, bir prolog ve epıtes yok olarak anlatmak için oluşturulmalıdır.

Orta B bölgesi, hiç bir prolog ve hiçbir kaynak olmayan bir parçayı açıklayan kendi. pdata veya. xdata kaydını alır. Ancak, bir işlev gövdesi olarak kabul edildiği için, bu bölgenin bırakma kodlarının hala mevcut olması gerekir. Kodlar, tek bir işlem dizisi tarafından üretilmiş gibi, bölge-A ' y A girmeden önce bir prolog ve bölge B ' yi girmeden önce kaydedilen ek Yazmaçları temsil eden bileşik bir prolog 'yi tanımlamalıdır.

B bölgesi için belirtilen bileşik prolog 'nin hem bir prolog hem de ek kayıt kaydedilmesi gerektiğinden, B bölgesinin kayıt kayıtları "İç prolog" olarak kabul edilmez. B bölümü bir işlem ile açıklandığı takdirde, geriye doğru izleme kodları o işlem için de bu değeri de anladı ve bileşik prolog 'yi yalnızca ek kayıtları kaydeden Opcode 'ları ile eşleyen bir şekilde tanımlamanın bir yolu yoktur.

Ek yazmaç, A bölgesinin bir parçası olarak düşünülmelidir, çünkü tamamlanana kadar, bileşik prolog yığının durumunu doğru bir şekilde açıklamaz.

Son C bölgesi kendi. pdata veya. xdata kaydını alır, bu, hiç bir prolog içermeyen ancak bir epıg içeren bir parçayı tanımlar.

Alternatif bir yaklaşım, B bölgesine girmeden önce yapılan yığın işleme işlemi bir yönergeye indirgenmeden da çalışabilir:

```asm
ShrinkWrappedFunction
    push   {r4, lr}          ; A: save minimal non-volatile registers
    sub    sp, sp, #0xE0     ; A: allocate minimal stack space up front
    ...                      ; A:
    push   {r4-r9}           ; A: save remaining non-volatiles
    ...                      ; B:
    pop    {r4-r9}           ; B: restore remaining non-volatiles
    ...                      ; C:
    pop    {r4, pc}          ; C: restore non-volatile registers
```

Buradaki anahtar, her yönerge sınırında, yığının, bölgenin bırakma kodlarıyla tamamen tutarlı olmasını sağlayan bir anahtardır. Bu örnekte iç göndermeden önce geriye doğru bir geri yükleme gerçekleşirse, A bölgesinin bir parçası olarak değerlendirilir ve yalnızca bir prolog bölgesi bozuk olur. Geri yükleme, iç göndermeden sonra gerçekleşirse, B bölgesinin bir parçası olarak kabul edilir, ancak iç gönderimi ve A bölgesinden gelen özgün prolog 'yi açıklayan bırakma kodlarına sahiptir. iç pop için benzer Logic barındırır.

### <a name="encoding-optimizations"></a>Kodlama Iyileştirmeleri

Bırakma kodlarının zenginliği ve verilerin sıkıştırılmış ve genişletilmiş biçimlerini kullanabilme özelliği sayesinde, alanı daha fazla azaltmak için kodlamayı iyileştirmek üzere çok sayıda fırsat vardır. Bu tekniklerin agresif kullanımıyla, geriye doğru izleme kodlarını kullanarak işlevleri ve parçaları tanımlamaya yönelik net ek yükü oldukça az olabilir.

En önemli iyileştirme, bir derleyici perspektifinden mantıksal prolog/epıg sınırları ile geriye doğru izleme için prolog/epıg sınırlarını kanıtlama konusunda dikkatli değildir. Geri sarma sınırları daraltılamaz ve verimliliği artırmak için daha sıkı hale getirilebilir. Örneğin, bir prolog, ek doğrulama denetimleri gerçekleştirmek için yığın kurulumundan sonra kod içerebilir. Ancak, tüm yığın düzenlemesi tamamlandıktan sonra, diğer işlemleri kodlamaya gerek kalmaz ve bunun dışındaki herhangi bir şey, geriye doğru izleme işleminden kaldırılabilirler.

Bu kural, işlev uzunluğu için de geçerlidir. Veriler varsa — Örneğin, bir işlev içinde bir epıden sonraki bir değer varsa, işlev uzunluğunun bir parçası olarak eklenmemelidir. İşlevi, işlevin yalnızca bir parçası olan koda daraltarak, epıg 'nin çok uçta ve bir Compact yolunda olacağı çok daha büyük olur. PDATA kaydı kullanılabilir.

Bir prolog 'da, yığın işaretçisi başka bir kayda kaydedildikten sonra, genellikle başka bir ek kod kaydetmeniz gerekmez. İşlevi geriye doğru bırakmak için, yapılan ilk şey, değişiklikleri kaydedilen kayıt 'den kurtarmaktır ve bu nedenle daha fazla işlem, geriye doğru izleme üzerinde hiçbir etkiye sahip olmaz.

Tek yönergeden epıtes 'in, kapsam veya bırakma kodları olarak her birinde kodlanmalıdır. Bu yönerge yürütülmeden önce bir geriye doğru hale getirmeniz durumunda, işlevin gövdesinde olduğu kabul edilebilir ve yalnızca işlem geri bırakma kodlarını yürütmek yeterlidir. Tek yönerge yürütüldükten sonra geri doğru gerçekleşdikten sonra, tanım tarafından başka bir bölgede gerçekleşir.

Multi-instruction epıtes, önceki nokta ile aynı nedenden dolayı epıg 'nin ilk yönergesini kodlamak zorunda değildir: geriye doğru izleme, bu yönerge yürütülmeden önce gerçekleşmişse, tam bir prolog açılımı yeterlidir. Bu yönergeden sonra geri doğru gerçekleşirken yalnızca sonraki işlemler göz önünde bulundurulmalıdır.

Bırakma kodu yeniden kullanımı agresif olmalıdır. Her bir epıg kapsamı tarafından belirtilen dizin, geriye doğru izleme kodları dizisinde rastgele bir başlangıç noktasını işaret eder. Önceki bir dizinin başlangıcına işaret etmek zorunda değildir; Bu, ortaya işaret edebilir. Buradaki en iyi yaklaşım, istenen kod sırasını oluşturmak ve ardından, daha önce kodlanmış sıralar havuzunda tam bayt eşleşmesi için tarama yapmak ve yeniden kullanmak için bir başlangıç noktası olarak herhangi bir kusursuz eşleşme kullanmak içindir.

Tek yönergeden sonra, tek yönergeden sonra yok sayılırsa, bir Compact. pdata formu kullanmayı düşünün; Bu, bir epıte yokluğunda çok daha büyük olur.

## <a name="examples"></a>Örnekler

Bu örneklerde, görüntü tabanı 0x00400000 ' dır.

### <a name="example-1-leaf-function-no-locals"></a>Örnek 1: yaprak Işlev, Yereller yok

```asm
Prologue:
  004535F8: B430      push        {r4-r5}
Epilogue:
  00453656: BC30      pop         {r4-r5}
  00453658: 4770      bx          lr
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x000535f8 (= 0x004535f8-0x00400000)

- Sözcük 1

   - *Bayrak* = 1, kurallı prolog ve epıg biçimlerini belirtir

   - *Işlev uzunluğu* = 0x31 (= 0x62/2)

   - *Ret* = 1, 16 bit dal dönüşü belirtir

   - *H* = 0, parametrelerin bağlantılı olmadığını belirtir

   - *R*= 0 ve *reg* = 1, R4-R5 push/pop belirten

   - *L* = 0, bir LR kaydet/geri yükle olduğunu belirtir

   - *C* = 0, çerçeve zinciri olmadığını gösterir

   - *Yığın ayarlama = 0* , yığın ayarlaması olmadığını gösterir

### <a name="example-2-nested-function-with-local-allocation"></a>Örnek 2: yerel ayırma ile Iç Içe Işlev

```asm
Prologue:
  004533AC: B5F0      push        {r4-r7, lr}
  004533AE: B083      sub         sp, sp, #0xC
Epilogue:
  00453412: B003      add         sp, sp, #0xC
  00453414: BDF0      pop         {r4-r7, pc}
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x000533ac (= 0x004533ac-0x00400000)

- Sözcük 1

   - *Bayrak* = 1, kurallı prolog ve epıg biçimlerini belirtir

   - *Işlev uzunluğu* = 0x35 (= 0x6A/2)

   - *Ret* = 0, bir pop {PC} dönüşü olduğunu belirtir

   - *H* = 0, parametrelerin bağlantılı olmadığını belirtir

   - *R*= 0 ve *reg* = 3, R4-R7 push/pop 'u belirten

   - *L* = 1, LR 'in kaydedildiğini/geri yüklendiğini belirtir

   - *C* = 0, çerçeve zinciri olmadığını gösterir

   - *Stack ayarlaması* = 3 (= 0x0C/4)

### <a name="example-3-nested-variadic-function"></a>Örnek 3: Iç Içe değişen bağımsız değişken Işlev

```asm
Prologue:
  00453988: B40F      push        {r0-r3}
  0045398A: B570      push        {r4-r6, lr}
Epilogue:
  004539D4: E8BD 4070 pop         {r4-r6}
  004539D8: F85D FB14 ldr         pc, [sp], #0x14
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x00053988 (= 0x00453988-0x00400000)

- Sözcük 1

   - *Bayrak* = 1, kurallı prolog ve epıg biçimlerini belirtir

   - *Işlev uzunluğu* = 0x2A (= 0x54/2)

   - *Ret* = 0, bir pop {PC} stili geri dönüşü (Bu durumda bir LDR bilgisayar, [SP], #0x14 dönüşü) belirtir

   - *H* = 1, parametre bağlı olduğunu belirtir

   - *R*= 0 ve *reg* = 2, R4-R6 push/pop belirten

   - *L* = 1, LR 'in kaydedildiğini/geri yüklendiğini belirtir

   - *C* = 0, çerçeve zinciri olmadığını gösterir

   - *Yığın ayarlama = 0* , yığın ayarlaması olmadığını gösterir

### <a name="example-4-function-with-multiple-epilogues"></a>Örnek 4: birden fazla Epıle Işlevi

```asm
Prologue:
  004592F4: E92D 47F0 stmdb       sp!, {r4-r10, lr}
  004592F8: B086      sub         sp, sp, #0x18
Epilogues:
  00459316: B006      add         sp, sp, #0x18
  00459318: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  0045943E: B006      add         sp, sp, #0x18
  00459440: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  004595D4: B006      add         sp, sp, #0x18
  004595D6: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  00459606: B006      add         sp, sp, #0x18
  00459608: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  00459636: F028 FF0F bl          KeBugCheckEx     ; end of function
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x000592f4 (= 0x004592f4-0x00400000)

- Sözcük 1

   - *Bayrak* = 0,. xdata kaydı mevcut (birden çok epiler nedeniyle gereklidir)

   - *. xdata adresi* -0x00400000

. xdata (değişken, 6 sözcük):

- Sözcük 0

   - *Işlev uzunluğu* = 0x0001a3 (= 0x000346/2)

   - *Vers* = 0, ilk XData sürümünü belirtir

   - *X* = 0, özel durum verisi olmadığını gösterir

   - *E* = 0, bir epıg kapsamlarının listesini belirtir

   - *F* = 0, prolog dahil olmak üzere tam bir işlev açıklaması belirtir

   - *Epıg sayısı* = 0x04, toplam 4 Toplam epıg kapsamını belirten

   - *Kod kelimeleri* = 0x01, geriye doğru izleme kodları için 1 32 bit kelime

- 4 konumda 4 epıg kapsamlarını açıklayan 1-4 kelimeleri. Her kapsam, 0x00 uzaklığında ortak bir geriye doğru bırakma kodları kümesine sahiptir ve bu, 0Xe (her zaman) koşulunu belirterek koşulsuz olur.

- Geriye doğru izleme kodları, 5. sözcükten itibaren: (prolog/epıg arasında paylaşılan)

   - Bırakma kodu 0 = 0x06: SP + = (6 < < 2)

   - Bırakma kodu 1 = 0xDE: pop {r4-r10, LR}

   - Bırakma kodu 2 = 0xFF: bitiş

### <a name="example-5-function-with-dynamic-stack-and-inner-epilogue"></a>Örnek 5: dinamik yığın ve Iç Epıng ile Işlev

```asm
Prologue:
  00485A20: B40F      push        {r0-r3}
  00485A22: E92D 41F0 stmdb       sp!, {r4-r8, lr}
  00485A26: 466E      mov         r6, sp
  00485A28: 0934      lsrs        r4, r6, #4
  00485A2A: 0124      lsls        r4, r4, #4
  00485A2C: 46A5      mov         sp, r4
  00485A2E: F2AD 2D90 subw        sp, sp, #0x290
Epilogue:
  00485BAC: 46B5      mov         sp, r6
  00485BAE: E8BD 41F0 ldm         sp!, {r4-r8, lr}
  00485BB2: B004      add         sp, sp, #0x10
  00485BB4: 4770      bx          lr
  ...
  00485E2A: F7FF BE7D b           #0x485B28    ; end of function
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x00085a20 (= 0x00485a20-0x00400000)

- Sözcük 1

   - *Bayrak* = 0,. xdata kaydı mevcut (birden çok epiler nedeniyle gereklidir)

   - *. xdata adresi* -0x00400000

. xdata (değişken, 3 sözcük):

- Sözcük 0

   - *Işlev uzunluğu* = 0x0001a3 (= 0x000346/2)

   - *Vers* = 0, ilk XData sürümünü belirtir

   - *X* = 0, özel durum verisi olmadığını gösterir

   - *E* = 0, bir epıg kapsamlarının listesini belirtir

   - *F* = 0, prolog dahil olmak üzere tam bir işlev açıklaması belirtir

   - *Epıg sayısı* = 0x001, toplam 1 Toplam epıg kapsamını belirten

   - *Kod kelimeleri* = 0x01, geriye doğru izleme kodları için 1 32 bit kelime

- Word 1:0xC6 (= 0x18C/2) uzaklığında Epıg kapsamı, 5. yeniden bırakma kodu dizinini 0x00 ve 0x0E (her zaman) durumuyla başlatma

- Bırakma kodları, Word 2 ' den başlayarak: (prolog/epıg arasında paylaşılan)

   - Bırakma kodu 0 = 0xC6: SP = R6

   - Bırakma kodu 1 = 0xDC: pop {r4-R8, LR}

   - Bırakma kodu 2 = 0x04: SP + = (4 < < 2)

   - Bırakma kodu 3 = 0xFD: son, epıg için 16 bit yönerge olarak sayılır

### <a name="example-6-function-with-exception-handler"></a>Örnek 6: özel durum Işleyicisiyle Işlev

```asm
Prologue:
  00488C1C: 0059 A7ED dc.w  0x0059A7ED
  00488C20: 005A 8ED0 dc.w  0x005A8ED0
FunctionStart:
  00488C24: B590      push        {r4, r7, lr}
  00488C26: B085      sub         sp, sp, #0x14
  00488C28: 466F      mov         r7, sp
Epilogue:
  00488C6C: 46BD      mov         sp, r7
  00488C6E: B005      add         sp, sp, #0x14
  00488C70: BD90      pop         {r4, r7, pc}
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x00088c24 (= 0x00488c24-0x00400000)

- Sözcük 1

   - *Bayrak* = 0,. xdata kaydı mevcut (birden çok epiler nedeniyle gereklidir)

   - *. xdata adresi* -0x00400000

. xdata (değişken, 5 sözcük):

- Sözcük 0

   - *Işlev uzunluğu* = 0x000027 (= 0x00004e/2)

   - *Vers* = 0, ilk XData sürümünü belirtir

   - *X* = 1, özel durum verilerinin mevcut olduğunu belirtir

   - *E* = 1, tek bir epıg olduğunu belirtir

   - *F* = 0, prolog dahil olmak üzere tam bir işlev açıklaması belirtir

   - *EPIO Count* = 0x00, epıg bırakma kodları 0x00 uzaklığında başlar

   - *Kod kelimeleri* = 0x02, geriye doğru izleme kodlarının 2 32 bitlik sözcüklerini belirten

- Geriye doğru izleme kodları, 1. sözcükten itibaren:

   - Bırakma kodu 0 = 0xC7: SP = R7

   - Bırakma kodu 1 = 0x05: SP + = (5 < < 2)

   - Bırakma kodu 2 = 0Faksla/0x90: pop {r4, R7, LR}

   - Bırakma kodu 4 = 0xFF: bitiş

- Word 3 bir özel durum işleyicisi belirtir = 0x0019A7ED (= 0x0059A7ED-0x00400000)

- 4 ve ötesi sözcükleri satır içine alınmış özel durum verileri

### <a name="example-7-funclet"></a>Örnek 7: funclet

```asm
Function:
  00488C72: B500      push        {lr}
  00488C74: B081      sub         sp, sp, #4
  00488C76: 3F20      subs        r7, #0x20
  00488C78: F117 0308 adds        r3, r7, #8
  00488C7C: 1D3A      adds        r2, r7, #4
  00488C7E: 1C39      adds        r1, r7, #0
  00488C80: F7FF FFAC bl          target
  00488C84: B001      add         sp, sp, #4
  00488C86: BD00      pop         {pc}
```

. pdata (düzeltildi, 2 sözcük):

- Sözcük 0

   - *Işlev başlangıç RVA* = 0x00088c72 (= 0x00488c72-0x00400000)

- Sözcük 1

   - *Bayrak* = 1, kurallı prolog ve epıg biçimlerini belirtir

   - *Işlev uzunluğu* = 0x0B (= 0x16/2)

   - *Ret* = 0, bir pop {PC} dönüşü olduğunu belirtir

   - *H* = 0, parametrelerin bağlantılı olmadığını belirtir

   - *R*= 0 ve *reg* = 7, kaydedilmiş bir kayıt olmadığını ve geri yüklendiğini belirtir

   - *L* = 1, LR 'in kaydedildiğini/geri yüklendiğini belirtir

   - *C* = 0, çerçeve zinciri olmadığını gösterir

   - *Yığın ayarlama* = 1, 1 × 4 baytlık yığın ayarlamayı belirtir

## <a name="see-also"></a>Ayrıca bkz.

[ARM ABI Kurallarına Genel Bakış](overview-of-arm-abi-conventions.md)<br/>
[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)
