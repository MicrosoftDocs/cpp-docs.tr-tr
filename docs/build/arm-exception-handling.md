---
title: ARM Özel Durum Taşıma
ms.date: 07/11/2018
ms.assetid: fe0e615f-c033-4ad5-97f4-ff96af45b201
ms.openlocfilehash: 4bdf0c88f0c2fe445f3a8865353ca1259ba586fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323218"
---
# <a name="arm-exception-handling"></a>ARM Özel Durum Taşıma

ARM'deki Windows, eşzamanlı donanım tarafından oluşturulan özel durumlar ve eşzamanlı yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme mekanizmasını kullanır. Dile özgü özel özel durum işleyicileri, dil yardımcı işlevlerini kullanarak Windows yapılandırılmış özel durum işlemenin üzerine inşa edilir. Bu belge, WINDOWS'da ARM'da özel durum işlemeyi ve Microsoft ARM assembler ve MSVC derleyicisi tarafından oluşturulan kod tarafından kullanılan dil yardımcılarını açıklar.

## <a name="arm-exception-handling"></a>ARM Özel Durum Taşıma

ARM'deki Windows, [yapılandırılmış özel durum işleme](/windows/win32/debug/structured-exception-handling) (SEH) sırasında yığın gevşemeyi denetlemek için gevşeme *kodlarını* kullanır. Gevşeme kodları, çalıştırılabilir görüntünün .xdata bölümünde depolanan bayt dizisidir. İşlev önsözü ve epilog kodunun işleyişini soyut bir şekilde açıklarlar, böylece bir işlevin prologunun etkileri arayanın yığın çerçevesine gevşemeye hazırlık olarak geri alınabilir.

ARM EABI (gömülü uygulama ikili arabirimi) kodları gevşetme kullanan bir özel durum gevşeme modeli belirtir, ancak işlemcinin bir işlevin önsözünün veya sonsözünün ortasında olduğu eşzamanlı durumları işlemek zorunda olan Windows'da SEH gevşemesi için yeterli değildir. Windows ayrıca, gevşeme denetimini ARM EABI'de birleştirilmiş işlev düzeyinde gevşeme ve dile özgü kapsam gevşemesine ayırır. Bu nedenlerden dolayı, WINDOWS ARM'da gevşetme verileri ve yordamı için daha fazla ayrıntı belirtir.

### <a name="assumptions"></a>Varsayımlar

