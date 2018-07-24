---
title: ARM özel durum işleme | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fe0e615f-c033-4ad5-97f4-ff96af45b201
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2047938e25ed235d04b7a851a21a44090194660a
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39209124"
---
# <a name="arm-exception-handling"></a>ARM özel durum işleme

ARM üzerinde Windows Donanım tarafından oluşturulan zaman uyumsuz özel durumları ve zaman uyumlu yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme mekanizmasını kullanır. Dile özgü özel durum işleyicileri dil yardımcı işlevleri kullanarak Windows yapılandırılmış özel durum işleme üzerinde oluşturulur. Bu belgede, özel durum işleme Windows ARM ve Microsoft ARM derleyicisi ve Visual C++ Derleyici tarafından oluşturulan kodu tarafından kullanılan dil Yardımcıları içinde açıklanmıştır.

## <a name="arm-exception-handling"></a>ARM özel durum işleme

ARM üzerinde Windows kullanan *geriye doğru izleme kodları* sırasında yığın geriye doğru izleme denetlemek için [yapılandırılmış özel durum işleme](http://msdn.microsoft.com/library/windows/desktop/ms680657) (SEH). Geriye doğru izleme kodları şunlardır: yürütülebilir resmin sanal işlem bulunur bölümde depolanan bayt dizisi. Arayanın yığın çerçevesi için geriye doğru izleme hazırlanırken bir işlevin prolog etkilerini alınabilir, soyut bir yolla işlev prolog ve Epilog kodu işlemi açıklanmaktadır.

ARM EABI (katıştırılmış uygulama ikili arabirimi) kullanan bir özel durumu geriye doğru izleme modeli geriye doğru izleme kodları belirtir, ancak SEH içindeki zaman uyumsuz durumda işlemci ortasında prolog olduğu işlemelidir Windows, geriye doğru izleme için yeterli değil veya Kapanış işlev. Windows ARM EABI içinde birleşik işlev düzeyi geriye doğru izleme ve dile özgü kapsam geriye doğru izleme, geriye doğru izleme denetimi ayrıca ayırır. Bu nedenlerden dolayı Windows ARM hakkında daha fazla ayrıntı için geriye doğru izleme verileri ve yordamı belirtir.

### <a name="assumptions"></a>Varsayımlar

ARM üzerinde Windows yürütülebilir görüntüler taşınabilir yürütülebilir (PE) biçimini kullanın. Daha fazla bilgi için [Microsoft PE ve COFF belirtimi](http://go.microsoft.com/fwlink/p/?linkid=84140). Özel durum bilgi işleme resminin .pdata ve .xdata bölümlerde depolanır.

Özel durum işleme mekanizmasını, üzerinde ARM ABI Windows için aşağıdaki kod ile ilgili bazı varsayımlarda bulunur:

- Bir işlev gövdesinin içinde bir özel durum oluştuğunda, prolog ait işlemler geri alınır veya kapanış ait işlemler ileriye doğru bir şekilde gerçekleştirilir bir önemi yoktur. Her ikisi de benzer sonuçlar üretmelidir.

- Öğesinin ve sonuçları yansıması eğilimindedir. Bu, geriye doğru izleme açıklamak için gereken meta verilerin boyutunu azaltmak için kullanılabilir.

- İşlevler, nispeten küçük olma eğilimindedir. Çeşitli iyileştirmeler bu etkin verileri paketleme için kullanır.

- Bir koşul üzerinde bir kapanış yerleştirilirse, kapanış her yönerge için eşit oranda geçerlidir.

- Yığın işaretçisi (SP) kaydedilir, böylece özgün SP herhangi bir zamanda kurtarılabilir kayıt kalmalıdır prolog, başka bir kayıttaki işlevi değişmedi.

- Tüm işlenmesini, SP başka bir kayıttaki kaydedilmezse kesinlikle prolog ve epilog içinde gerçekleşmelidir.

- Herhangi bir yığın çerçevesi geriye doğru izlemek için bu işlemler gereklidir:

  - R13 ayarlayın (SP) 4 baytlık halinde.

  - Açılan bir veya daha fazla tamsayı kaydeder.

  - Bir veya daha fazla VFP pop (sanal kayan nokta) kaydeder.

  - Bir rastgele yazmaç değerini r13 için kopyalayın (SP).

  - SP Yığından küçük bir sonrası azaltma işlemi kullanarak yükleyin.

  - Birkaç iyi tanımlanmış çerçeve türlerinden birini ayrıştırılamıyor.

### <a name="pdata-records"></a>.pdata kayıtları

Her yığın düzenleme işlevi tanımlayan sabit uzunluklu öğelerinin sıralı bir diziye bir PE biçimi görüntüde .pdata kayıtlardır. Yığın düzenleme yok, diğer işlevleri çağırmayın işlevleri olan yaprak İşlevler, .pdata kayıt gerektirmez. (Diğer bir deyişle, bunlar herhangi bir yerel depolama alanı gerektirmez ve kaydetmek veya geçici olmayan kayıtlar geri yüklemek gerekmez.). Bu işlevler için kayıtları alanından tasarruf etmek için .pdata bölümünden atlanabilir. Bu işlevlerden biri bir bırakma işlemi yalnızca dönüş adresi bağlantı kaydetme (LR gelen) program sayacının çağırana taşımak (PC) kopyalayabilirsiniz.

ARM her .pdata kaydı 8 bayt uzun içindir. Bir kaydın genel biçimi, değişken uzunluklu sanal işlem bulunur bloğu için bir işaretçi veya kurallı bir işlevi tanımlayan paketlenmiş bir sözcük içeren ikinci bir sözcük ilk 32-bit Word işlevi başlangıç göreli sanal adres (RVA) yerleştirir. Bu tabloda gösterildiği gibi geriye doğru izleme sırası:

|Word uzaklığı|Bits|Amaç|
|-----------------|----------|-------------|
|0|0-31|*İşlevi Başlat RVA* 32-bit RVA işlevi başlangıcı olduğu. İşlev thumb kodu içeriyorsa, bu adres, düşük bit ayarlamanız gerekir.|
|1.|0-1|*Bayrağı* kalan 30 bit ikinci .pdata word'ün yorumlama gösteren bir 2 bit alanıdır. Varsa *bayrağı* 0'dır ve ardından form kalan bitleri bir *özel durum bilgileri RVA* (düşük iki bit örtük olarak 0). Varsa *bayrağı* form kalan bitleri sonra sıfır olan bir *geriye doğru izleme verileri paketlenmiş* yapısı.|
|1.|2-31|*Özel durum bilgilerini RVA* veya *paketlenmiş veri bırakma*.<br /><br /> *Özel durum bilgileri RVA* sanal işlem bulunur bölümde depolanan değişken uzunluklu özel durum bilgisi yapısı adresidir. Bu veriler, 4 bayt hizalı olmalıdır.<br /><br /> *Geriye doğru izleme verileri paketlenmiş* kurallı biçimi varsayılarak bir işlevden geriye doğru izleme için gerekli işlemleri sıkıştırılmış bir açıklaması verilmektedir. Bu durumda, hiçbir sanal işlem bulunur kayıt gereklidir.|

### <a name="packed-unwind-data"></a>Paketlenmiş veri bırakma

Veriler, öğesinin ve sonuçları izleyin, aşağıda açıklanan kurallı biçimi paketlenmiş işlevleri geriye doğru izleme için kullanılabilir. Bu bir sanal işlem bulunur kaydı gereksinimini ortadan kaldırır ve sağlamak için gereken alanı önemli ölçüde azaltır veri bırakma. Kurallı öğesinin ve sonuçları bir özel durum işleyicisi gerektirmez ve kurulumu ve kaldırma işlemlerini gerçekleştiren standart bir sırada, basit bir işlevi ortak gereksinimlerini karşılayacak şekilde tasarlanmıştır.

Bu tablo biçimi gösterir bir .pdata paketlenmiş kayıt veri geriye doğru izleme:

|Word uzaklığı|Bits|Amaç|
|-----------------|----------|-------------|
|0|0-31|*İşlevi Başlat RVA* 32-bit RVA işlevi başlangıcı olduğu. İşlev thumb kodu içeriyorsa, bu adres, düşük bit ayarlamanız gerekir.|
|1.|0-1|*Bayrağı* bu anlamlara sahip 2 bit alanı:<br /><br /> -00 = paketlenmiş kullanılmıyor; veri bırakma Kalan bitleri için sanal işlem bulunur kayıt noktası.<br />-01 = paketlenmiş veri bırakma.<br />-10 = paketlenmiş burada işlevi varsayılır hiçbir prolog sağlamak için veri bırakma. Bu işlev başlangıcı bitişik olmayan işlev parçalarını tanımlamak için yararlıdır.<br />-11 = ayrılmış.|
|1.|2-12|*İşlev uzunluğu* uzunluğu 2 ile bölünen bayt tüm işlevi sağlayan bir 11 bit alanıdır. İşlevin 4 K bayt'tan büyükse, bir tam sanal işlem bulunur kaydı yerine kullanılmalıdır.|
|1.|13-14|*Ret* nasıl işlevi döndürür gösteren 2 bit alanı:<br /><br /> -00 pop {pc} aracılığıyla iade = ( *L* bayrağı biti ayarlanmış olması gerekir 1 Bu durumda).<br />-01 16-bit dal kullanarak dönüş =.<br />-10 32 bit dal kullanarak dönüş =.<br />-11 hiçbir kapanış hiç =. Bu, yalnızca bir prolog içerebilir, ancak başka bir yerde, kapanış olduğu bir bitişik olmayan işlev parça açıklamak için kullanışlıdır.|
|1.|15|*H* işlevi "tam sayı parametresi homes olup olmadığını" belirten bir 1 bit bayrağı işlevi başlangıcında ileterek (r0-r3) kaydeder ve dönmeden önce yığını, 16 bayt kaldırır. (0 = 1 kaydeder ev değil havaalanlarından kayıtları =.)|
|1.|16-18|*Reg* son dizinini belirten bir 3-bit alanı geçici olmayan kaydı kaydedilir. Varsa *R* bit, 0 ve ardından yalnızca tamsayı kayıtlar kaydediliyor ve aralığında r4-kaydırmayı, burada N, 4'e eşit olarak kabul edilir + *Reg*. Varsa *R* bit, 1, ardından yalnızca kayan nokta kayıtlarını kaydediliyor ve d8-dN, burada N, 8'e eşit aralığında olduğu varsayılır + *Reg*. Özel birleşimi *R* = 1 ve *Reg* = 7 yazmaç yok kaydedildiğini gösterir.|
|1.|19|*R* kaydedilen geçici olmayan kayıtları tamsayı (0) kayıtları olup veya kayan nokta kayıtlarını (1) belirten bir 1 bit bayrağı. Varsa *R* 1 olarak ayarlayın ve *Reg* alanı, 7'ye ayarlanmışsa, geçici olmayan yazmaç yok gönderildi.|
|1.|20|*M* işlevi kaydeder/LR, tarafından belirtilen diğer kayıtlara birlikte geri yükleme işlemleri olup olmadığını gösteren bir 1 bit bayrağı *Reg* alan. (0 = değil kaydedilemiyor/geri, 1 = mu kaydedilemiyor/geri.)|
|1.|21|*C* işlevi (1) veya hızlı yığın (0) için bir çerçeve zinciri ayarlamak için ek yönergeler içerip içermediğini gösteren bir 1 bit bayrağı. Bu biti ayarlanmışsa r11 örtük olarak kaydedilen tamsayı geçici olmayan kayıtları listesine eklenir. (Eğer aşağıda kısıtlamalarını *C* bayrağı kullanılır.)|
|1.|22-31|*Ayarla yığın* yığınının bölü 4, bu işlev için ayrılan bayt sayısını gösteren bir 10-bit alanıdır. Ancak, yalnızca değerleri 0x000 0x3F3 arasında doğrudan kodlanabilir. 4044 bayttan daha fazla yığın ayırma işlevleri tam bir sanal işlem bulunur kaydı kullanmanız gerekir. Varsa *yığını ayarlamak* alandır 0x3F4 veya daha büyük, daha sonra düşük 4 BITS özel bir anlamı yoktur:<br /><br /> -Bitler 0-1 yığın düzeltmesi (1-4), eksi 1 sözcük sayısını gösterir.<br />-Bu düzeltme, anında iletme işlemde prolog birleştirildiğinde bit 2 1 olarak ayarlanır.<br />-Kapanış pop, işlemde bu ayarlama birleştirildiğinde bit 3 1 olarak ayarlanır.|

Yukarıdaki Kodlamalar, olası fazlalıkları nedeniyle bu kısıtlamalar uygulanır:

- Varsa *C* bayrağı 1 olarak ayarlayın:

   - *L* bayrağı da ayarlanmalıdır 1, çerçeve zincirleme r11 hem LR gerekli olduğu.

   - R11 gerekir dahil edilmeyecek tarafından açıklanan yazmaç kümesini *Reg*. Diğer bir deyişle, r4 r11 itilir, *Reg* r4 r10, çünkü yalnızca açıklamalıdır *C* bayrağı r11 anlamına gelir.

- Varsa *Ret* alanı 0 olarak ayarlanmış *L* bayrağı 1 olarak ayarlanması gerekir.

Bu kısıtlamalar ihlal desteklenmeyen dizisi neden olur.

İki sahte bayrakları türetilmiştir tartışma aşağıdaki amaçlarla *yığını ayarlamak*:

- *PF* veya gösterir "prolog Katlama" *yığını ayarlamak* 0x3F4 ya da daha büyük ve bit 2 ayarlanır.

- *EF* veya gösterir "kapanış Katlama" *yığını ayarlamak* 0x3F4 ya da daha büyük ve bit 3 ayarlanır.

Öğesinin kurallı işlevler için en fazla 5 yönergeleri (bildirim 3a ve 3b birbirinden bağımsızdır) olabilir:

|Yönerge|Opcode mevcut varsayılır varsa:|Boyut|Opcode|Geriye doğru izleme kodları|
|-----------------|-----------------------------------|----------|------------|------------------|
|1.|*H*1 ==|16|`push {r0-r3}`|04|
|2|*C*1 == veya *L*1 == veya *R*0 veya PF == 1 ==|16/32|`push {registers}`|80-BF/D0-SD/EC-ED|
|3a|*C*1 == ve (*L*== 0 ve *R*1 ve PF == 0 ==)|16|`mov r11,sp`|C0-CF/FB|
|3B|*C*1 == ve (*L*1 == veya *R*0 veya PF == 1 ==)|32|`add r11,sp,#xx`|FC|
|4|*R*1 == ve *Reg* ! = 7|32|`vpush {d8-dE}`|E0 E7|
|5|*Yığın ayarlamak* ! = 0 ve PF == 0|16/32|`sub sp,sp,#xx`|00-7F/E8-EB|

Yönerge 1 varsa her zaman, *H* biti 1 olarak ayarlanır.

Çerçeve zincirleme ayarlamak üzere, yönerge 3a veya 3b varsa, *C* bitinin ayarlanmasıdır. Bir 16-bit, `mov` yoksa r11 ve LR dışında kayıtları itilir; Aksi takdirde, 32 bit bir değer `add`.

Katlanmış olmayan bir ayarı belirtilirse, 5 açık yığın ayarlama yönergedir.

2 ve 4 yönergeler bir anında iletme gerekli olmasına göre ayarlanır. Bu tablo hangi kayıtları göre kaydedilir özetler *C*, *L*, *R*, ve *PF* alanları. Tüm durumlarda *N* eşittir *Reg* + 4 *E* eşittir *Reg* + 8, ve *S* eşittir (~*Yığını ayarlamak*) ve 3.

|C|L|R|PF|Tamsayı kayıtları gönderildi|VFP kaydeder gönderildi|
|-------|-------|-------|--------|------------------------------|--------------------------|
|0|0|0|0|r R4*N*|yok|
|0|0|0|1.|r*S*- r*N*|yok|
|0|0|1.|0|yok|D8-d*E*|
|0|0|1.|1.|r*S*-r3|D8-d*E*|
|0|1.|0|0|r R4*N*, LR|yok|
|0|1.|0|1.|r*S*- r*N*, LR|yok|
|0|1.|1.|0|LR|D8-d*E*|
|0|1.|1.|1.|r*S*-r3, LR|D8-d*E*|
|1.|0|0|0|r R4*N*, r11|yok|
|1.|0|0|1.|r*S*- r*N*, r11|yok|
|1.|0|1.|0|R11|D8-d*E*|
|1.|0|1.|1.|r*S*-r3, r11|D8-d*E*|
|1.|1.|0|0|r R4*N*, r11, LR|yok|
|1.|1.|0|1.|r*S*- r*N*, r11, LR|yok|
|1.|1.|1.|0|R11, LR|D8-d*E*|
|1.|1.|1.|1.|r*S*-r3, r11, LR|D8-d*E*|

Sonuçları kurallı işlevler izleyin benzer bir form ancak tersine ve bazı ek seçeneklere sahip. Kapanış en fazla 5 yönergeleri uzun olabilir ve kendi form prolog form tarafından kesin olarak belirlenmiştir.

|Yönerge|Opcode mevcut varsayılır varsa:|Boyut|Opcode|
|-----------------|-----------------------------------|----------|------------|
|6|*Yığın ayarlamak*! = 0 ve *EF*== 0|16/32|`add   sp,sp,#xx`|
|7|*R*1 == ve *Reg*! = 7|32|`vpop  {d8-dE}`|
|8|*C*1 == veya (*L*1 == ve *H*== 0) veya *R*== 0 veya *EF*1 ==|16/32|`pop   {registers}`|
|9a|*H*1 == ve *L*== 0|16|`add   sp,sp,#0x10`|
|9b|*H*1 == ve *L*1 ==|32|`ldr   pc,[sp],#0x14`|
|10A|*Ret*1 ==|16|`bx    reg`|
|10b|*Ret*2 ==|32|`b     address`|

Katlanmış olmayan bir ayarı belirtilirse 6 açık yığın ayarlama yönergedir. Çünkü *PF* bağımsızdır *EF*, yönerge 5 6 yönerge var veya tam tersi olması mümkündür.

Yönergeleri 7 ve 8 hangi kayıtları yığından geri belirlemek için giriş aynı mantığı kullanır, ancak bu iki değiştirir: ilk *EF* yerine kullanılan *PF*; ikinci, varsa *Ret*  = 0, LR, kayıt listesinde PC ile değiştirilir ve kapanış hemen sonlandırır.

Varsa *H* yönerge 9a ya da 9b sonra ayarlanır. Yönerge 9a kullanılan zaman *L* LR yığında olmadığını göstermek için 0 ' dır. Bu durumda, yığın el ile ayarlanır ve *Ret* 1 ya da açık bir dönüş belirtmek için 2 olmalıdır. Yönerge 9b kullanılan zaman *L* kapanış erken sona belirtmek ve dönün ve yığın aynı anda ayarlamak için 1 ' dir.

Kapanış değil zaten sona erdi, 10a yönerge sonra ya da veya 10b 16-bit veya 32-bit bir dal belirtmek için mevcut değerine göre *Ret*.

### <a name="xdata-records"></a>Sanal işlem bulunur kayıtları

Paketlenmiş geriye doğru izleme biçimi işlevi geriye doğru izleme açıklamak için yetersiz olduğunda, bir değişken uzunluklu sanal işlem bulunur kaydı oluşturulmalıdır. Bu kaydın adresini .pdata kaydın ikinci Word'de depolanır. Sanal işlem bulunur dört bölüm olan bir değişken uzunluklu dizi paketlenmiş sözcükleri biçimdedir:

1. Sanal işlem bulunur yapısı toplam boyutunu açıklayan ve anahtar işlevi veri sağlayan bir 1 veya 2 sözcük üstbilgisi. İkinci sözcük yalnızca var ise *kapanış sayısı* ve *kod sözcükleri* alanları her ikisi de 0 olarak ayarlanır. Bu tablodaki alanlar belirtilir:

   |Word|Bits|Amaç|
    |----------|----------|-------------|
    |0|0-17|*İşlev uzunluğu* işlevi 2 ile bölünen bayt cinsinden toplam uzunluğunu belirten bir 18 bit alanıdır. Bir işlev 512 KB'den büyükse, .pdata ve .xdata birden çok kayıt işlevi tanımlamak için kullanılmalıdır. Ayrıntılar için bu belgede büyük işlevler bölümüne bakın.|
    |0|18-19|*Vers* 2-bit alanı, kalan xdata sürümü açıklanmaktadır. Yalnızca 0 sürümü şu anda tanımlanır; 1-3, değerler ayrılmıştır.|
    |0|20|*X* varlığı (1) veya özel durum verileri yokluğu (0) gösteren bir 1 bit alanıdır.|
    |0|21|*E* olan ek kapsam gerektiren yerine tek bir kapanış açıklayan bilgileri (1) üstbilgisine iyileştirmesiyle doludur gösteren bir 1 bit alanı sözcükleri sonraki (0).|
    |0|22|*F* bu kaydı işlevi parça (1) veya tam bir işlev (0) açıklayan gösteren bir 1 bit alanıdır. Bir parça yok prolog olduğunu ve tüm prolog işleme yoksayılıp yoksayılmaması gerektiğini gösterir.|
    |0|23-27|*Kapanış sayısı* durumuna bağlı olarak iki anlama sahip 5-bit alanı *E* bit:<br /><br /> -Eğer *E* 0'dır, bu alan 3 bölümünde açıklanan özel durum kapsamları toplam sayısı bir sayıdır. Birden fazla 31 kapsamları işlevi ve ardından bu alan varsa ve *kod sözcükleri* alanı hem de ayarlanması gerekir 0 için bir uzantı Word'ün gerekli olduğunu belirtmek için.<br />-Eğer *E* 1, bu alan yalnızca kapanış açıklayan ilk geriye doğru izleme kodu dizinini belirtir.|
    |0|28-31|*Kod sözcük* tüm bölüm 4'teki geriye doğru izleme kodları içermesi için gerekli 32 bit sözcük sayısını belirten bir 4-bit alanıdır. En fazla 63 geriye doğru izleme kodu bayt için bu alan 15'ten fazla sözcük gerekiyorsa ve *kapanış sayısı* alanı hem de ayarlanması gerekir 0 için bir uzantı Word'ün gerekli olduğunu belirtmek için.|
    |1.|0-15|*Kapanış sayısı Genişletilmiş* sonuçları olağan dışı derecede büyük sayıda kodlama için daha fazla alan sağlayan bir 16 bit alanıdır. Bu alan içeren uzantı sözcüğünü yalnızca var ise *kapanış sayısı* ve *kod sözcükleri* ilk üstbilgi sözcük alanlarında hem de 0 olarak ayarlanır.|
    |1.|16-23|*Kod sözcük Genişletilmiş* olağan dışı derecede büyük bir geriye doğru izleme kodu sözcük sayısını kodlama için daha fazla alan sağlayan bir 8 bit alanıdır. Bu alan içeren uzantı sözcüğünü yalnızca var ise *kapanış sayısı* ve *kod sözcükleri* ilk üstbilgi sözcük alanlarında hem de 0 olarak ayarlanır.|
    |1.|24-31|Ayrılmış|

2. Özel durum verileri sonra (varsa *E* bit üst bilgisindeki 0 olarak ayarlanmıştır), başlangıç uzaklığını artan sıraya göre depolanır ve bir Word paketlenmiş kapanış kapsamları hakkında bilgi listesidir. Her kapsam, bu alanları içerir:

   |Bits|Amaç|
    |----------|-------------|
    |0-17|*Kapanış başlangıç uzaklığı* kapanış, 2, işlev başlangıcını göre bölü bayt uzaklığı açıklayan bir 18 bit alanıdır.|
    |18-19|*Res* gelecekteki genişleme için ayrılmış bir 2 bit alanıdır. Değeri 0 olmalıdır.|
    |20-23|*Koşul* altında kapanış yürütülen koşulu sağlayan bir 4-bit alanıdır. Koşulsuz sonuçları için "her zaman" gösteren 0xE ayarlamanız gerekir. (Bir kapanış tamamen koşullu ya da tamamen koşulsuz olmalıdır ve ilk yönerge sonra BT opcode ile kapanış Thumb-2 modunda başlar.)|
    |24-31|*Kapanış başlangıç dizini* bu kapanış açıklayan ilk geriye doğru izleme kodu bayt dizinini belirten bir 8 bit alanıdır.|

3. Bu makalede geriye doğru izleme kodları bölümünde ayrıntılı olarak açıklanan geriye doğru izleme kodları içeren bir bayt dizisi kapanış kapsam listesi çağrıldıktan sonra. Bu dizi için en yakın tam sözcük sınırı sonunda sıfır eklenir. Küçük endian modunda doğrudan getirilebilir, böylece bayt little endian sırayla depolanır.

4. Varsa *X* üstbilgisinde alan 1, geriye doğru izleme kodu bayt özel durum işleyicisi bilgilerini tarafından izlenir. Bu birini oluşur *özel durum işleyicisi RVA* adresi özel durum işleyicisi tarafından gerekli verileri (değişken uzunluklu) miktarına göre hemen ardından özel durum işleyicisinin içerir.

Sanal işlem bulunur kaydı ilk 8 bayt getirmek ve aşağıdaki özel durum değişken boyutlu veri uzunluğu dahil değil kayıt tam boyutunu hesaplamak mümkündür şekilde tasarlanmıştır. Bu kod parçacığı, kayıt boyutunu hesaplar:

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

Athough prolog ve her kapanış geriye doğru izleme kodları bir dizine sahip, tablo, bunlar arasında paylaşılır. Bunların tümü aynı geriye doğru izleme kodları paylaşabilirsiniz seyrek değil. Derleyici yazıcıları belirtilebilecek en büyük dizinden 255'tir ve bu belirli bir işlev için olası geriye doğru izleme kodları toplam sayısını sınırlar çünkü bu durumda, iyileştirme öneririz.

### <a name="unwind-codes"></a>Geriye doğru izleme kodları

Geriye doğru izleme kodları işlemleri geri alınmalıdır sırada prolog etkilerini geri nasıl tam olarak açıklayan yönerge sıralarını havuzu dizisidir. Geriye doğru izleme kodları bir bayt dizisi kodlanmış bir mini yönerge kümesidir. Yürütme tamamlandıktan sonra çağıran işlevin dönüş adresi LR kaydıdır ve tüm geçici olmayan kasalar değerlerine işlev çağrıldı zaman geri yüklenir.

Dizisi özel durumları her zaman sadece bir işlev gövdesinin içinde gerçekleşmesi için garantili ve hiçbir zaman bir prolog veya kapanış içinde yalnızca bir bırakma gerekli olacaktır. Ancak, Windows geriye doğru izleme modeli kısmen yürütülen prolog veya kapanış içinde dan geriye doğru izleme yeteneği gerektirir. Bu gereksinimi karşılamak için geriye doğru izleme kodları dikkatle prolog ve epilog ilgili her opcode için belirsiz bire bir eşleme sağlamak için tasarlanmıştır. Bu, birkaç olası etkilere sahiptir:

- Geriye doğru izleme kodları sayısı sayılarak prolog ve epilog uzunluğunu hesaplamak mümkündür. 16-bit ve 32-bit işlem için ayrı eşlemeleri olmadığından bu bile değişken uzunluklu Thumb-2 yönergeleri ile mümkündür.

- Yönerge bir kapanış kapsamı başlangıcını geçmiş sayısını sayma tarafından geriye doğru izleme kodları eşdeğeri olan sayıyı atlayabilir ve kısmen yürütülen tamamlamak için bir dizi rest yürütmek mümkündür kapanış gerçekleştirmekte olduğu geriye doğru izleme.

- Yönerge prolog bitmeden önce sayısını sayma tarafından geriye doğru izleme kodları eşdeğeri olan sayıyı atlayabilir ve sırası, yalnızca yürütme tamamlanan prolog bölümlerini geri kalanını yürütmek mümkündür.

Aşağıdaki tabloda, geriye doğru izleme kodları eşleme işlem kodlarını gösterir. Daha az ortak olanları iki, üç veya dört bile bayt gerektirirken en yaygın yalnızca tek baytlık kodlarıdır. Her kod en önemli bayt için en az önemli bayt depolanır. Geriye doğru izleme kod yapısını kodlamadan çünkü bu geriye doğru izleme kodları bire bir eşleme işlem için giriş sağlamak için tasarlanmıştır ve öğesinin ve sonuçları, kısmen geriye doğru izleme için izin vermek için kapanış yürütülen ARM EABI içinde açıklanan farklıdır.

|1 bayt|2 bayt|Bayt 3|4 bayt|Opsize|Açıklama|
|------------|------------|------------|------------|------------|-----------------|
|00-7F||||16|`add   sp,sp,#X`<br /><br /> burada X, (kod & 0x7F) \* 4|
|80 BF|00-FF|||32|`pop   {r0-r12, lr}`<br /><br /> Kod & 0x2000 ve r0-r12 karşılık gelen bit kod & 0x1FFF ayarlanırsa, POP, LR burada POP|
|C0 CF||||16|`mov   sp,rX`<br /><br /> Kod & 0x0F X olduğu|
|D0 D7 HÜCRESİNİ||||16|`pop   {r4-rX,lr}`<br /><br /> burada X, (kod & 0x03) + 4 ve LR, kaldırılmaz kod & 0x04|
|DF D8||||32|`pop   {r4-rX,lr}`<br /><br /> burada X, (kod & 0x03) + 8 ve LR, kaldırılmaz kod & 0x04|
|E0 E7||||32|`vpop  {d8-dX}`<br /><br /> X (kod & 0x07) burada + 8|
|E8 EB|00-FF|||32|`addw  sp,sp,#X`<br /><br /> burada X, (kod & 0x03FF) \* 4|
|EC-ED|00-FF|||16|`pop   {r0-r7,lr}`<br /><br /> Kod & 0x0100 ve r0-r7 karşılık gelen bit kod & 0x00FF ayarlanırsa, POP, LR burada POP|
|EE|00-0F|||16|Microsoft'a özgü|
|EE|10-FF|||16|Kullanılabilir|
|EF|00-0F|||32|`ldr   lr,[sp],#X`<br /><br /> burada X, (kod & 0x000F) \* 4|
|EF|10-FF|||32|Kullanılabilir|
|F0 F4||||-|Kullanılabilir|
|F5|00-FF|||32|`vpop  {dS-dE}`<br /><br /> (kod & 0x00F0) S olduğu >> 4 E ise kod & 0x000F|
|F6|00-FF|||32|`vpop  {dS-dE}`<br /><br /> S olduğu ((Code & 0x00F0) >> 4) + 16 ve E (kod & 0x000F) + 16|
|F7|00-FF|00-FF||16|`add   sp,sp,#X`<br /><br /> burada X, (kod & 0x00FFFF) \* 4|
|F8|00-FF|00-FF|00-FF|16|`add   sp,sp,#X`<br /><br /> burada X, (kod & 0x00FFFFFF) \* 4|
|F9|00-FF|00-FF||32|`add   sp,sp,#X`<br /><br /> burada X, (kod & 0x00FFFF) \* 4|
|FA|00-FF|00-FF|00-FF|32|`add   sp,sp,#X`<br /><br /> burada X, (kod & 0x00FFFFFF) \* 4|
|FB||||16|NOP (16-bit)|
|FC||||32|NOP (32-bit)|
|FD||||16|Son + 16 bit nop kapanış içinde|
|FE||||32|Son + 32-bit nop kapanış içinde|
|TT||||-|end|

Bu bir geriye doğru izleme kodu ile onaltılı değerler için her bir bayt aralığı gösterir *kod*, opcode boyutu birlikte *Opsize* ve karşılık gelen özgün yönerge yorumu. Boş hücreleri kısa geriye doğru izleme kodları belirtin. Birden fazla bayt kapsayan büyük değerlere sahip yönergelerde en önemli bitleri ilk depolanır. *Opsize* alan her bir Thumb-2 işlemle ilişkili örtük opcode boyutunu gösterir. Görünen yinelenen girişler farklı kodlamaları tabloda, farklı opcode boyutları arasında ayrım yapmak için kullanılır.

Geriye doğru izleme kodları, kodun ilk baytı karşılık gelen opcode yönerge akış boyutu ve kodun bayt cinsinden toplam boyut söyler şekilde tasarlanmıştır. Epilog ve prolog boyutunu hesaplamak için geriye doğru izleme kodları, dizinin başından sonuna kadar size yol ve karşılık gelen opcode ne olduğunu belirlemek için arama tablosu veya benzer bir yöntem kullanın.

Geriye doğru izleme kodları 0xFD ve normal son kod 0xFF, ancak bir ek nop opcode kapanış durumda, 16 bit veya 32-bit için hesap 0xFE eşdeğerdir. Öğesinin için kodları 0xFD ve 0xFE 0xFF tam olarak eşdeğerdir. Bu hesaplar için ortak kapanış sonlarını `bx lr` veya `b <tailcall-target>`, eşdeğer prolog yönergesi yok. Bu artış dizileri geriye doğru izleme olasılığını prolog ve sonuçları arasında paylaşılabilir.

Çoğu durumda, geriye doğru izleme kodları aynı dizi prolog ve tüm sonuçları için kullanmak mümkündür. Ancak, kısmen yürütülen öğesinin ve sonuçları geriye doğru izleme işlemek için sıralama veya davranış farklılık birden çok geriye doğru izleme kodu dizilerinizi olması gerekebilir. Her kapanış kendi yürütmeye başlamak nereye gösterilecek bırakma dizi dizine sahip olmasının nedeni budur.

### <a name="unwinding-partial-prologues-and-epilogues"></a>Geriye doğru izleme kısmi öğesinin ve sonuçları

Prolog ve tüm sonuçları uzağa işlevinin gövdesi içinde özel durum oluştuğunda en yaygın geriye doğru bir durumdur. Bu durumda, unwinder dizin 0 geriye doğru izleme dizi başında kodları yürütür ve son opcode algılandığında kadar devam eder.

Bir başlangıç sırasında bir özel durum oluşur veya kapanış Yürütülüyor, yığın çerçevesini yalnızca kısmen oluşturulur ve tam olarak ne doğru geri almak için yapılmıştır unwinder belirlemeniz gerekir.

Örneğin, bu prolog ve epilog sırası göz önünde bulundurun:

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

Her opcode yanında, bu işlemi tanımlamak için uygun geriye doğru izleme kodudur. Son yönergede sayılmaz, kapanış geriye doğru izleme kodları bir Ayna görüntüsünü prolog için geriye doğru izleme kodları dizisidir. Bu durumda yaygındır ve prolog için geriye doğru izleme kodları her zaman prolog'ın yürütme siparişi ters sırada depolanır varsayılır nedenidir. Bu bize geriye doğru izleme kodları ortak bir dizi sağlar:

```asm
0xc7, 0xdd, 0x04, 0xfd
```

Son sırasının kapanış prolog uzun bir 16 bit yönergesi olduğu anlamına gelir için özel bir kod 0xFD kodudur. Geriye doğru izleme kodları büyük paylaşımı bu mümkün kılar.

Prolog ve epilog arasındaki işlev gövdesi yürütülürken bir özel durum oluşursa örnek kapanış ile geriye doğru izleme başlar, uzaklığındaki 0 Epilog kodu içinde veririz. Bu örnekte uzaklığı 0x140 karşılık gelir. Temizlik yapılmadığı için unwinder tam geriye doğru izleme dizisini yürütür. Özel durum Epilog kodu bir yönerge başına sonra oluşursa, bunun yerine, unwinder başarıyla ilk geriye doğru izleme kodu atlayarak geriye doğru izleyebilirsiniz. Verilen işlem kodlarını arasında bire bir eşleme ve, yönergesinden geriye doğru izleme, geriye doğru izleme kodları *n* kapanış içinde ilk unwinder atlamalısınız *n* geriye doğru izleme kodları.

Benzer bir mantık için prolog tersine çalışır. Başlangıç Uzaklığı 0'dan geriye doğru izleme, yürütülecek bir şey vardır. Prolog geriye doğru izleme kodları ters sırada depolandığından tek bir yönerge geriye doğru izleme, geriye doğru izleme dizisi bir geriye doğru izleme kodu sonundan başlamanız gerekir. Genel durumda yönergesinden geriye doğru izleme, *n* prolog geriye doğru izleme sırasında yürütülen başlamalıdır *n* geriye doğru izleme kodları sonundan itibaren kodlarının listesi.

Prolog ve epilog geriye doğru izleme kodları tam olarak her zaman eşleşmiyor. Bu durumda, geriye doğru izleme kodu dizisi kodlarının birkaç dizileri içeren gerekebilir. Kodları işlemesi için uzaklık belirlemek için bu mantıksal kullanın:

1. Gelen işlevinin gövdesi içinde geriye doğru izleme, geriye doğru izleme kodları dizin 0 konumunda çalıştırmaya başlar ve son opcode ulaşılana kadar devam edin.

2. Gelen bir kapanış içinde geriye doğru izleme, kapanış kapsamı tarafından sağlanan kapanış özgü başlangıç dizini kullanın. Kaç bilgisayar bayttır kapanış başlangıcından hesaplayın. Tüm zaten yürütüldü yönergeleri muhasebesi kadar İleri geriye doğru izleme kodları atlayın. Bu noktada başlangıç geriye doğru izleme dizisi yürütün.

3. Gelen giriş içinde geriye doğru izleme, geriye doğru izleme kodları 0 dizinden başlatın. Sıra prolog koddan uzunluğunu hesaplamak ve ardından kaç bayt PC prolog sonundan hesaplamak. Tüm yürütme geri yönergeleri muhasebesi kadar İleri geriye doğru izleme kodları atlayın. Bu noktada başlangıç geriye doğru izleme dizisi yürütün.

Geriye doğru izleme kodları için prolog ilk dizideki her zaman olmalıdır. Bunlar aynı zamanda gelen gövdesi içinde geriye doğru izleme genel kullanım durumu geriye doğru izleme için kullanılan kodlarıdır. Herhangi bir kapanış özgü kodu dizilerinizi prolog kod dizisi hemen sonra uygulamanız gerekir.

### <a name="function-fragments"></a>İşlev parçaları

Kod iyileştirme için bir işlev bitişik olmayan parçalara bölmek yararlı olabilir. Bu yapıldığında, işlevin her parçayı kendi ayrı .pdata gerektirir — ve büyük olasılıkla .xdata — kayıt.

İşlev prolog işlevi başındaki ve bölünemez varsayılarak, dört işlev parça durumlar vardır:

- Yalnızca prolog; Tüm sonuçları diğer parçaları.

- Prolog ve sonuçları; bir veya daha fazla diğer parçaları ek sonuçları.

- Prolog veya sonuçları yok; prolog ve diğer parçaları bir veya daha fazla sonuçları.

- Sonuçları yalnızca; prolog ve diğer parçaları muhtemelen diğer sonuçları.

Bu durumda, yalnızca giriş tanımlanmış olmalıdır. Bu kısa .pdata formunda prolog normalde açıklayan ve belirterek yapılabilir bir *Ret* hiçbir kapanış belirtmek için 3 değeri. Tam sanal işlem bulunur formda dizin 0 konumunda prolog geriye doğru izleme kodları zamanki sağlama ve kapanış sayısı 0 belirterek bu yapılabilir.

Bir normal işlev gibi ikinci bir durumdur. Parça içinde yalnızca bir kapanış yoktur ve parça sonunda ise compact .pdata kaydı kullanılabilir. Aksi halde, tam bir sanal işlem bulunur kayıt kullanılmalıdır. Kapanış başlangıç için belirtilen uzaklık parça, işlevin özgün start başlangıcını göreli olduğunu aklınızda bulundurun.

Bunlar bir prolog içermeyen dışında üçüncü ve dördüncü birinci ve ikinci durumda, türevleri sırasıyla örnekleridir. Bu durumda kapanış başlamadan önce kod ve bu normalde prolog etkilerini geri alma tarafından sapmasına işlev gövdesinin bir parçası olarak kabul edilir varsayılır. Bu nedenle bu gibi durumlarda bırakma açıklar bir sözde prolog ile kodlanmalı gelen gövdesi içinde fakat belirlerken, 0-uzunluğu değerlendirilir yapılıp yapılmayacağını kısmi bir parça başlangıcında geriye doğru izleme. Alternatif olarak, bu sözde giriş muhtemelen eşdeğer işlemler gerçekleştirdiğinden kapanış aynı geriye doğru izleme kodları kullanarak açıklanan.

Üçüncü ve dördüncü durumlarda sözde prolog varlığını ya da ayarlayarak belirtilen *bayrağı* 2 ya da ayarlayarak compact .pdata kaydının alan *F* 1 sanal işlem bulunur üst bilgisindeki bayrağı. Her iki durumda da çekin kısmi prolog geriye doğru izleme göz ardı edilir ve kapanış olmayan tüm geriye doğru izler kabul edilir dolu.

#### <a name="large-functions"></a>Büyük işlevleri

Parçaları, İşlevler sanal işlem bulunur üst bilgisindeki bit alanları tarafından uygulanan 512 KB sınırdan daha büyük açıklamak için kullanılabilir. Çok büyük bir işlev açıklamak için yalnızca bu parçaları 512 KB'tan küçük bölün. Her parça, böylece bir kapanış birden fazla parçaya bölmediğinden düşüncesiyle ayarlanması gerekir.

İşlev yalnızca ilk parçasını bir giriş içerir. diğer tüm parçaları hiçbir prolog sahip olarak işaretlenir. Sonuçları sayısına bağlı olarak, her parça sıfır veya daha fazla sonuçları içerebilir. Her bir parça kapanış kapsamda parça, start işlevin başlangıcını göreli başlangıç uzaklığı belirtir aklınızda bulundurun.

Hiçbir prolog ve epilog herhangi bir parçaya sahipse, kendi .pdata hala gerektirir — ve büyük olasılıkla .xdata — kaydı gelen işlevinin gövdesi içinde bırakma açıklar.

#### <a name="shrink-wrapping"></a>Sabit

Daha karmaşık bir özel durum işlevi parçaların *sabit*, işlevinde kaydı kaydetme gerektirmeyen basit durumlar için en iyi duruma getirmek için daha sonra işleve başından itibaren kayıt ertelemek için bir teknik kaydeder. Bu, bir dış bölgesi yığın alanı ayırır, ancak en az bir yazmaç kümesini kaydeder ve kaydeder ve ek kayıtlar geri yükleyen bir iç bölgesi açıklanabilir.

```asm
ShrinkWrappedFunction
     push   {r4, lr}          ; A: save minimal non-volatiles
     sub    sp, sp, #0x100    ; A: allocate all stack space up front
     ...                     ; A:
     add    r0, sp, #0xE4     ; A: prepare to do the inner save
     stm    r0, {r5-r11}      ; A: save remaining non-volatiles
     ...                     ; B:
     add    r0, sp, #0xE4     ; B: prepare to do the inner restore
     ldm    r0, {r5-r11}      ; B: restore remaining non-volatiles
     ...                     ; C:
     pop    {r4, pc}          ; C:
```

Naylon işlevleri genellikle normal prolog içinde ek kayıt kaydeder alan önceden ayırmak için beklenen ve kayıt kaydeder kullanarak gerçekleştirin `str` veya `stm` yerine `push`. Bu işlevin özgün prolog içinde tüm yığın işaretçisi işleme tutar.

Örnek naylon işlevi A olarak işaretlenmiş, üç bölgelere bozuk durumda B ve C olarak yorumlar. Bir bölge işlevin sonuna kadar ek geçici olmayan kaydeder başlangıç ilk kapsar. Bu parça bir prolog ve hiçbir sonuçları sahip olarak tanımlamak için bir .pdata veya sanal işlem bulunur kaydı yeniden oluşturulması gerekir.

Orta B bölge hiçbir prolog ve epilog hiçbir sahip bir parçasını tanımlayan kendi .pdata veya sanal işlem bulunur kaydı alır. Ancak, bu bölge için geriye doğru izleme kodları nedeniyle bir işlev gövdesinin dikkate almıştır mevcut olmalıdır. Bir bölge prolog ve işlem bir dizisi tarafından üretilmiş olan gibi B, bölge girmeden önce kaydedilmiş ek kayıtlar kayıtlı hem özgün kayıtları temsil eden bir bileşik prolog kodları açıklamanız gerekir.

Kayıt bölgesi B açıklanan bileşik prolog bölge A prolog hem kaydedilmiş ek kayıtlar açıklamanız gerekir çünkü bir "İç prolog" B düşünülmez bölge için kaydeder. Parça B bir prolog sahip olacak şekilde açıklandığı gibi geriye doğru izleme kodları bu prolog boyutunu da kapsıyor ve bileşik prolog bire bir olarak yalnızca ek kayıtlar Kaydet işlem ile eşleyen bir şekilde tanımlamak için bir yolu yoktur.

Bunlar tamamlanana kadar bileşik prolog yığının durumunu doğru şekilde tanımlamaz çünkü ek kayıt kaydeder ve bölgesinin bir parçası dikkate alınmalıdır.

Son C bölge bir kapanış var ancak hiçbir prolog bir parça açıklayan kendi .pdata veya sanal işlem bulunur kayıt alır.

Bir yönerge için bölge B girişinden önce yığını düzenlenmesini azaltılabilir, alternatif bir yaklaşım da çalışabilir:

```asm
ShrinkWrappedFunction
     push   {r4, lr}          ; A: save minimal non-volatile registers
     sub    sp, sp, #0xE0     ; A: allocate minimal stack space up front
     ...                     ; A:
     push   {r4-r9}           ; A: save remaining non-volatiles
     ...                     ; B:
     pop    {r4-r9}           ; B: restore remaining non-volatiles
     ...                     ; C:
     pop    {r4, pc}          ; C: restore non-volatile registers
```

Burada her yönerge sınırında yığın geriye doğru izleme kodları bölge ile tam olarak tutarlı olduğunu anahtardır. Bu örnekte iç anında iletme önce bir geriye doğru izleme meydana gelirse, A bölgesinin bir parçası olarak kabul edilir ve yalnızca bir giriş bölgesi geriye doğru çözülür. Geriye doğru izleme iç anında iletme sonra meydana gelirse, hiçbir prolog var, ancak iç anında iletme hem özgün prolog A. benzer bir mantık bölgeden açıklayan geriye doğru izleme kodları olan B bölgesinin bir parçası için iç pop tutan kabul edilir.

### <a name="encoding-optimizations"></a>Kodlama iyileştirmeleri

Geriye doğru izleme kodları ve Dengeleme compact ve genişletilmiş veri biçimlerini yeteneği zenginliklere nedeniyle daha fazla alanı azaltmak için kodlama iyileştirmek için birçok fırsat vardır. Bu teknikler agresif kullanımıyla, İşlevler ve parçaları geriye doğru izleme kodları kullanarak açıklayan ağ yükünü oldukça minimal düzeyde olabilir.

En önemli iyileştirme prolog/kapanış sınırları geriye doğru izleme amacıyla mantıksal prolog/kapanış sınırları derleyici açısından ile karıştırmamaya dikkat sağlamaktır. Geriye doğru izleme sınırları, TempDB'de ve verimliliği artırmak için sıkı yapılır. Örneğin, ek doğrulama gerçekleştirmek için yığın Kurulumu denendikten sonra bir prolog kodu içerebilir. Ancak tüm yığın işleme tamamlandıktan sonra daha fazla operations kodlamak için gerek yoktur ve ötesinde herhangi bir şey geriye doğru izleme prolog kaldırılabilir.

Bu aynı kural işlevi uzunluğu için geçerlidir. Veri yoksa — Örneğin, bir değişmez değer havuz —, izleyen bir işlevdeki bir kapanış, işlev uzunluğu bir parçası olarak dahil olmamalıdır. Yalnızca işlevin bir parçası olan kod için işlev küçülterek olasılığını kapanış sonuna ve CD olacağını çok büyük. kaydı kullanılabilir.

Bir giriş yığın işaretçisi başka bir kasaya kaydedildikten sonra genellikle herhangi bir başka işlem kaydetmek için gerek yoktur. İşlevi geriye doğru izlemek için kaydedilen kasadan SP kurtarmak için ilk şey yapmış olan ve kadar başka işlem bırakma üzerinde hiçbir etkisi yoktur.

Tek yönergeli sonuçları hiç, kapsam olarak kodlanması gerekmez veya olarak geriye doğru izleme kodları. Bu yönerge yürütülmeden önce bir geriye doğru izleme yer alıyorsa, ardından, işlev gövdesinde arasında için kabul edilebilir ve prolog geriye doğru izleme kodları yalnızca yürütme yeterlidir. Tek bir yönerge yürütüldükten sonra geriye doğru izleme yer alıyorsa, ardından tanımı gereği, başka bir bölgede gerçekleşir.

Aynı nedenle önceki noktaya olarak kapanış ilk yönergesinin kodlamak çok yönerge sonuçları gerekmez: tam prolog geriye doğru izleme bu yönerge yürütülmeden önce geriye doğru izleme gerçekleşir, yeterli olur. Geriye doğru izleme bu yönerge sonra yer alıyorsa, yalnızca sonraki işlemleri göz önünde bulundurulması gerekir.

Bırakma, kod yeniden kullanımı agresif olmalıdır. Her dizide bir rastgele başlangıç noktası geriye doğru izleme kodları kapanış kapsam işaret tarafından belirtilen dizin. Bir önceki sıra başlangıcına işaret edecek şekilde yok; Bu, ortadaki işaret edebilir. Burada en iyi yaklaşım, istenen kod dizisi oluşturmak ve sonra bir tam bayt eşleşme sıralarının zaten kodlanmış havuzundaki tarayın ve yeniden kullanımı için herhangi bir kusursuz bir başlangıç noktası olarak kullanın sağlamaktır.

Tek yönergeli sonuçları göz ardı edilir sonra varsa, kalan hiçbir sonuçları compact .pdata form; kullanmayı düşünün çok büyük olasılıkla bir kapanış olmaması durumunda olur.

## <a name="examples"></a>Örnekler

Bu örneklerde, 0x00400000 görüntü tabanıdır.

### <a name="example-1-leaf-function-no-locals"></a>Örnek 1: Yaprak işlevi, hiçbir yerel öğeler

```asm
Prologue:
  004535F8: B430      push        {r4-r5}
Epilogue:
  00453656: BC30      pop         {r4-r5}
  00453658: 4770      bx          lr
```

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x000535F8 (= 0x004535F8 0x00400000) =

- Word 1

   - *Bayrağı* = 1, kurallı prolog ve epilog biçimlerini belirten

   - *İşlev uzunluğu* 0x31 = (0x62/2 =)

   - *Ret* 16-bit dala iade gösteren, 1 =

   - *H* = 0, parametrelerini belirten değil bağlantılı

   - *R*= 0 ve *Reg* = 1, anında iletme/pop r4 r5 belirten

   - *M* hiçbir LR kaydedilemiyor/geri belirten, 0 =

   - *C* hiçbir çerçeve zincirleme belirten, 0 =

   - *Ayarla yığın* hiçbir yığın ayarlama belirten, 0 =

### <a name="example-2-nested-function-with-local-allocation"></a>Örnek 2: İç içe geçmiş işlev ile yerel ayırma

```asm
Prologue:
  004533AC: B5F0      push        {r4-r7, lr}
  004533AE: B083      sub         sp, sp, #0xC
Epilogue:
  00453412: B003      add         sp, sp, #0xC
  00453414: BDF0      pop         {r4-r7, pc}
```

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x000533AC = (0x004533AC =-0x00400000)

- Word 1

   - *Bayrağı* = 1, kurallı prolog ve epilog biçimlerini belirten

   - *İşlev uzunluğu* 0x35 = (0x6A/2 =)

   - *Ret* dönüş pop {pc} belirten, 0 =

   - *H* = 0, parametrelerini belirten değil bağlantılı

   - *R*= 0 ve *Reg* = 3, anında iletme/pop r4 r7 belirten

   - *M* = 1, LR gösteren kayıtlı/geri yüklendi

   - *C* hiçbir çerçeve zincirleme belirten, 0 =

   - *Yığın ayarlamak* = 3 (0x0C/4 =)

### <a name="example-3-nested-variadic-function"></a>Örnek 3: İç içe geçmiş bağımsız değişken içeren işlevi

```asm
Prologue:
  00453988: B40F      push        {r0-r3}
  0045398A: B570      push        {r4-r6, lr}
Epilogue:
  004539D4: E8BD 4070 pop         {r4-r6}
  004539D8: F85D FB14 ldr         pc, [sp], #0x14
```

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x00053988 (= 0x00453988 0x00400000) =

- Word 1

   - *Bayrağı* = 1, kurallı prolog ve epilog biçimlerini belirten

   - *İşlev uzunluğu* 0x2A = (0x54/2 =)

   - *Ret* = {pc} pop belirten, 0-style return (Bu durumda bir ldr pc [], #0x14 return sp)

   - *H* = 1, parametrelerini belirten bağlantılı

   - *R*= 0 ve *Reg* = 2, anında iletme/pop r4 r6 belirten

   - *M* = 1, LR gösteren kayıtlı/geri yüklendi

   - *C* hiçbir çerçeve zincirleme belirten, 0 =

   - *Ayarla yığın* hiçbir yığın ayarlama belirten, 0 =

### <a name="example-4-function-with-multiple-epilogues"></a>Örnek 4: Birden çok sonuçları işlevi

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

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x000592F4 (= 0x004592F4 0x00400000) =

- Word 1

   - *Bayrağı* = 0, mevcut sanal işlem bulunur kaydı (birden çok sonuçları nedeniyle gereklidir) gösteren

   - *Sanal işlem bulunur adresi* -0x00400000

(değişken, 6 sözcükleri) sanal işlem bulunur:

- Word 0

   - *İşlev uzunluğu* 0x0001A3 (= 0x000346/2) =

   - *Vers* xdata ürününün ilk sürümünü belirten, 0 =

   - *X* hiçbir özel durum verileri belirten, 0 =

   - *E* kapanış kapsam listesi belirten, 0 =

   - *F* prolog dahil tam işlev açıklamasını belirten, 0 =

   - *Kapanış sayısı* 0x04, 4 toplam kapanış kapsamları belirten =

   - *Kod sözcük* 0x01, geriye doğru izleme kodları bir 32-bit sözcük belirten =

- 1-4, 4 konumlarda 4 kapanış kapsamları açıklayan sözcükler. Her kapsam bırakma kodlarının 0x00, uzaklığında prolog paylaşılan, ortak bir dizi sahip ve koşul 0x0E belirtme koşulsuz (her zaman).

- Geriye doğru izleme kodları, Word 5 başlatılıyor: (prolog/kapanış arasında paylaşılan)

   - 0 = 0x06 kod geriye doğru izleme: sp += (6 << 2)

   - Bırakma kodu 1 = 0xDE: pop {r4 r10, lr}

   - Bırakma kodu 2 = 0xFF: son

### <a name="example-5-function-with-dynamic-stack-and-inner-epilogue"></a>Örnek 5: İşleviyle dinamik yığınını ve iç kapanış

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

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x00085A20 (= 0x00485A20 0x00400000) =

- Word 1

   - *Bayrağı* = 0, mevcut sanal işlem bulunur kaydı (birden çok sonuçları nedeniyle gereklidir) gösteren

   - *Sanal işlem bulunur adresi* -0x00400000

(değişken, 3 sözcükleri) sanal işlem bulunur:

- Word 0

   - *İşlev uzunluğu* 0x0001A3 (= 0x000346/2) =

   - *Vers* xdata ürününün ilk sürümünü belirten, 0 =

   - *X* hiçbir özel durum verileri belirten, 0 =

   - *E* kapanış kapsam listesi belirten, 0 =

   - *F* prolog dahil tam işlev açıklamasını belirten, 0 =

   - *Kapanış sayısı* 0x001, 1 toplam kapanış kapsamını belirten =

   - *Kod sözcük* 0x01, geriye doğru izleme kodları bir 32-bit sözcük belirten =

- Word 1: 0x00 ve 0x0E (her zaman), bir koşul ile geriye doğru izleme kodu dizininden başlayarak kapanış kapsam uzaklığında 0xC6, (0x18C/2 =)

- Geriye doğru izleme kodları, Word 2 konumunda başlayarak: (prolog/kapanış arasında paylaşılan)

   - Bırakma kodu 0 = 0xC6: sp r6 =

   - Bırakma kodu 1 = 0xDC: pop {r4 r8, lr}

   - 2 = 0x04 kod geriye doğru izleme: sp += (4 << 2)

   - Kod 3 = 0xFD bırakma: son, kapanış 16-bit yönergesi olarak sayar

### <a name="example-6-function-with-exception-handler"></a>Örnek 6: İşlev özel durum işleyicisi

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

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x00088C24 (= 0x00488C24 0x00400000) =

- Word 1

   - *Bayrağı* = 0, mevcut sanal işlem bulunur kaydı (birden çok sonuçları nedeniyle gereklidir) gösteren

   - *Sanal işlem bulunur adresi* -0x00400000

(değişken, 5 sözcük) sanal işlem bulunur:

- Word 0

   - *İşlev uzunluğu* 0x000027 (= 0x00004E/2) =

   - *Vers* xdata ürününün ilk sürümünü belirten, 0 =

   - *X* = 1, özel durum verileri gösteren

   - *E* tek bir kapanış gösteren, 1 =

   - *F* prolog dahil tam işlev açıklamasını belirten, 0 =

   - *Kapanış sayısı* 0x00, kapanış geriye doğru izleme kodları Başlat 0x00 uzaklığında belirten =

   - *Kod sözcük* 0x02, geriye doğru izleme kodları iki 32-bit sözcük belirten =

- Geriye doğru izleme kodları, Word 1'den başlayarak:

   - Bırakma kodu 0 = 0xC7: sp r7 =

   - Bırakma kodu 1 = 0x05: sp += (5 << 2).

   - Bırakma 2 = 0xED/0x90 kodu: {r4, r7, lr} açılır

   - Bırakma kodu 4 = 0xFF: son

- Word 3 belirtir bir özel durum işleyicisi 0x0019A7ED = (0x0059A7ED - = 0x00400000)

- Sözcükleri 4 ve ötesine satır içine alınmış bir özel durum verileri

### <a name="example-7-funclet"></a>Örnek 7: Funclet'inde

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

.pdata (sabit, 2 kelimeden):

- Word 0

   - *İşlevi Başlat RVA* 0x00088C72 (= 0x00488C72 0x00400000) =

- Word 1

   - *Bayrağı* = 1, kurallı prolog ve epilog biçimlerini belirten

   - *İşlev uzunluğu* 0x0B = (0x16/2 =)

   - *Ret* dönüş pop {pc} belirten, 0 =

   - *H* = 0, parametrelerini belirten değil bağlantılı

   - *R*= 0 ve *Reg* = 7 yazmaç yok belirten kaydedilen ve geri

   - *M* = 1, LR gösteren kayıtlı/geri yüklendi

   - *C* hiçbir çerçeve zincirleme belirten, 0 =

   - *Ayarla yığın* 1 × 4 bayt yığın ayarlama gösteren, 1 =

## <a name="see-also"></a>Ayrıca bkz.

[ARM ABI Kurallarına Genel Bakış](../build/overview-of-arm-abi-conventions.md)  
[Genel Visual C++ ARM Geçiş Sorunları](../build/common-visual-cpp-arm-migration-issues.md)  