ARM'daki Windows için çalıştırılabilir görüntüler Taşınabilir Çalıştırılabilir (PE) biçimini kullanır. Daha fazla bilgi için [Microsoft PE ve COFF Belirtimi'ne](https://go.microsoft.com/fwlink/p/?linkid=84140)bakın. Özel durum işleme bilgileri görüntünün .pdata ve .xdata bölümlerinde depolanır.

Özel durum işleme mekanizması ARM'da Windows için ABI'yi izleyen kod hakkında bazı varsayımlar yapar:

- Bir işlevin gövdesi içinde bir özel durum oluştuğunda, prolog işlemlerinin geri alınıp alınmadığı veya epilog işlemlerinin ileri yönde bir şekilde gerçekleştirilip gerçekleştirilmediği önemli değildir. Her ikisi de aynı sonuçları üretmelidir.

- Prologlar ve epiloglar birbirini yansıtma eğilimindedir. Bu, gevşemeyi tanımlamak için gereken meta verilerin boyutunu azaltmak için kullanılabilir.

- Fonksiyonlar nispeten küçük olma eğilimindedir. Çeşitli optimizasyonlar, verilerin verimli bir şekilde paketlenmesi için buna dayanır.

- Bir koşul bir epiloga yerleştirilirse, epilogdaki her talimat için eşit olarak geçerlidir.

- Yığın işaretçisi (SP) önlogtaki başka bir kayda kaydedilirse, özgün SP'nin herhangi bir zamanda kurtarılabilmesi için bu kaydın işlev boyunca değişmeden kalması gerekir.

- SP başka bir kayıt ta kaydedilmedikçe, tüm manipülasyon kesinlikle prolog ve epilog içinde gerçekleşmelidir.

- Herhangi bir yığın çerçevesini gevşetmek için şu işlemler gereklidir:

  - r13'ü (SP) 4 baytlık artışlarla ayarlayın.

  - Bir veya daha fazla tümseci kaydını pop.

  - Bir veya daha fazla VFP (sanal kayan nokta) kaydını pop.

  - Rasgele bir kayıt değerini r13 (SP) olarak kopyalayın.

  - Küçük bir decrement sonrası işlem kullanarak yığından SP yükleyin.

  - Birkaç iyi tanımlanmış çerçeve türlerinden birini ayrıştırın.

### <a name="pdata-records"></a>.pdata Kayıtları

PE biçimindeki görüntüdeki .pdata kayıtları, her yığın işleme işlevini açıklayan sıralı bir sabit uzunlukta öğeler dizisidir. Diğer işlevleri çağırmayan işlevler olan yaprak işlevleri, yığını işlemediklerinde .pdata kayıtları gerektirmez. (Diğer bir şey, herhangi bir yerel depolama gerektirmez ve geçici olmayan kayıtları kaydetmek veya geri yüklemek zorunda değilsiniz.). Bu işlevlere ait kayıtlar, yer kazanmak için .pdata bölümünden atlanabilir. Bu işlevlerden birinden gelen gevşeme işlemi, arayana geçmek için Bağlantı Kaydı'ndan (LR) program sayacına (PC) geri dönüş adresini kopyalayabilir.

ARM için her .pdata kaydı 8 bayt uzunluğundadır. Bir kaydın genel biçimi, işlevin göreli sanal adresini (RVA) ilk 32 bit sözcükte başlatır ve ardından değişken uzunlukta .xdata bloğuna işaretçi veya bu tabloda gösterildiği gibi kanonik işlev gevşeme dizisini açıklayan paketlenmiş bir sözcüğü içeren ikinci bir sözcük yerleştirir:

|Sözcük Ofset|Bits|Amaç|
|-----------------|----------|-------------|
|0|0-31|*Fonksiyon Başlangıç RVA* fonksiyonun başlangıcının 32 bit RVA'sudur. İşlev başparmak kodu içeriyorsa, bu adresin alt biti ayarlanmalıdır.|
|1|0-1|*Bayrak,* ikinci .pdata sözcüğünün kalan 30 bitinin nasıl yorumlanacağına işaret eden 2 bitlik bir alandır. *Bayrak* 0 ise, kalan bitler bir *Özel Durum Bilgisi RVA'sı* oluşturur (düşük iki biti örtülü olarak 0 ile). *Bayrak* sıfır değilse, kalan bitler Paketlenmiş *Gevşeme Verileri* yapısı oluşturur.|
|1|2-31|*Özel Durum Bilgileri RVA* veya *Paketlenmiş Gevşeme Verileri*.<br /><br /> *Özel Durum Bilgisi RVA,* .xdata bölümünde depolanan değişken uzunluktaki özel durum bilgi yapısının adresidir. Bu veriler 4 bayt hizalanmış olmalıdır.<br /><br /> *Paketlenmiş Gevşeme Verileri,* bir işlevden gevşemek için gereken işlemlerin sıkıştırılmış bir açıklamasıdır ve bir döngüsel form varsayılabilir. Bu durumda, .xdata kaydı gerekmez.|

### <a name="packed-unwind-data"></a>Paketlenmiş Gevşeme Verileri

Prologları ve epilogları aşağıda açıklanan kanonik formu takip eden işlevler için paketlenmiş gevşeme verileri kullanılabilir. Bu, bir .xdata kaydı gereksinimini ortadan kaldırır ve gevşeyemeyen veriler sağlamak için gereken alanı önemli ölçüde azaltır. Kanonik prologlar ve epiloglar, özel durum işleyicisi gerektirmeyen basit bir işlevin ortak gereksinimlerini karşılayacak şekilde tasarlanmıştır ve kurulum ve yıkma işlemlerini standart bir sırada gerçekleştirir.

Bu tablo, paketlenmiş gevşeme verileri olan bir .pdata kaydının biçimini gösterir:

|Sözcük Ofset|Bits|Amaç|
|-----------------|----------|-------------|
|0|0-31|*Fonksiyon Başlangıç RVA* fonksiyonun başlangıcının 32 bit RVA'sudur. İşlev başparmak kodu içeriyorsa, bu adresin alt biti ayarlanmalıdır.|
|1|0-1|*Bayrak,* şu anlamlara sahip 2 bitlik bir alandır:<br /><br />- 00 = paketlenmiş gevşeme verileri kullanılmaz; kalan bitler .xdata kaydına işaret eder.<br />- 01 = paketlenmiş gevşeme verileri.<br />- 10 = fonksiyonun prolog olmadığı varsayıldığı paketlenmiş gevşeme verileri. Bu, işlevin başlangıcıyla ayrıştırılabilen işlev parçalarını açıklamak için yararlıdır.<br />- 11 = saklıdır.|
|1|2-12|*İşlev Uzunluğu,* baytlar halindeki tüm işlevin 2'ye bölünmesini sağlayan 11 bitlik bir alandır. İşlev 4K baytlardan büyükse, bunun yerine tam bir .xdata kaydı kullanılmalıdır.|
|1|13-14|*Ret,* işlevin nasıl döndürür olduğunu gösteren 2 bitlik bir alandır:<br /><br />- 00 = pop {pc} ile return *(Bu* durumda L bayrak biti 1 olarak ayarlanmalıdır).<br />- 01 = 16 bit dal kullanarak geri dönün.<br />- 10 = 32 bit dal kullanarak geri dönün.<br />- 11 = hiç epilog yok. Bu, yalnızca bir önsöz içerebilecek, ancak epilogbaşka bir yerde olan ayrıştırıcı bir işlev parçasını tanımlamak için yararlıdır.|
|1|15|*H,* tamsayı parametresinin işlevinin başında iterek "evler" işlevinin "evlere" kaydedip kaydetmediğini (r0-r3) gösteren ve dönmeden önce 16 baytlık desteyi işaret eden bir bayraktır. (0 = ev kayıtları değil, 1 = evler kayıtları.)|
|1|16-18|*Reg,* kaydedilen son geçici olmayan kaydın dizinini gösteren 3 bitlik bir alandır. *R* biti 0 ise, yalnızca toplam kayıt kaydedilir ve N'nin 4 + *Reg'e*eşit olduğu r4-rN aralığında olduğu varsayılır. *R* biti 1 ise, yalnızca kayan nokta kayıtları kaydedilir ve N'nin 8 + *Reg'e*eşit olduğu d8-dN aralığında olduğu varsayılır. *R* = 1 ve *Reg* = 7'nin özel birleşimi hiçbir kaydın kaydolmadığını gösterir.|
|1|19|*R,* kaydedilen geçici olmayan kayıtların tamsayı kayıtları (0) veya kayan nokta kayıtları (1) olup olmadığını gösteren 1 bitlik bir bayraktır. *R* 1'e ayarlanırsa ve *Reg* alanı 7 olarak ayarlanmışsa, uçucu olmayan kayıtlar itilmiş değildir.|
|1|20|*L,* işlevin *Reg* alanı tarafından gösterilen diğer kayıtlarla birlikte LR'yi kaydedip kurtarmadığını/geri yükleyip geri yüklemediğini gösteren 1 bitlik bir bayraktır. (0 = kaydetmez/geri yüklemez, 1 = kaydet/geri yükleme yapar.)|
|1|21|*C,* işlevin hızlı yığın yürümesi (1) veya (0) için bir çerçeve zinciri kurmak için ek yönergeler içerip içermediğini gösteren 1 bitlik bir bayraktır. Bu bit ayarlanırsa, r11 kaydedilen tamsayı geçici olmayan kayıtlar listesine dolaylı olarak eklenir. *(C* bayrağı kullanılırsa aşağıdaki kısıtlamalara bakın.)|
|1|22-31|*Yığın Ayarlama,* bu işlev için ayrılan ve 4'e bölünen yığın bayt sayısını gösteren 10 bitlik bir alandır. Ancak, yalnızca 0x000-0x3F3 arasındaki değerler doğrudan kodlanabilir. 4044 bayttan fazla yığın ayıran işlevler tam bir .xdata kaydı kullanmalıdır. Stack *Adjust* alanı 0x3F4 veya daha büyükse, düşük 4 bitin özel bir anlamı vardır:<br /><br />- 0-1 bitleri yığın ayarlaması (1-4) eksi 1 kelime sayısını gösterir.<br />- Prolog bu ayarı itme işleminde birleştirdiyse Bit 2 1 olarak ayarlanır.<br />- Bit 3, epilog bu ayarı pop işleminde birleştirdiyse 1 olarak ayarlanır.|

Yukarıdaki kodlamalarda olası fazlalıklar nedeniyle, bu kısıtlamalar geçerlidir:

- *C* bayrağı 1 olarak ayarlanmışsa:

  - Çerçeve zincirleme hem r11 hem de LR gerektirdiğinden, *L* bayrağı da 1 olarak ayarlanmalıdır.

  - r11, *Reg*tarafından açıklanan kayıt kümesine dahil edilmemelidir. Diğer bir de, r4-r11 itilirse, *Reg* yalnızca r4-r10'u tanımlamalıdır, çünkü *C* bayrağı r11'i ifade eder.

- *Ret* alanı 0 olarak ayarlanmışsa, *L* bayrağı 1 olarak ayarlanmalıdır.

Bu kısıtlamaların ihlal edilmesi desteklenmeyen bir sıraya neden olur.

Aşağıdaki tartışmanın amaçları için *Stack Adjust'dan*iki sözde bayrak türetilmiştir:

- *PF* veya "prolog katlama" *Stack Adjust* 0x3F4 veya daha büyük olduğunu gösterir ve bit 2 ayarlanır.

- *EF* veya "epilog katlama" *Stack Adjust* 0x3F4 veya daha büyük olduğunu gösterir ve bit 3 ayarlanır.

Kanonik işlevler için prologlar en fazla 5 yönergeye sahip olabilir (3a ve 3b'nin birbirini dışladığını fark edin):

|Yönerge|Opcode varsayılarak:|Boyut|Işlem kodu|Kodları Gevşet|
|-----------------|-----------------------------------|----------|------------|------------------|
|1|*H*==1|16|`push {r0-r3}`|04|
|2|*C*==1 veya *L*==1 veya *R*==0 veya PF==1|16/32|`push {registers}`|80-BF/D0-DF/EC-ED|
|3a|*C*==1 ve (*L*==0 ve *R*==1 ve PF ==0)|16|`mov r11,sp`|C0-CF/FB|
|3b|*C*==1 ve (*L*==1 veya *R*==0 veya PF ==1)|32|`add r11,sp,#xx`|Fc|
|4|*R*==1 ve *Reg* != 7|32|`vpush {d8-dE}`|E0-E7|
|5|*Yığın Ayarlama* != 0 ve PF ==0|16/32|`sub sp,sp,#xx`|00-7F/E8-EB|

*H* biti 1 olarak ayarlanmışsa, 1 öğretim iyonu her zaman vardır.

Çerçeve zincirlemesi ayarlamak için, *C* biti ayarlanmışsa 3a veya 3b yönergesi bulunur. R11 ve LR dışında hiçbir kayıt itilirse 16-bit; `mov` aksi takdirde, bir 32-bit `add`.

Katlanmış olmayan bir ayarlama belirtilirse, yönerge 5 açık yığın ayarıdır.

Talimatlar 2 ve 4 bir itme gerekli olup olmadığını temel alınatır. Bu tablo, *c,* *l,* *r*ve *PF* alanlarına göre hangi kayıtların kaydedildiği özetlenir. Her *durumda, N* *Reg* + 4'e eşittir, *E* *Reg* + 8'e eşittir ve *S* (~*Stack Adjust*) & 3'e eşittir.

|C|L|R|PF|Karşıcı Kayıtları İtilmiş|VFP Registers itti|
|-------|-------|-------|--------|------------------------------|--------------------------|
|0|0|0|0|r4-r*N*|yok|
|0|0|0|1|r*S*-r*N*|yok|
|0|0|1|0|yok|d8-d*E*|
|0|0|1|1|r*S*-r3|d8-d*E*|
|0|1|0|0|r4-r*N*, LR|yok|
|0|1|0|1|r*S*-r*N*, LR|yok|
|0|1|1|0|LR|d8-d*E*|
|0|1|1|1|r*S*-r3, LR|d8-d*E*|
|1|0|0|0|r4-r*N*, r11|yok|
|1|0|0|1|r*S*-r*N*, r11|yok|
|1|0|1|0|r11|d8-d*E*|
|1|0|1|1|r*S*-r3, r11|d8-d*E*|
|1|1|0|0|r4-r*N*, r11, LR|yok|
|1|1|0|1|r*S*-r*N*, r11, LR|yok|
|1|1|1|0|r11, LR|d8-d*E*|
|1|1|1|1|r*S*-r3, r11, LR|d8-d*E*|

Kanonik işlevler için epiloglar benzer bir formu izler, ancak ters ve bazı ek seçenekler le. Epilog en fazla 5 talimatlar uzunluğunda olabilir ve formu kesinlikle prolog şeklinde dikte edilir.

|Yönerge|Opcode varsayılarak:|Boyut|Işlem kodu|
|-----------------|-----------------------------------|----------|------------|
|6|*Yığın Ayarlama*!=0 ve *EF*==0|16/32|`add   sp,sp,#xx`|
|7|*R*==1 ve *Reg*!=7|32|`vpop  {d8-dE}`|
|8|*C*==1 veya (*L*==1 ve *H*==0) veya *R*==0 veya *EF*==1|16/32|`pop   {registers}`|
|9a|*H*==1 ve *L*==0|16|`add   sp,sp,#0x10`|
|9b|*H*==1 ve *L*==1|32|`ldr   pc,[sp],#0x14`|
|10a|*Ret*==1|16|`bx    reg`|
|10b|*Ret*==2|32|`b     address`|

Yönerge 6, katlanmış olmayan bir ayarlama belirtilmişse açık yığın ayarıdır. *PF* *EF'den*bağımsız olduğundan, yönerge 6 veya tam tersi olmadan 5 yönergesi mevcut olması mümkündür.

7 ve 8 yönergeleri, hangi kayıtların yığından geri yüklenir belirlemek için önsözle aynı mantığı kullanır, ancak bu iki değişiklikle: birincisi, *EF* *PF*yerine kullanılır; ikincisi, *Eğer Ret* = 0, sonra LR kayıt listesinde PC ile değiştirilir ve son sözlemi hemen sona erer.

*H* ayarlanırsa, 9a veya 9b yönergesi bulunur. L 0 *olduğunda,* LR yığının üzerinde olmadığını belirtmek için 9a yönergesi kullanılır. Bu durumda, yığın el ile ayarlanır ve Açık bir dönüş belirtmek için *Ret* 1 veya 2 olmalıdır. Yönerge 9b, *L* 1 olduğunda, epilogun erken sonunu belirtmek ve yığını aynı anda döndürmek ve ayarlamak için kullanılır.

Son söz le sona ermediyse, *Ret*değerine göre 16 bit veya 32 bit lik bir dalı belirtmek için 10a veya 10b yönergesi vardır.

### <a name="xdata-records"></a>.xdata Kayıtları

Paketlenmiş gevşeme biçimi bir işlevin gevşemesini açıklamak için yetersiz olduğunda, değişken uzunlukta bir .xdata kaydı oluşturulmalıdır. Bu kaydın adresi .pdata kaydının ikinci sözcüğünde depolanır. .xdata biçimi dört bölümden oluşan paketlenmiş değişken uzunlukta bir sözcük kümesidir:

1. .xdata yapısının genel boyutunu açıklayan ve anahtar işlev verilerini sağlayan 1 veya 2 sözcüklü üstbilgi. İkinci sözcük yalnızca *Epilog Sayısı* ve *Kod Sözcükleri* alanları nın her ikisi de 0 olarak ayarlanmışsa bulunur. Bu tabloda alanlar kırılır:

   |Word|Bits|Amaç|
   |----------|----------|-------------|
   |0|0-17|*İşlev Uzunluğu,* baytlar halindeki işlevin toplam uzunluğunu gösteren ve 2'ye bölünen 18 bitlik bir alandır. Bir işlev 512 KB'den büyükse, işlevi açıklamak için birden çok .pdata ve .xdata kaydı kullanılmalıdır. Ayrıntılar için bu belgedeki Büyük İşlevler bölümüne bakın.|
   |0|18-19|*Vers,* kalan xdata sürümünü açıklayan 2 bitlik bir alandır. Yalnızca sürüm 0 şu anda tanımlanmıştır; 1-3 değerleri ayrılmıştır.|
   |0|20|*X,* özel durum verilerinin varlığını (1) veya devamsızlığı (0) gösteren 1 bitlik bir alandır.|
   |0|21|*E,* tek bir epilogaçıklayan bilgilerin daha sonra (0) ek kapsam sözcükleri gerektirmek yerine üstbilginin (1) içine paketlenmiş olduğunu belirten 1 bitlik bir alandır.|
   |0|22|*F,* bu kaydın bir işlev parçasını (1) veya tam işlev (0) açıkladığını gösteren 1 bitlik bir alandır. Bir parça, önsöz olmadığını ve tüm prolog işlemlerinin göz ardı edilmesi gerektiğini ima eder.|
   |0|23-27|*Epilogue Count,* *E* bitinin durumuna bağlı olarak iki anlamı olan 5 bitlik bir alandır:<br /><br /> - *E* 0 ise, bu alan bölüm 3'te açıklanan toplam özel durum kapsamı sayısıdır. İşlevde 31'den fazla kapsam varsa, uzantı sözcüğünün gerekli olduğunu belirtmek için bu alan ve *Kod Sözcükleri* alanının her ikisi de 0 olarak ayarlanmalıdır.<br />- *E* 1 ise, bu alan yalnızca epilogaçıklayan ilk gevşeme kodu dizini belirtir.|
   |0|28-31|*Kod Sözcükleri,* bölüm 4'teki tüm gevşeme kodlarını içerecek şekilde gereken 32 bit sözcüklerin sayısını belirten 4 bitlik bir alandır. 63'ten fazla gevşeyen kod baytı için 15'ten fazla sözcük gerekiyorsa, uzantı sözcüğünün gerekli olduğunu belirtmek için bu alan ve *Epilog Sayısı* alanının her ikisi de 0 olarak ayarlanmalıdır.|
   |1|0-15|*Genişletilmiş Epilog Sayısı,* alışılmadık sayıda epilog kodlamak için daha fazla alan sağlayan 16 bitlik bir alandır. Bu alanı içeren uzantı sözcüğü yalnızca ilk üstbilgi sözcüğündeki *Epilog Sayısı* ve *Kod Sözcükleri* alanları nın her ikisi de 0 olarak ayarlanırsa bulunur.|
   |1|16-23|*Genişletilmiş Kod Sözcükleri,* alışılmadık derecede çok sayıda gevşeme kodu sözcüğünün kodlanması için daha fazla alan sağlayan 8 bitlik bir alandır. Bu alanı içeren uzantı sözcüğü yalnızca ilk üstbilgi sözcüğündeki *Epilog Sayısı* ve *Kod Sözcükleri* alanları nın her ikisi de 0 olarak ayarlanırsa bulunur.|
   |1|24-31|Ayrıldı|

1. Özel durum verilerinden sonra (üstbilgideki *E* biti 0 olarak ayarlanmışsa), bir kelimeye bir olarak paketlenen ve artan başlangıç mahsup sırasına göre depolanan epilog kapsamları hakkında bir bilgi listesidir. Her kapsam şu alanları içerir:

   |Bits|Amaç|
   |----------|-------------|
   |0-17|*Epilogue Start Ofset,* işlevin başlangıcına göre 2'ye bölünen baytlarda, epilogun mahsupunu açıklayan 18 bitlik bir alandır.|
   |18-19|*Res,* gelecekteki genişleme için ayrılmış 2 bitlik bir alandır. Değeri 0 olmalıdır.|
   |20-23|*Koşul,* epilogun yürütülme koşulunu veren 4 bitlik bir alandır. Koşulsuz epiloglar için, "her zaman" anlamına gelen 0xE olarak ayarlanmalıdır. (Bir epilog tamamen koşullu veya tamamen koşulsuz olmalıdır ve Thumb-2 modunda, epilog BT opcode sonra ilk öğretim ile başlar.)|
   |24-31|*Epilog Başlangıç Dizini,* bu epilogu açıklayan ilk gevşeme kodunun bayt dizini gösteren 8 bitlik bir alandır.|

1. Epilog kapsamları listesinden sonra, bu makaledeki Gevşeme Kodları bölümünde ayrıntılı olarak açıklanan gevşeme kodları içeren bir dizi bayt gelir. Bu dizi, en yakın tam sözcük sınırının sonunda yastıklı. Baytlar, doğrudan küçük endian modunda getirilebilmeleri için küçük endian sırayla saklanır.

1. Üstbilgideki *X* alanı 1 ise, gevşeme kodu baytları özel durum işleyicisi bilgileri tarafından izlenir. Bu, özel durum işleyicisinin adresini içeren bir *Özel Durum İşleyicisi RVA'dan* oluşur ve bunu hemen ardından özel durum işleyicisi tarafından gerekli olan (değişken uzunlukta) veri miktarı ndan oluşur.

.xdata kaydı, izleyen değişken boyutlu özel durum verilerinin uzunluğu hariç olmak üzere, ilk 8 baytı getirip kaydın tam boyutunu hesaplayabilmek için tasarlanmıştır. Bu kod snippet kayıt boyutunu kaydeder:

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

Önsöz ve her sondan, gevşeme kodlarına bir dizin olmasına rağmen, tablo aralarında paylaşılır. Hepsinin aynı gevşeme kodlarını paylaşması nadir değildir. Belirtilen en büyük dizin 255 olduğundan ve belirli bir işlev için mümkün olan toplam gevşeme kodu sayısını sınırladığı için derleyici yazarların bu durum için en iyi duruma getirmelerini öneririz.

### <a name="unwind-codes"></a>Kodları Gevşet

Gevşeme kodları dizisi, işlemlerin geri alınması gereken sırada prologun etkilerini tam olarak nasıl geri alsüreceğini açıklayan bir yönerge dizileri havuzudur. Gevşeme kodları, bayt dizisi olarak kodlanmış mini bir yönerge kümesidir. Yürütme tamamlandığında, arama işlevinin iade adresi LR kaydındadır ve tüm geçici olmayan kayıtlar işlevçağrıldığı anda değerlerine geri yüklenir.

İstisnalar yalnızca bir işlev gövdesi içinde ve hiçbir zaman bir prolog veya epilog içinde meydana gelmesi garanti edildiyse, yalnızca bir gevşeme dizisi gerekir. Ancak, Windows gevşeme modeli kısmen yürütülmüş bir önsöz veya epilog içinde gevşemek için bir yetenek gerektirir. Bu gereksinimi karşılamak için, gevşeme kodları, prolog ve sonsözdeki her ilgili opcode için bire bir eşleme olacak şekilde dikkatle tasarlanmıştır. Bunun çeşitli etkileri vardır:

- Gevşeme kodlarının sayısını sayarak prolog ve epiloguzunu hesaplamak mümkündür. 16-bit ve 32-bit opcodes için farklı eşlemeler olduğundan bu değişken uzunlukta Thumb-2 talimatları ile bile mümkündür.

- Bir sonsöz kapsamının başlangıcından önceki yönerge lerin sayısını sayarak, eşdeğer gevşeme kodu sayısını atlamak ve sonsözün gerçekleştirdiği kısmen yürütülmüş gevşemeişlemini tamamlamak için bir dizinin geri kalanını yürütmek mümkündür.

- Prologun bitiminden önce yönergelerin sayısını sayarak, eşdeğer gevşeme kodları sayısını atlamak ve yürütmeyi tamamlamış prologun yalnızca bu bölümlerini geri almak için sıranın geri kalanını yürütmek mümkündür.

Aşağıdaki tablo, gevşeme kodlarından opcodes'a eşleme gösterir. En yaygın kodlar sadece bir bayt, daha az yaygın olanlar ise iki, üç, hatta dört bayt gerektirir. Her kod en önemli bayttan en az önemli bayta kadar depolanır. Bu gevşeme kodu yapısı ARM EABI'de açıklanan kodlamadan farklıdır, çünkü bu gevşeme kodları, kısmen çalıştırılan prologların ve epilogların gevşemesine olanak sağlamak için prolog ve epilogdaki opcode'lara bire bir eşleme yapacak şekilde tasarlanmıştır.

|Bayt 1|Bayt 2|Bayt 3|Bayt 4|Opsize|Açıklama|
|------------|------------|------------|------------|------------|-----------------|
|00-7F arası||||16|`add   sp,sp,#X`<br /><br /> X nerede (Kod & 0x7F) \* 4|
|80-BF|00-FF|||32|`pop   {r0-r12, lr}`<br /><br /> Kod & 0x2000 ve r0-r12' nin şifresi, ilgili bit kod & 0x1FFF'de ayarlanırsa LR'nin kırıldığı yer|
|C0-CF||||16|`mov   sp,rX`<br /><br /> x kod & 0x0F nerede|
|D0-D7||||16|`pop   {r4-rX,lr}`<br /><br /> X'in olduğu yer (Kod & 0x03) + 4 ve LR, Kod & 0x04|
|D8-DF||||32|`pop   {r4-rX,lr}`<br /><br /> X nerede (Kod & 0x03) + 8 ve LR kodu 0x04 &|
|E0-E7||||32|`vpop  {d8-dX}`<br /><br /> X nerede (Kod & 0x07) + 8|
|E8-EB|00-FF|||32|`addw  sp,sp,#X`<br /><br /> X nerede (Kod & 0x03FF) \* 4|
|EC-ED|00-FF|||16|`pop   {r0-r7,lr}`<br /><br /> Kod & 0x0100 ve r0-r7' nin kodu 0x00FF'& ayarlanırsa LR'nin atıldığı yer|
|EE|00-0F arası|||16|Microsoft'a özgü|
|EE|10-FF|||16|Kullanılabilir|
|Ef|00-0F arası|||32|`ldr   lr,[sp],#X`<br /><br /> X nerede (Kod & 0x000F) \* 4|
|Ef|10-FF|||32|Kullanılabilir|
|F0-F4||||-|Kullanılabilir|
|F5|00-FF|||32|`vpop  {dS-dE}`<br /><br /> S (Kod & 0x00F0) >> 4 ve E Kod & 0x000F|
|F6|00-FF|||32|`vpop  {dS-dE}`<br /><br /> S nerede ((Kod & 0x00F0) >> 4) + 16 ve E (Kod & 0x000F) + 16|
|F7|00-FF|00-FF||16|`add   sp,sp,#X`<br /><br /> X nerede (Kod & 0x00FFFF) \* 4|
|F8|00-FF|00-FF|00-FF|16|`add   sp,sp,#X`<br /><br /> X nerede (Kod & 0x00FFFFFF) \* 4|
|F9|00-FF|00-FF||32|`add   sp,sp,#X`<br /><br /> X nerede (Kod & 0x00FFFF) \* 4|
|Fa|00-FF|00-FF|00-FF|32|`add   sp,sp,#X`<br /><br /> X nerede (Kod & 0x00FFFFFF) \* 4|
|Fb||||16|nop (16-bit)|
|Fc||||32|nop (32-bit)|
|Fd||||16|sonsözde son + 16 bit nop|
|Fe||||32|sonsözde son + 32-bit nop|
|Ff||||-|end|

Bu, opcode boyutu *Opsize* ve ilgili özgün yönerge yorumu ile birlikte, bir gevşeme kodu *Kodu*her bayt için hexadecimal değerlerin aralığını gösterir. Boş hücreler daha kısa gevşeme kodlarını gösterir. Birden çok baytı kapsayan büyük değerlere sahip yönergelerde, önce en önemli bitler depolanır. *Opsize* alanı, her Başparmak-2 işlemiyle ilişkili örtük opcode boyutunu gösterir. Tabloda farklı kodlamalar içeren görünen yinelenen girişler, farklı kod boyutları arasında ayrım yapmak için kullanılır.

Açma kodları, kodun ilk baytının hem kodun baytlarının toplam boyutunu hem de yönerge akışındaki ilgili opkodun boyutunu belirtebilecek şekilde tasarlanmıştır. Prolog veya epilog boyutunu hesaplamak için, dizinin başından sonuna kadar gevşeme kodlarını yürüyün ve ilgili opcode ne kadar uzun olduğunu belirlemek için bir arama tablosu veya benzer bir yöntem kullanın.

0xFD ve 0xFE kodları normal son kodu 0xFF eşdeğerdir, ancak sonsöz durumda bir ekstra nop opcode için hesap, ya 16-bit veya 32-bit. Prologlar için 0xFD, 0xFE ve 0xFF kodları tam olarak eşdeğerdir. Bu, eşdeğer bir prolog `bx lr` `b <tailcall-target>`yönergesi olmayan veya ortak sonsöz sonları için hesaplar. Bu, gevşeme dizilerinin prolog ve epiloglar arasında paylaşılabiliyor olasılığını artırır.

Çoğu durumda, prolog ve tüm epiloglar için aynı gevşeme kodları kümesini kullanmak mümkün olmalıdır. Ancak, kısmen yürütülmüş prologların ve epilogların gevşemesini işlemek için, sıralama veya davranış açısından farklılık gösteren birden çok gevşeme kodu diziniz olması gerekebilir. Bu nedenle, her epilogun yürütmeye nereden başlayacağını göstermek için gevşeme dizisine kendi dizini vardır.

### <a name="unwinding-partial-prologues-and-epilogues"></a>Kısmi Prologları ve Epilogları Gevşetme

En yaygın gevşeme durumu, özel durumun işlevin gövdesinde, prologve tüm epiloglardan uzakta meydana gelmesidir. Bu durumda, gevşetici dizin 0'dan başlayarak gevşeme dizisindeki kodları yürütür ve bir son opkodu algılanıncaya kadar devam eder.

Bir önsöz veya epilog yürütüldüğünde bir özel durum oluştuğunda, yığın çerçevesi yalnızca kısmen oluşturulur ve gevşeticinin doğru şekilde geri almak için tam olarak ne yapıldığını belirlemesi gerekir.

Örneğin, bu önsöz ve epilog dizisini göz önünde bulundurun:

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

Her opcode yanında bu işlemi açıklamak için uygun gevşeme kodudur. Prolog için gevşeme kodları dizisi son yönergesi sayma değil, sonsöz için gevşeme kodları bir ayna görüntüsüdür. Bu durum yaygındır ve prolog unwind kodları her zaman prolog yürütme emrinden ters sırada depolanacak varsayılır nedenidir. Bu bize ortak bir gevşeme kodları kümesi verir:

```asm
0xc7, 0xdd, 0x04, 0xfd
```

0xFD kodu, dizinin sonu için önsözden 16 bit daha uzun bir talimat anlamına gelen özel bir koddur. Bu, gevşeme kodlarının daha fazla paylaşılmasını mümkün kılar.

Örnekte, prolog ve epilog arasındaki işlev gövdesi yürütülerken bir özel durum oluşursa, sonişlem kodu içinde 0'da gevşeme sonişlem durumuyla başlar. Bu örnekte 0x140 ofset karşılık gelir. Temizleme yapılmadığından, gevşeyen tam gevşeme sırasını çalıştırıyor. Bunun yerine özel durum, son sözleme kodunun başlangıcından sonra bir yönerge oluşursa, gevşetici ilk gevşey kodunu atlayarak başarılı bir şekilde gevşeyebilir. Opcodes ve gevşeme kodları arasında bire bir eşleme göz önüne alındığında, son sözde *n* yönergesinden gevşeme varsa, gevşetici ilk *n* gevşeme kodlarını atlamalıdır.

Benzer mantık önsöz için ters çalışır. Önsözde ofset 0'dan gevşemek durumunda, hiçbir şey yürütülmemalıdır. Bir yönergeden gevşeme durumunda, prolog açma kodları ters sırada depolandığı için, gevşeme sırası sondan bir gevşeme kodu başlamalıdır. Genel durumda, önsözden *n* talimatından gevşemek durumunda, açma kodları listesinin sonundan *itibaren n* gevşetme kodlarında yürütmeye başlamalıdır.

Prolog ve epilog gevşeme kodları her zaman tam olarak eşleşmiyor. Bu durumda, gevşeme kodu dizisi nin birkaç kod dizisini içermesi gerekebilir. Kodları işlemeye başlamak için mahsup belirlemek için şu mantığı kullanın:

1. İşlevin gövdesi içinden gevşeme varsa, dizin 0'da kodları gevşetmeye başlayın ve bir son opcode'a ulaşılıncaya kadar devam edin.

2. Bir sonsöz içinden gevşemek istiyorsanız, epilog kapsamı tarafından sağlanan epiloga özgü başlangıç dizinini kullanın. Sonsözün başlangıcından itibaren bilgisayarın kaç bayt olduğunu hesaplayın. Zaten yürütülmüş tüm yönergeler hesaba katılıncaya kadar açma kodlarını ileri atlayın. Bu noktadan itibaren gevşeme sırasını çalıştırın.

3. Önsözünden gevşeme varsa, gevşeme kodlarındaki dizin 0'dan başlayın. Prolog kodunun dizideki uzunluğunu hesaplayın ve ardından önsözün sonundan itibaren pc'nin kaç bayt olduğunu hesaplayın. Yürütülmemiş tüm yönergeler hesaba katılıncaya kadar açma kodları arasında ileri atlayın. Bu noktadan itibaren gevşeme sırasını çalıştırın.

Önsöz için gevşeme kodları her zaman dizideki ilk olmalıdır. Onlar da vücudun içinden gevşeme genel durumda gevşemek için kullanılan kodlar vardır. Epiloga özgü kod dizileri, prolog kod dizisinden hemen sonra izlemelidir.

### <a name="function-fragments"></a>Fonksiyon Parçaları

Kod optimizasyonu için, bir işlevi ayrık parçalara bölmek yararlı olabilir. Bu yapıldığında, her işlev parçası kendi ayrı .pdata gerektirir-ve muhtemelen .xdata-kayıt.

İşlev önsözünün işlevin başında olduğunu ve bölünemediğini varsayarsak, dört işlev parçası örnekleri vardır:

- Prolog sadece; diğer parçalardaki tüm epiloglar.

- Prolog ve bir veya daha fazla epiloglar; diğer parçalarda ek epiloglar.

- Hiçbir prolog veya epilogs; prolog ve diğer parçalarda bir veya daha fazla epilog.

- Sadece epiloglar; prolog ve diğer parçalar muhtemelen ek epiloglar.

İlk durumda, yalnızca önsöz açıklanmalıdır. Bu, prologu normal olarak tanımlayarak ve sonyok belirtmek için 3 *Ret* değeri belirterek kompakt .pdata formunda yapılabilir. Tam .xdata formunda, bu durum her zamanki gibi dizin 0'da prolog gevşeme kodları sağlayarak ve 0'ın epilog sayısı belirtilerek yapılabilir.

İkinci durum normal bir fonksiyon gibidir. Parçada yalnızca bir son söz varsa ve parçanın sonundaysa, kompakt bir .pdata kaydı kullanılabilir. Aksi takdirde, tam bir .xdata kaydı kullanılmalıdır. Sonsyon başlangıcı için belirtilen uzaklıkların işlevin özgün başlangıcına değil, parçanın başlangıcına göre olduğunu unutmayın.

Üçüncü ve dördüncü olgular, bir prolog içermedikleri sürece sırasıyla birinci ve ikinci olguların türevleridir. Bu gibi durumlarda, epilog başlamadan önce kod olduğu varsayılır ve normalde prolog etkilerini geri alarak çözülmüş olurdu fonksiyonun vücut, bir parçası olarak kabul edilir. Bu nedenle bu durumlarda, vücudun içinden nasıl gevşemek açıklar, ancak parçanın başında kısmi bir gevşeme gerçekleştirmek için olup olmadığını belirlerken 0 uzunlukta olarak kabul edilir bir sözde prolog ile kodlanmış olmalıdır. Alternatif olarak, bu sözde prolog, muhtemelen eşdeğer işlemler gerçekleştirdikleri için sonsözle aynı gevşeme kodları kullanılarak tanımlanabilir.

Üçüncü ve dördüncü durumlarda, sözde prolog un varlığı, kompakt .pdata kaydının *Bayrak* alanını 2'ye ayarlayarak veya .xdata üstbilgisindeki *F* bayrağını 1'e ayarlayarak belirtilir. Her iki durumda da, kısmi bir prolog gevşeme için kontrol yoksayılır ve tüm epilog olmayan gevşeme ler dolu olarak kabul edilir.

#### <a name="large-functions"></a>Büyük Fonksiyonlar

Parçalar, .xdata üstbilgisindeki bit alanları tarafından dayatılan 512 KB sınırından daha büyük işlevleri tanımlamak için kullanılabilir. Çok büyük bir işlevi tanımlamak için, 512 KB'den daha küçük parçalara ayırmanızı. Her parça, bir epilogu birden çok parçaya bölmeyecek şekilde ayarlanmalıdır.

Fonksiyonun yalnızca ilk parçası bir önsöz içerir; diğer tüm parçaların önsözü yoktur olarak işaretlenir. Epilog sayısına bağlı olarak, her parça sıfır veya daha fazla epilog içerebilir. Bir parçadaki her epilog kapsamının, işlevin başlangıcına değil, parçanın başlangıcına göre başlangıç ofsetini belirlediğini unutmayın.

Bir parçanın önsözü ve sonbölümü yoksa, işlevin gövdesi içinden nasıl gevşeyilsüreceğini açıklamak için yine de kendi .pdata ve muhtemelen .xdata-kaydı gerektirir.

#### <a name="shrink-wrapping"></a>Küçültme-sarma

İşlev parçalarının daha karmaşık özel bir örneği, kayıt tasarrufu gerektirmeyen basit durumlar için en iyi duruma getirmek için, işlevin başlangıcından daha sonra işleve kaydedilen kayıt tasarruflarını erteleyen bir teknik olan *küçültme-paketlemedir.* Bu, yığın alanını ayıran ancak en az kayıt kümesini kaydeden bir dış bölge ve ek kayıtları kaydeden ve geri yükleyen bir iç bölge olarak tanımlanabilir.

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

Küçültme yle sarılmış işlevlerin genellikle normal prologdaki ekstra kayıt kayıtları için alanı önceden ayırması ve ardından kayıt `str` `stm` kayıtlarının `push`kullanılması veya yerine gerçeklemesi beklenir. Bu, işlevin özgün önözünde tüm yığın işaretçisi işlemetutar.

Örnek küçültülmüş işlev, yorumlarda A, B ve C olarak işaretlenmiş üç bölgeye bölünmelidir. İlk A bölgesi, ek geçici olmayan kayda son la işlevi kapsar. Bir .pdata veya .xdata kaydı, bu parçayı bir önsöze sahip ve sondası olmayan olarak tanımlamak için oluşturulmalıdır.

Orta B bölgesi, prologve sondası olmayan bir parçayı açıklayan kendi .pdata veya .xdata kaydına sahip olur. Ancak, bir işlev gövdesi olarak kabul edilir, çünkü bu bölge için gevşeme kodları hala mevcut olmalıdır. Kodlar, hem bölge-A önlogueunda kaydedilen özgün kayıtları hem de B bölgesine girmeden önce kaydedilen ek kayıtları temsil eden bir bileşik önselogueu, sanki bir işlem dizisi tarafından üretiliyormuş gibi tanımlamalıdır.

B bölgesi için açıklanan bileşik önsöz hem bölge-A prologunu hem de kaydedilen ek kayıtları tanımlaması gerektiğinden, B bölgesi için kayıt kayıtları "iç prolog" olarak kabul edilemez. B parçası bir önsöze sahip olarak tanımlanmışsa, gevşeme kodları da bu önsözün boyutunu ima eder ve bileşik önsözü yalnızca ek kayıtları kaydeden opcodes ile eşleyen bir şekilde tanımlamanın bir yolu yoktur.

Ek kayıt kayıtları A bölgesinin bir parçası olarak kabul edilmelidir, çünkü tamamlanana kadar bileşik prolog yığının durumunu tam olarak tanımlamaz.

Son C bölgesi, prologsuz ancak bir sonsözü olan bir parçayı açıklayan kendi .pdata veya .xdata kaydına sahip olur.

B bölgesine girmeden önce yapılan yığın manipülasyonu tek bir yönergeye indirgenebiliyorsa, alternatif bir yaklaşım da işe yarayabilir:

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

Burada anahtar, her talimat sınırında, yığının bölge için gevşeme kodlarıyla tamamen tutarlı olmasıdır. Bu örnekte iç itmeden önce bir gevşeme oluşursa, A bölgesinin bir parçası olarak kabul edilir ve yalnızca Bir önsözü çözülmeye alınır. Eğer gevşeme iç itme den sonra gerçekleşirse, önsözü olmayan, ancak hem iç itme yi hem de A bölgesinden gelen orijinal prologu tanımlayan gevşeme kodları olan B bölgesinin bir parçası olarak kabul edilir.

### <a name="encoding-optimizations"></a>Optimizasyonları Kodlama

Gevşeme kodlarının zenginliği ve kompakt ve genişletilmiş veri formlarından yararlanma becerisi nedeniyle, alanı daha da azaltmak için kodlamayı optimize etmek için birçok fırsat vardır. Bu tekniklerin agresif kullanımı ile, gevşeme kodları kullanarak işlevleri ve parçaları açıklayan net yükü oldukça az olabilir.

En önemli optimizasyon, prolog/epilog sınırlarını derleme perspektifinden mantıksal prolog/epilog sınırları ile gevşetme amacıyla karıştırmamaya dikkat etmektir. Gevşeme sınırları küçültülebilir ve verimliliği artırmak için daha sıkı hale getirilebilir. Örneğin, ek doğrulama denetimleri gerçekleştirmek için yığın kurulumundan sonra bir önsöz kod içerebilir. Ancak tüm yığın manipülasyonu tamamlandıktan sonra, daha fazla işlemi kodlamaya gerek yoktur ve bunun ötesindeki her şey gevşeme önsözünden kaldırılabilir.

Aynı kural işlev uzunluğu için de geçerlidir. Bir işlevdeki bir epilogizleyen gerçek bir havuz varsa, işlev uzunluğunun bir parçası olarak eklenmemelidir. İşlevin sadece işlevin bir parçası olan koda küçültülerek, son sözün en sonunda ve kompakt olması olasılığı çok daha fazladır. pdata kaydı kullanılabilir.

Bir önsözde, yığın işaretçisi başka bir kayda kaydedildikten sonra, genellikle başka bir opcodes kaydetmeye gerek yoktur. İşlevi gevşetmek için yapılan ilk şey Kaydedilen kayıttan SP kurtarmaktır ve bu nedenle daha fazla işlem gevşeme üzerinde herhangi bir etkiye sahip değildir.

Tek öğretimli epilogların kapsam olarak veya gevşeme kodları olarak kodlanmış olması gerekmez. Bu talimat yürütülmeden önce bir gevşeme gerçekleşirse, o zaman işlevin gövdesi içinden olduğu varsayılabilir ve sadece prolog gevşeme kodları yürütme yeterlidir. Tek bir yönerge yürütüldükten sonra gevşeme gerçekleşirse, tanım gereği başka bir bölgede gerçekleşir.

Çok yönergeli epiloglar, önceki noktayla aynı nedenle epilogun ilk talimatını kodlamak zorunda değildir: bu talimat yürürlüğe girmeden önce gevşeme gerçekleşirse, tam bir prolog gevşeme yeterlidir. Bu talimattan sonra gevşeme gerçekleşirse, yalnızca sonraki işlemler dikkate alınmalı.

Kodu yeniden gevşetme agresif olmalıdır. Her epilog kapsamı tarafından belirtilen dizin, gevşeme kodları dizisinde rasgele bir başlangıç noktasına işaret eder. Bir önceki dizinin başlangıcına işaret etmek zorunda değildir; ortaya işaret edebilir. Buradaki en iyi yaklaşım, istenilen kod dizisini oluşturmak ve daha sonra zaten kodlanmış diziler havuzunda tam bir bayt eşleşmesi tarayabilmek ve herhangi bir mükemmel eşleşmeyi yeniden kullanım için bir başlangıç noktası olarak kullanmaktır.

Tek öğretimli epiloglar göz ardı edildikten sonra, kalan epiloglar yoksa, kompakt bir .pdata formu kullanmayı düşünün; bir epilog yokluğunda çok daha olası hale gelir.

## <a name="examples"></a>Örnekler

Bu örneklerde, görüntü tabanı 0x00400000'dir.

### <a name="example-1-leaf-function-no-locals"></a>Örnek 1: Yaprak Fonksiyonu, No Locals

```asm
Prologue:
  004535F8: B430      push        {r4-r5}
Epilogue:
  00453656: BC30      pop         {r4-r5}
  00453658: 4770      bx          lr
```

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x000535F8 (= 0x004535F8-0x00400000)

- Kelime 1

  - *Kamçı* = 1, kanonik prolog ve epilog biçimlerini gösteren

  - *İşlev Uzunluğu* = 0x31 (= 0x62/2)

  - *Ret* = 1, 16 bit dal dönüşünü gösteren

  - *H* = 0, parametrelerin evde olmadığını gösteren

  - *R*=0 ve *Reg* = 1, r4-r5'in itme/pop'unun göstergesi

  - *L* = 0, lr kaydet/geri yükleme yok

  - *C* = 0, çerçeve zincirleme olmadığını gösteren

  - *Yığın Ayarlama* = 0, hiçbir yığın ayarı gösteren

### <a name="example-2-nested-function-with-local-allocation"></a>Örnek 2: Yerel Ayırma ile İç Içe İşlev

```asm
Prologue:
  004533AC: B5F0      push        {r4-r7, lr}
  004533AE: B083      sub         sp, sp, #0xC
Epilogue:
  00453412: B003      add         sp, sp, #0xC
  00453414: BDF0      pop         {r4-r7, pc}
```

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x000533AC (= 0x004533AC -0x00400000)

- Kelime 1

  - *Kamçı* = 1, kanonik prolog ve epilog biçimlerini gösteren

  - *İşlev Uzunluğu* = 0x35 (= 0x6A/2)

  - *Ret* = 0, bir pop {pc} dönüş gösteren

  - *H* = 0, parametrelerin evde olmadığını gösteren

  - *R*=0 ve *Reg* = 3, r4-r7'nin itme/pop'unun göstergesi

  - *L* = 1, LR'nin kaydedildiğini/geri yüklenmesini gösteren

  - *C* = 0, çerçeve zincirleme olmadığını gösteren

  - *Yığın Ayarlama* = 3 (= 0x0C/4)

### <a name="example-3-nested-variadic-function"></a>Örnek 3: İç içe variadik fonksiyon

```asm
Prologue:
  00453988: B40F      push        {r0-r3}
  0045398A: B570      push        {r4-r6, lr}
Epilogue:
  004539D4: E8BD 4070 pop         {r4-r6}
  004539D8: F85D FB14 ldr         pc, [sp], #0x14
```

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x00053988 (= 0x00453988-0x00400000)

- Kelime 1

  - *Kamçı* = 1, kanonik prolog ve epilog biçimlerini gösteren

  - *İşlev Uzunluğu* = 0x2A (= 0x54/2)

  - *Ret* = 0, bir pop {pc}tarzı dönüş gösteren (bu durumda bir ldr pc,[sp],#0x14 dönüş)

  - *H* = 1, parametrelerin ev sahibi olduğunu gösteren

  - *R*=0 ve *Reg* = 2, r4-r6'nın itme/pop'unun göstergesi

  - *L* = 1, LR'nin kaydedildiğini/geri yüklenmesini gösteren

  - *C* = 0, çerçeve zincirleme olmadığını gösteren

  - *Yığın Ayarlama* = 0, hiçbir yığın ayarı gösteren

### <a name="example-4-function-with-multiple-epilogues"></a>Örnek 4: Çoklu Epiloglu Fonksiyon

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

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x000592F4 (= 0x004592F4-0x00400000)

- Kelime 1

  - *.xdata* kaydının mevcut olduğunu gösteren bayrak = 0 (birden çok epilog nedeniyle gereklidir)

  - *.xdata adresi* - 0x00400000

.xdata (değişken, 6 kelime):

- Kelime 0

  - *İşlev Uzunluğu* = 0x0001A3 (= 0x000346/2)

  - *Vers* = 0, xdata ilk sürümünü gösteren

  - *X* = 0, özel durum verilerini belirtme

  - *E* = 0, epilog kapsamlarının listesini gösteren

  - *F* = 0, prolog da dahil olmak üzere tam bir fonksiyon açıklaması gösteren

  - *Epilog Sayısı* = 0x04, 4 toplam epilog kapsamlarını gösteren

  - *Kod Kelimeler* = 0x01, gevşeme kodları bir 32-bit kelime gösteren

- 4 noktada 4 epilog kapsamları açıklayan 1-4 kelime. Her kapsamda, 0x00'de önsözle paylaşılan ortak bir gevşeme kodu kümesi vardır ve koşulsuzdur ve 0x0E (her zaman) koşulunu belirtir.

- Word 5'ten başlayarak kodları gevşetin: (prolog/epilog arasında paylaşılır)

  - Kodu çöz 0 = 0x06: sp += (6 << 2)

  - Kodu 1 = 0xDE: pop {r4-r10, lr}

  - Kodu 2 = 0xFF: sonu

### <a name="example-5-function-with-dynamic-stack-and-inner-epilogue"></a>Örnek 5: Dinamik Yığın ve İç Epilog ile Fonksiyon

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

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x00085A20 (= 0x00485A20-0x00400000)

- Kelime 1

  - *.xdata* kaydının mevcut olduğunu gösteren bayrak = 0 (birden çok epilog nedeniyle gerekli)

  - *.xdata adresi* - 0x00400000

.xdata (değişken, 3 kelime):

- Kelime 0

  - *İşlev Uzunluğu* = 0x0001A3 (= 0x000346/2)

  - *Vers* = 0, xdata ilk sürümünü gösteren

  - *X* = 0, özel durum verilerini belirtme

  - *E* = 0, epilog kapsamlarının listesini gösteren

  - *F* = 0, prolog da dahil olmak üzere tam bir fonksiyon açıklaması gösteren

  - *Epilog Sayısı* = 0x001, 1 toplam epilog kapsamını gösteren

  - *Kod Kelimeler* = 0x01, gevşeme kodları bir 32-bit kelime gösteren

- Kelime 1: Ofset 0xC6 'da epilog kapsamı (= 0x18C/2), 0x00'de gevşeme kodu dizinini başlatarak ve 0x0E (her zaman) koşuluyla

- Word 2'den başlayarak kodları gevşetin: (prolog/epilog arasında paylaşılır)

  - Kodu çöz 0 = 0xC6: sp = r6

  - Kodu çöz = 0xDC: pop {r4-r8, lr}

  - Kodu çöz = 0x04: sp += (4 << 2)

  - Kodu 3 = 0xFD:son, son söziçin 16 bit yönerge sayar

### <a name="example-6-function-with-exception-handler"></a>Örnek 6: Özel Durum İşleyicisi ile İşlev

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

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x00088C24 (= 0x00488C24-0x00400000)

- Kelime 1

  - *.xdata* kaydının mevcut olduğunu gösteren bayrak = 0 (birden çok epilog nedeniyle gerekli)

  - *.xdata adresi* - 0x00400000

.xdata (değişken, 5 kelime):

- Kelime 0

  - *İşlev Uzunluğu* =0x000027 (= 0x00004E/2)

  - *Vers* = 0, xdata ilk sürümünü gösteren

  - *X* = 1, özel durum verilerini gösteren

  - *E* = 1, tek bir epilog gösteren

  - *F* = 0, prolog da dahil olmak üzere tam bir fonksiyon açıklaması gösteren

  - *Epilog Sayısı* = 0x00, epilog gevşeme kodları ofset 0x00 başlar gösteren

  - *Kod Kelimeler* = 0x02, gevşeme kodları iki 32-bit kelime gösteren

- Word 1'den başlayarak kodları gevşet:

  - Kodu çöz 0 = 0xC7: sp = r7

  - Kodu çöz = 0x05: sp += (5 << 2)

  - Kodu çöz = 0xED/0x90: pop {r4, r7, lr}

  - Kodu 4 = 0xFF:son

- Word 3 bir özel durum işleyicisi = 0x0019A7ED (= 0x0059A7ED - 0x00400000) belirtir

- 4 ve sonrası sözcükler, satır lı özel durum verileridir

### <a name="example-7-funclet"></a>Örnek 7: Funclet

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

.pdata (sabit, 2 kelime):

- Kelime 0

  - *Fonksiyon Başlangıç RVA* = 0x00088C72 (= 0x00488C72-0x00400000)

- Kelime 1

  - *Kamçı* = 1, kanonik prolog ve epilog biçimlerini gösteren

  - *İşlev Uzunluğu* = 0x0B (= 0x16/2)

  - *Ret* = 0, bir pop {pc} dönüş gösteren

  - *H* = 0, parametrelerin evde olmadığını gösteren

  - *R*=0 ve *Reg* = 7, hiçbir kaydın kaydedilen/geri yüklenmedi

  - *L* = 1, LR'nin kaydedildiğini/geri yüklenmesini gösteren

  - *C* = 0, çerçeve zincirleme olmadığını gösteren

  - *1* × 4 bayt yığını ayarlaması gösteren Yığın Ayarlama = 1

## <a name="see-also"></a>Ayrıca bkz.

[ARM ABI Sözleşmelerine Genel Bakış](overview-of-arm-abi-conventions.md)<br/>
[Genel Visual C++ ARM Geçiş Sorunları](common-visual-cpp-arm-migration-issues.md)
