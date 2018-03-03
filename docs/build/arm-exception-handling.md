---
title: "ARM özel durum işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fe0e615f-c033-4ad5-97f4-ff96af45b201
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdbb6ea3563fb82e90b2bc4ca19f76c43c703cf3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="arm-exception-handling"></a>ARM özel durum işleme
Windows ARM üzerinde mekanizması zaman uyumsuz donanım ürettiği özel durumlar ve zaman uyumlu yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme kullanır. Dile özgü özel durum işleyicileri dil yardımcı işlevleri kullanarak Windows yapılandırılmış özel durum işleme üzerinde oluşturulmuştur. Bu belgede, özel durum Windows ARM ve MASM ve Visual C++ derleyicisi tarafından oluşturulan kodu tarafından kullanılan dil Yardımcıları işleme açıklanmaktadır.  
  
## <a name="arm-exception-handling"></a>ARM özel durum işleme  
 Windows ARM üzerinde kullanan *kodlarının bırakma* sırasında yığını geriye doğru izleme denetlemek için [yapılandırılmış özel durum işleme](http://msdn.microsoft.com/library/windows/desktop/ms680657) (SEH). Bırakma kodlarıdır yürütülebilir görüntü sanal işlem bulunur bölümünde depolanan bayt dizisi. Böylece bir işlevin giriş etkilerini arayanın yığın çerçevesi için geriye doğru izleme için hazırlık alınabilecek soyut bir şekilde işlev giriş ve Epilog kodu işlemi açıklanmaktadır.  
  
 ARM EABI (katıştırılmış uygulama ikili arabirimi) kullanan bir özel durum unwinding modeli kodlarının bırakma belirtiyor, ancak SEH işlemci ortasında giriş olduğu zaman uyumsuz durumlarda işlemelidir Windows geriye doğru izleme için yeterli değil veya bir işlev epilog. Windows ARM EABI birleşik unwinding denetim işlev düzeyi geriye doğru izleme ve dile özgü kapsam geriye doğru izleme, ayrıca ayırır. Bu nedenlerle, daha fazla ayrıntı unwinding veri ve yordam için Windows ARM üzerinde belirtir.  
  
### <a name="assumptions"></a>Varsayımlar  
 Yürütülebilir görüntüler Windows ARM için taşınabilir yürütülebilir (PE) biçimini kullanın. Daha fazla bilgi için bkz: [Microsoft PE ve COFF belirtimi](http://go.microsoft.com/fwlink/p/?linkid=84140). Özel durum bilgilerini işleme resminin ve.xdata'yı ve sanal işlem bulunur bölümlerde depolanır.  
  
 Özel durum mekanizması işleme için ABI Windows ARM üzerinde aşağıdaki kod ile ilgili bazı varsayımlarda bulunur:  
  
-   İşlev gövdesi içinde bir özel durum oluştuğunda, bu giriş'ın operations alınmadan ya da epilog ait işlemler ileriye doğru bir şekilde gerçekleştirilir önemli değildir. Her ikisi de aynı sonuçları üretir.  
  
-   Öğesinin ve sonuçları birbirine yansıtma eğilimindedir. Bu, geriye doğru izleme açıklamak için gerekli meta veri boyutunu azaltmak için kullanılabilir.  
  
-   İşlevler görece küçük olma eğilimindedir. Çeşitli iyileştirmeler bu verileri verimli paketleme için kullanır.  
  
-   Bir koşul üzerinde bir epilog girdiyseniz epilog her yönergesinde için eşit oranda geçerlidir.  
  
-   Yığın işaretçisi (SP) kaydedilir, böylece özgün SP herhangi bir zamanda kurtarılabilir kayıt kalması gereken giriş, başka bir kayıttaki işlevi değişmeden.  
  
-   SP başka bir kayıttaki kaydedilir sürece tüm işlenmesini kesinlikle epilog ve başlangıç içinde gerçekleşmelidir.  
  
-   Yığın çerçevesi bırakma için bu işlemler gereklidir:  
  
    -   R13 ayarlayın (SP) 4-bayt artışlarla.  
  
    -   Bir pop veya daha fazla tamsayı kaydeder.  
  
    -   Bir veya daha fazla VFP pop (sanal kayan nokta) kaydeder.  
  
    -   R13 için rasgele yazmaç değerini kopyalayın (SP).  
  
    -   SP Yığından küçük sonrası azaltma işlemi kullanarak yükleyin.  
  
    -   Birkaç iyi tanımlanmış çerçeve türlerinden birini ayrıştırılamıyor.  
  
### <a name="pdata-records"></a>ve.xdata'yı kayıtları  
 Her yığın düzenleme işlevi açıklayan sabit uzunluklu öğeleri sıralı bir dizi PE biçimli görüntüsündeki ve.xdata'yı kayıtlarıdır. Yığın üzerinde değişiklik yapmazsınız zaman diğer işlevleri çağırmayın işlevleri olan yaprak işlevleri ve.xdata'yı kayıtları gerektirmez. (Diğer bir deyişle, bunlar herhangi bir yerel depolama alanı gerektirmez ve kaydetmek veya geçici olmayan Yazmaçları geri yüklemek gerekmez.). Bu işlevler için kayıtları alanından tasarruf etmek için ve.xdata'yı bölümünden atlanabilir. Bu işlevler birinden hedefiyle yalnızca dönüş adresi bağlantı kaydetmek (LR gelen) programı sayaç çağırana taşımaya (PC) kopyalayabilirsiniz.  
  
 ARM her ve.xdata'yı kaydı 8 bayt uzun içindir. Bir kayıt genel biçimi göreli sanal adres (RAV) bir değişken uzunlukta sanal işlem bulunur bloğu için bir işaretçi veya kurallı işlevi açıklayan paketlenmiş Word'ün içeren ikinci bir sözcük ve ardından ilk 32-bit Word işlevi başlangıcı yerleştirir. Bu tabloda gösterildiği gibi unwinding sırası:  
  
|Word uzaklığı|Bits|Amaç|  
|-----------------|----------|-------------|  
|0|0-31|*İşlev Başlat RVA* 32-bit RVA işlevi başlangıcı olduğu. İşlev Flash kodu içeriyorsa, bu adresini düşük bit ayarlamanız gerekir.|  
|1.|0-1|*Bayrak* ikinci ve.xdata'yı word'ün kalan 30 bit yorumlama belirten 2-bit bir alandır. Varsa *bayrağı* 0'dır ve ardından kalan form BITS bir *özel durum bilgileri RVA* (düşük iki BITS ile örtük olarak 0). Varsa *bayrağı* kalan form BITS sıfır, olduğundan bir *bırakma veri paketlenmiş* yapısı.|  
|1.|2-31|*Özel durum bilgilerini RVA* veya *paketlenmiş veri bırakma*.<br /><br /> *Özel durum bilgileri RVA* sanal işlem bulunur bölümünde depolanan değişken uzunlukta özel durum bilgi yapısı adresidir. Bu veriler, 4-bayt hizalı olması gerekir.<br /><br /> *Veri bırakma, paketlenmiş* kurallı biçimi varsayarak bir işlevden bırakma için gereken işlem sıkıştırılmış açıklamasıdır. Bu durumda, sanal işlem bulunur kaydı gereklidir.|  
  
### <a name="packed-unwind-data"></a>Paketlenmiş veri bırakma  
 Veri bırakma, öğesinin ve sonuçları izleyin, aşağıda açıklanan kurallı biçimi paketlenmiş işlevler için kullanılabilir. Bu bir sanal işlem bulunur kaydı gereksinimini ortadan kaldırır ve önemli ölçüde sağlamak için gereken alanı azaltır veri bırakma. Kurallı öğesinin ve sonuçları bir özel durum işleyici gerektirmez ve standart bir sırada Kurulum ve erdirme işlemlerini gerçekleştiren basit bir işlevin ortak gereksinimlerini karşılamak üzere tasarlanmıştır.  
  
 Bu tablo biçimini gösterir ve.xdata'yı paketlenmiş kayıt bırakma verisi:  
  
|Word uzaklığı|Bits|Amaç|  
|-----------------|----------|-------------|  
|0|0-31|*İşlev Başlat RVA* 32-bit RVA işlevi başlangıcı olduğu. İşlev Flash kodu içeriyorsa, bu adresini düşük bit ayarlamanız gerekir.|  
|1.|0-1|*Bayrak* şu anlama gelir 2-bit alandır:<br /><br /> -00 = paketlenmiş kullanılmaz; veri bırakma Kalan BITS sanal işlem bulunur kayıt noktası.<br />-01 = paketlenmiş veri bırakma.<br />-10 = paketlenmiş burada işlevi varsayılır hiçbir giriş sağlamak için veri bırakma. Bu işlev başlangıcı bitişik olmayan işlevi parçaları açıklamak için kullanışlıdır.<br />-11 = ayrılmış.|  
|1.|2-12|*İşlev uzunluğu* tüm işlevi 2 ile bölünmüş bayt cinsinden uzunluğu sağlayan bir 11-bit bir alandır. İşlev 4 K bayttan büyük olursa, bir tam sanal işlem bulunur kaydı yerine kullanılmalıdır.|  
|1.|13-14|*Ret* nasıl işlevi döndürür gösterir 2-bit alandır:<br /><br /> -00 pop {pc} aracılığıyla iade = ( *L* bayrağı biti ayarlanmış olması gerekir 1 Bu durumda).<br />-01 return = 16 bit şube kullanarak.<br />-10 return = 32-bit şube kullanarak.<br />-11 hiçbir epilog hiç =. Bu, yalnızca bir giriş içerebilir, ancak başka bir yerde, epilog olan bir bitişik olmayan işlevi parça açıklamak için kullanışlıdır.|  
|1.|15|*H* işlevi "tamsayı parametresi homes olup olmadığını" gösteren 1-bit bayrak işlevi başlangıcında ileterek (r0-r3) kaydeder ve döndürmeden önce yığınının 16 bayt kaldırır. (0 = kaydeder, 1 ev değil ev yazmaçlar =.)|  
|1.|16-18|*Reg* son dizinini belirten bir 3-bit'lik alan geçici olmayan kaydı kaydedilir. Varsa *R* bitidir 0 sonra yalnızca tamsayı yazmaçları kaydediliyor ve r4-kaydırmayı, N, 4'e eşit aralığı içinde olduğu varsayılır + *Reg*. Varsa *R* bitidir 1 sonra yalnızca kayan nokta yazmaçlar kaydediliyor ve d8-dN, N, 8'e eşit aralığı içinde olduğu varsayılır + *Reg*. Özel birleşimi *R* = 1 ve *Reg* = 7 gösterir hiçbir yazmaçlar kaydedilir.|  
|1.|19|*R* 1 bit bayrağı, kaydedilen geçici olmayan Yazmaçları tamsayı kaydeder (0) olup olmadığı veya kayan nokta yazmaçlar (1) gösterir. Varsa *R* 1 olarak ayarlayın ve *Reg* alan 7'ye ayarlanmışsa, hiçbir geçici olmayan Yazmaçları gönderilen.|  
|1.|20|*L* işlevi kaydeder/LR, tarafından belirtilen diğer kayıtları birlikte geri yüklemeler olup olmadığını gösteren 1-bit bayrağı *Reg* alan. (0 = değil kaydetme/geri yükleme, 1 = mu kaydetme/geri yükle.)|  
|1.|21|*C* 1 bit bayrağı, işlevi (1) veya olmadığını taramasını hızlı yığın (0) için bir çerçeve zinciri ayarlamak için ek yönergeler içerip içermediğini gösterir. Bu biti ayarlanmışsa r11 örtük olarak kaydedilen tamsayı geçici olmayan Yazmaçları listesine eklenir. (IF aşağıda kısıtlamaları bkz *C* bayrağı kullanılır.)|  
|1.|22-31|*Ayarla yığın* yığınının 4 tarafından ayrılmış, bu işlev için ayrılan bayt sayısını gösterir. 10 bit alanıdır. Ancak, yalnızca 0x000 0x3F3 arasındaki değerleri doğrudan kodlanmış. 4044 bayttan fazla yığın ayırma işlevleri tam sanal işlem bulunur kaydı kullanmanız gerekir. Varsa *yığın ayarlamak* alandır 0x3F4 veya daha büyük, düşük 4 BITS özel anlama sahip sonra:<br /><br /> -Bit 0-1 sözcük eksi 1 yığın düzeltmesi (1-4) sayısını gösterir.<br />-Giriş bu ayarlama, gönderme işlemi içine birleştirildiğinde bit 2 1 olarak ayarlanır.<br />-Epilog pop işlemde bu ayarlama birleştirildiğinde bit 3 1 olarak ayarlanır.|  
  
 Yukarıdaki Kodlamalar, olası açarken nedeniyle bu kısıtlamalar geçerlidir:  
  
-   Varsa *C* bayrağı 1 olarak ayarlayın:  
  
    -   *L* bayrağı da ayarlanmalıdır 1, çerçeve zincirleme r11 ve LR gerektirdiğinden.  
  
    -   R11 değil eklenmesi gereken kümesi tarafından açıklanan kaydeder, *Reg*. Diğer bir deyişle, r4 r11 gönderilir, *Reg* r4-r10, çünkü yalnızca açıklamalıdır *C* bayrağı r11 anlamına gelir.  
  
-   Varsa *Ret* alan 0 olarak ayarlanmış *L* bayrağı 1 olarak ayarlanması gerekir.  
  
 Bu kısıtlamaları ihlal desteklenmeyen dizisi neden olur.  
  
 Tartışma amaçları doğrultusunda, iki sözde bayrak türetilmiş *yığın ayarlamak*:  
  
-   *PF* veya gösteren "Başlangıç Katlama" *yığın ayarlamak* 0x3F4 ya da daha büyük ve bit 2 olarak ayarlanmış.  
  
-   *EF* veya gösteren "epilog Katlama" *yığın ayarlamak* 0x3F4 ya da daha büyük ve bit 3 ayarlanır.  
  
 Öğesinin kurallı işlevler için en fazla 5 yönergeleri (bildirim 3a ve 3b birbirini dışlayan) sahip olabilir:  
  
|Yönergesi|Opcode mevcut varsayılır varsa:|Boyut|İşlem kodu|Kodlarının bırakma|  
|-----------------|-----------------------------------|----------|------------|------------------|  
|1.|*H*== 1|16|`push {r0-r3}`|04|  
|2|*C*== 1 veya *L*== 1 veya *R*0 veya PF == == 1|16/32|`push {registers}`|80-BF/D0-DF/EC-ED|  
|3a|*C*1 == ve (*L*== 0 ve *R*1 ve PF == == 0)|16|`mov r11,sp`|C0-CF/FB|  
|3B|*C*1 == ve (*L*== 1 veya *R*0 veya PF == == 1)|32|`add r11,sp,#xx`|FC|  
|4|*R*1 == ve *Reg* ! = 7|32|`vpush {d8-dE}`|E0 E7|  
|5|*Yığın ayarlamak* ! = 0 ve PF == 0|16/32|`sub sp,sp,#xx`|00-7F/E8-EB|  
  
 Yönerge 1 varsa her zaman, *H* biti 1 olarak ayarlayın.  
  
 Çerçeve zincirleme ayarlamak üzere, yönerge 3a veya 3b mevcut değilse *C* bit ayarlanır. 16 bit olan `mov` yoksa yazmaçlar r11 ve LR dışında kalan; Aksi takdirde, 32 bit değer `add`.  
  
 Katlanmış olmayan ayarlama belirtilirse, yönerge 5 açık yığın ayarlanmasıdır.  
  
 2 ve 4 yönergeler push gerekli olmasına göre ayarlanır. Bu tablo hangi yazmaçlar göre kaydedilir özetler *C*, *L*, *R*, ve *PF* alanları. Tüm durumlarda *N* eşittir *Reg* + 4, *E* eşittir *Reg* + 8, ve *S* eşittir (~*Yığın ayarlamak*) ve 3.  
  
|C|L|R|PF|Tamsayı yazmaçları gönderilir|VFP iletilmesini kaydeder|  
|-------|-------|-------|--------|------------------------------|--------------------------|  
|0|0|0|0|R4-r*N*|yok|  
|0|0|0|1.|r*S*- r*N*|yok|  
|0|0|1.|0|yok|D8-d*E*|  
|0|0|1.|1.|r*S*-r3|D8-d*E*|  
|0|1.|0|0|R4-r*N*, LR|yok|  
|0|1.|0|1.|r*S*- r*N*, LR|yok|  
|0|1.|1.|0|LR|D8-d*E*|  
|0|1.|1.|1.|r*S*-r3, LR|D8-d*E*|  
|1.|0|0|0|R4-r*N*, r11|yok|  
|1.|0|0|1.|r*S*- r*N*, r11|yok|  
|1.|0|1.|0|R11|D8-d*E*|  
|1.|0|1.|1.|r*S*-r3, r11|D8-d*E*|  
|1.|1.|0|0|R4-r*N*, r11, LR|yok|  
|1.|1.|0|1.|r*S*- r*N*, r11, LR|yok|  
|1.|1.|1.|0|R11, LR|D8-d*E*|  
|1.|1.|1.|1.|r*S*-r3, r11, LR|D8-d*E*|  
  
 Sonuçları kurallı işlevleri izleyin benzer bir form ancak ters ve bazı ek seçeneklere sahip. Epilog en fazla 5 yönergeleri uzun olabilir ve kendi form kesinlikle giriş form tarafından dikte edilir.  
  
|Yönergesi|Opcode mevcut varsayılır varsa:|Boyut|İşlem kodu|  
|-----------------|-----------------------------------|----------|------------|  
|6|*Yığın ayarlamak*! = 0 ve *EF*== 0|16/32|`add   sp,sp,#xx`|  
|7|*R*1 == ve *Reg*! = 7|32|`vpop  {d8-dE}`|  
|8|*C*== 1 veya (*L*1 == ve *H*== 0) veya *R*== 0 veya *EF*== 1|16/32|`pop   {registers}`|  
|9a|*H*1 == ve *L*== 0|16|`add   sp,sp,#0x10`|  
|9b|*H*1 == ve *L*== 1|32|`ldr   pc,[sp],#0x14`|  
|10A|*Ret*== 1|16|`bx    reg`|  
|10b|*Ret*2 ==|32|`b     address`|  
  
 Katlanmış olmayan ayarlama belirtilmişse yönerge 6 açık yığın ayarlanmasıdır. Çünkü *PF* bağımsızdır *EF*, yönerge 5 6 yönerge mevcut ya da tam tersini olması mümkündür.  
  
 Yönergeler 7 ve 8 hangi yazmaçlar yığından geri belirlemek için giriş aynı mantığı kullanır, ancak bunlarla iki değiştirir: ilk olarak, *EF* yerine kullanılan *PF*; ikinci, varsa *Ret*  = 0, LR kayıt listesinde PC ile değiştirilir ve epilog hemen sona erer.  
  
 Varsa *H* yönerge 9a veya 9b sonra ayarlanır. Yönerge 9a kullanılan zaman *L* LR yığında olmadığını göstermek için 0 ' dır. Bu durumda, yığın el ile ayarlanır ve *Ret* 1 veya açık bir return belirtmek için 2 olmalıdır. Yönerge 9b kullanılan zaman *L* epilog erken bir sonuna belirtmek ve dönmek ve yığını aynı anda ayarlamak için 1 ' dir.  
  
 Epilog değil zaten sona erdi, 10a yönerge sonra ya da ya da 10b 16 bit veya 32 bit bir şube belirtmek için mevcut değeri temel alınarak *Ret*.  
  
### <a name="xdata-records"></a>Sanal işlem bulunur kayıtları  
 Paketlenmiş bırakma biçim bir işlevi olarak geriye doğru izleme açıklamak için yetersiz olduğunda, bir değişken uzunlukta sanal işlem bulunur kaydı oluşturulmalıdır. Bu kaydın adresini ve.xdata'yı kaydı ikinci Word'de depolanır. Sanal işlem bulunur dört bölüme sahip bir değişken uzunlukta dizi paketlenmiş sözcükler biçimdedir:  
  
1.  Sanal işlem bulunur yapısı toplam boyutunu açıklar ve anahtar işlevi veri sağlayan bir 1 veya 2-word üstbilgisi. İkinci word yalnızca var ise *epilog sayısı* ve *kod sözcük* alanları her ikisi de 0 olarak ayarlanmış. Alanları bu tabloda bölünmüştür:  
  
    |Word|Bits|Amaç|  
    |----------|----------|-------------|  
    |0|0-17|*İşlev uzunluğu* işlevi 2 ile bölünmüş bayt cinsinden toplam uzunluğu belirten bir 18-bit bir alandır. Bir işlev 512 KB'den büyükse, birden çok ve.xdata'yı ve sanal işlem bulunur kayıtları işlevi açıklamak için kullanılmalıdır. Ayrıntılar için bu belgede büyük işlevlerin bölümüne bakın.|  
    |0|18-19|*Sürücüleri* kalan xdata sürümünü açıklar 2-bit alandır. Yalnızca 0 sürümü şu anda tanımlı; değerler 1-3'ün ayrılmıştır.|  
    |0|20|*X* varlığının (1) veya özel durum verileri yokluğunun (0) gösteren 1-bit bir alandır.|  
    |0|21|*E* ek kapsam gerektiren yerine tek bir epilog açıklayan bilgileri (1) üstbilgisine paketlenmiştir gösteren 1-bit alan sözcükleri sonraki (0) değil.|  
    |0|22|*F* bu kaydı işlevi parça (1) veya tam işlevi (0) açıklayan gösteren 1-bit bir alandır. Bir parça hiçbir giriş olduğundan ve tüm giriş işleme yoksayılmalıdır anlamına gelir.|  
    |0|23-27|*Epilog sayısı* durumuna bağlı olarak iki anlama gelir 5-bit alandır *E* bit:<br /><br /> -İf *E* 0'dır, bu alan 3 bölümünde açıklanan özel durum kapsamların sayısı toplam sayısıdır. Birden fazla 31 kapsamları işlevi, ardından bu alan varsa ve *kod sözcük* alanı hem de ayarlanmalıdır 0 olarak bir uzantı Word'ün gerekli olduğunu belirtmek için.<br />-İf *E* 1, bu alan yalnızca epilog açıklar ilk bırakma kodu dizinini belirtir.|  
    |0|28-31|*Kod sözcük* bölüm 4'teki bırakma kodlarının tümü içermesi için gerekli 32 bit sözcük sayısını belirten bir 4-bit bir alandır. 15'ten fazla sözcükler en fazla 63 bırakma kodu bayt için bu alan gerekli olduğunda ve *epilog sayısı* alanı hem de ayarlanmalıdır 0 olarak bir uzantı Word'ün gerekli olduğunu belirtmek için.|  
    |1.|0-15|*Epilog sayısı Genişletilmiş* bir çok sayıda işlem sonuçları kodlama için daha fazla alan sağlayan bir 16 bit alanıdır. Bu alan içeren uzantısı sözcüğü yalnızca var ise *epilog sayısı* ve *kod sözcük* ilk üstbilgi word alanlarında her ikisi de 0 olarak ayarlanmış.|  
    |1.|16-23|*Kod sözcük Genişletilmiş* bırakma kod sözcük olağan dışı derecede büyük bir sayısını kodlama için daha fazla alan sağlayan bir 8 bit alanıdır. Bu alan içeren uzantısı sözcüğü yalnızca var ise *epilog sayısı* ve *kod sözcük* ilk üstbilgi word alanlarında her ikisi de 0 olarak ayarlanmış.|  
    |1.|24-31|Ayrılmış|  
  
2.  Özel durum verileri sonra (varsa *E* üstbilgisinde bit 0 olarak ayarlanmış), başlangıç uzaklığı artan sırada depolanan ve bir Word paketlenmiş epilog kapsamları hakkındaki bilgileri listesidir. Bu alanların her kapsam içerir:  
  
    |Bits|Amaç|  
    |----------|-------------|  
    |0-17|*Epilog başlangıç uzaklığı* işlevi başlangıcı göre 2 bölü bayt epilog uzaklığını açıklayan bir 18-bit alanıdır.|  
    |18-19|*Res* gelecekteki genişleme için ayrılmış bir 2-bit alanıdır. Değeri 0 olmalıdır.|  
    |20-23|*Koşul* altında epilog yürütüldüğünde koşulu sağlayan bir 4-bit bir alandır. Koşulsuz sonuçları için "her zaman" gösterir 0xE ayarlamanız gerekir. (Bir epilog tamamen koşullu veya tamamen koşulsuz olmalıdır ve BT opcode sonra ilk talimatı epilog Flash 2 modunda başlar.)|  
    |24-31|*Epilog başlangıç dizini* bu epilog açıklar ilk bırakma kodu bayt dizinini belirten bir 8 bit alanıdır.|  
  
3.  Bu makalede bırakma kodları bölümünde ayrıntılı olarak açıklanmıştır bırakma kodları içeren bir bayt dizisi epilog kapsamları listesi çağrıldıktan sonra. Bu dizi en yakın tam sözcük sınırına sonunda sıfır eklenir. Böylece little endian modunda doğrudan getirilebilir bayt little endian sırayla depolanır.  
  
4.  Varsa *X* üstbilgi alanında 1, geriye doğru izleme kodu bayt özel durum işleyici bilgilerini tarafından izlenir. Bu birini oluşur *özel durum işleyici RVA* hemen ardından özel durum işleyicisi tarafından gerekli verileri (değişken uzunlukta) miktarı da özel durum işleyici adresini içerir.  
  
 Sanal işlem bulunur kayıt ilk 8 bayt fetch ve aşağıdaki özel durum değişken boyutlu veri uzunluğu hariç kaydının tam boyutlu işlem mümkündür şekilde tasarlanmıştır. Bu kod parçacığını kayıt boyutu hesaplar:  
  
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
  
 Athough giriş ve her epilog bırakma kodlarının bir dizine sahipse, tablo arasında paylaşılır. Bunların tümü aynı bırakma kodlarının paylaşabilirsiniz seyrek değil. Derleyici yazıcılarının belirtilebilir en büyük dizin 255'tir ve belirli bir işlev için olası bırakma kodlarının toplam sayısını sınırlar çünkü bu durumda, iyileştirmek öneririz.  
  
### <a name="unwind-codes"></a>Kodlarının bırakma  
 Bir havuzu işlemleri geri olmalıdır sırayla giriş etkilerini tam olarak nasıl kaldırıldığını açıklamaktadır yönerge sıralarının bırakma kodlarının dizisidir. Bir bayt dizisi kodlanmış bir mini yönerge kümesi bırakma kodlarıdır. Yürütme tamamlandığında, arama işlevi için dönüş adresi LR kaydıdır ve tüm geçici olmayan kasalar değerlerine işlevi çağrıldı aynı anda geri yüklenir.  
  
 Özel durumlar her zaman sadece bir işlev gövdesi içinde gerçekleşmesi için garantili ve hiçbir zaman bir giriş veya epilog içinde yalnızca bir bırakma ise sırası gerekli olabilir. Ancak, Windows unwinding modeli gelen kısmen yürütülen başlangıç ya da epilog içinde bırakma yeteneği gerektirir. Bu gereksinimi karşılamak için bırakma kodlarının dikkatle başlangıç ve epilog ilgili her opcode için anlaşılır bire bir eşleme sağlamak için tasarlanmıştır. Bu, birkaç etkilere sahiptir:  
  
-   Başlangıç ve epilog uzunluğu bırakma kodlarının sayısı sayım tarafından işlem mümkündür. 16 bit ve 32-bit işlem kodları için ayrı eşlemleri olduğundan bu bile değişken uzunlukta Flash 2 yönergeleri ile mümkündür.  
  
-   Yönerge epilog kapsam başlangıcı geçmiş sayısını sayım tarafından bırakma kodlarının eşdeğer sayıda atlamak ve kısmen yürütülen tamamlamak için bir dizi rest yürütmek mümkündür epilog yapıyor olduğu bırakma.  
  
-   Giriş sonundan önce yönerge sayısını sayım tarafından bırakma kodlarının eşdeğer sayıda atlamak ve yalnızca giriş yürütme tamamladınız bölümlerini geri dizinin geri kalanı yürütmek mümkündür.  
  
 Aşağıdaki tabloda işlem kodları bırakma kodlarından eşlemeyi gösterir. Daha az yaygın olanları iki, üç ya da hatta dört bayt gerektirirken en yaygın yalnızca tek baytlık kodlarıdır. Her kod en önemli bayttan az önemli bayt depolanır. Bırakma kod yapısını kodlamadan çünkü bu bırakma kodları bire bir eşleme işlem için giriş sağlamak için tasarlanmıştır ve öğesinin ve sonuçları, kısmen geriye doğru izleme için izin vermek için epilog yürütülen ARM EABI içinde açıklanan farklıdır.  
  
|Byte 1|Bayt 2|Bayt 3|Bayt 4|Opsize|Açıklama|  
|------------|------------|------------|------------|------------|-----------------|  
|00 7F||||16|`add   sp,sp,#X`<br /><br /> X, (kod & 0x7F) * 4|  
|80 BF|00-FF|||32|`pop   {r0-r12, lr}`<br /><br /> karşılık gelen bit kod & 0x1FFF ayarlarsanız kodu & 0x2000 ve r0 r12 Sil'i varsa LR burada Sil'i|  
|C0 CF||||16|`mov   sp,rX`<br /><br /> X kod & 0x0F|  
|D0 D7 HÜCRESİNİ||||16|`pop   {r4-rX,lr}`<br /><br /> burada X, (kod & 0x03) + 4 ve LR Sil'i varsa kod & 0x04|  
|D8 DF||||32|`pop   {r4-rX,lr}`<br /><br /> burada X, (kod & 0x03) + 8 ve LR Sil'i varsa kod & 0x04|  
|E0 E7||||32|`vpop  {d8-dX}`<br /><br /> X (kod & 0x07), + 8|  
|E8 EB|00-FF|||32|`addw  sp,sp,#X`<br /><br /> X, (kod & 0x03FF) * 4|  
|EC ED|00-FF|||16|`pop   {r0-r7,lr}`<br /><br /> karşılık gelen bit kod & 0x00FF ayarlarsanız kodu & 0x0100 ve r0 r7 Sil'i varsa LR burada Sil'i|  
|EE|00 0F|||16|Microsoft'a özgü|  
|EE|10-FF|||16|Kullanılabilir|  
|EF|00 0F|||32|`ldr   lr,[sp],#X`<br /><br /> X, (kod & 0x000F) * 4|  
|EF|10-FF|||32|Kullanılabilir|  
|F0 F4||||-|Kullanılabilir|  
|F5|00-FF|||32|`vpop  {dS-dE}`<br /><br /> (kod & 0x00F0) S olduğu >> 4 E ise kod & 0x000F|  
|F6|00-FF|||32|`vpop  {dS-dE}`<br /><br /> S olduğu ((Code & 0x00F0) >> 4) + 16 ve E (kod & 0x000F) + 16|  
|F7|00-FF|00-FF||16|`add   sp,sp,#X`<br /><br /> X, (kod & 0x00FFFF) * 4|  
|F8|00-FF|00-FF|00-FF|16|`add   sp,sp,#X`<br /><br /> X, (kod & 0x00FFFFFF) * 4|  
|F9|00-FF|00-FF||32|`add   sp,sp,#X`<br /><br /> X, (kod & 0x00FFFF) * 4|  
|FA|00-FF|00-FF|00-FF|32|`add   sp,sp,#X`<br /><br /> X, (kod & 0x00FFFFFF) * 4|  
|FB||||16|NOP (16-bit)|  
|FC||||32|NOP (32 bit)|  
|FD||||16|End + 16-bit nop epilog içinde|  
|FE||||32|End + 32-bit nop epilog içinde|  
|FF||||-|end|  
  
 Bu bir bırakma kodda onaltılık değerler için her bir bayt aralığı gösterir *kod*, opcode boyutu birlikte *Opsize* ve karşılık gelen özgün yönerge yorumlama. Boş hücrelerin kısa bırakma kodları gösterir. Birden çok bayt kapsayan büyük değer olan yönergeleri en önemli BITS ilk depolanır. *Opsize* alan her Flash 2 işlemle ilişkili örtük opcode boyutunu gösterir. Tablo farklı kodlamaları ile görünen yinelenen girişler farklı opcode boyutları arasında ayrım yapmak için kullanılır.  
  
 Bırakma kodlarının kodu ilk baytını kodunun bayt cinsinden toplam boyut ve karşılık gelen opcode yönerge akış boyutu söyler şekilde tasarlanmıştır. Giriş veya epilog boyutunu hesaplamak için bırakma kodlarının dizisi başından sonuna yol ve karşılık gelen opcode ne kadar olacağını belirlemek için bir arama tablosu veya benzer bir yöntem kullanın.  
  
 Kodları 0xFD bırakma ve normal bitiş kodu 0xFF, ancak bir ek nop opcode epilog durumda, 16 bit veya 32 bit için hesap 0xFE eşdeğerdir. Öğesinin için kodları 0xFD, 0xFE ve 0xFF tam olarak eşdeğerdir. Bu ortak epilog sonları için hesapları `bx lr` veya `b <tailcall-target>`, eşdeğer başlangıç yönerge değilsiniz. Dizileri bırakma Fırsat Giriş ve sonuçları arasında paylaşılabilir bu artar.  
  
 Çoğu durumda, giriş ve tüm sonuçları için bırakma kodları aynı kümesini kullanmak mümkün olmalıdır. Ancak, kısmen yürütülen öğesinin ve sonuçları geriye doğru izleme işlemek için sıralama veya davranışını farklılık birden çok bırakma kodu sıraları olması gerekebilir. Her epilog yürütülmeye başlamaya yeri göstermek üzere bırakma dizi kendi dizine sahip nedeni budur.  
  
### <a name="unwinding-partial-prologues-and-epilogues"></a>Unwinding kısmi öğesinin ve sonuçları  
 Giriş ve tüm sonuçları çıktığınızda işlevinin gövdesini'nda özel durum oluştuğunda en yaygın unwinding bir durumdur. Bu durumda, unwinder dizin 0 konumunda bırakma dizi başına kodları yürütür ve son opcode algılandığında kadar devam eder.  
  
 Başlangıç sırasında bir özel durum oluşur veya epilog yürütüyor, yığın çerçevesi yalnızca kısmen oluşturulur ve unwinder tam olarak ne doğru geri almak için gerçekleştirildi belirlemeniz gerekir.  
  
 Örneğin, bu giriş ve epilog sırası göz önünde bulundurun:  
  
```  
0000:   push  {r0-r3}         ; 0x04  
0002:   push  {r4-r9, lr}     ; 0xdd  
0006:   mov   r7, sp          ; 0xc7  
...  
0140:   mov   sp, r7          ; 0xc7  
0142:   pop   {r4-r9, lr}     ; 0xdd  
0146:   add   sp, sp, #16     ; 0x04  
0148:   bx    lr  
```  
  
 Her opcode yanında, bu işlem açıklamak için uygun bırakma kodudur. Yansıma için son yönerge saymaz epilog bırakma kodlarının bırakma kodları giriş için dizisidir. Bu durumda yaygındır ve giriş için bırakma kodları giriş 's yürütme sıra ters sırada depolanması için her zaman varsayılır nedenidir. Bu bize bırakma kodlarının ortak bir dizi sunar:  
  
```  
0xc7, 0xdd, 0x04, 0xfd  
```  
  
 Epilog başlangıç daha uzun bir 16 bit yönerge anlamına gelir dizinin sonuna için özel bir kod 0xFD kodudur. Büyük bırakma kodlarının paylaşımı bu mümkün kılar.  
  
 İşlev gövdesi başlangıç epilog arasındaki yürütülürken, bir özel durum oluşursa örnekte epilog ile unwinding başlar, uzaklığındaki 0 epilog kodundaki durumda. Bu örnekte uzaklığı 0x140 karşılık gelir. Temizleme yapılmadığı için unwinder tam bırakma dizisi yürütür. Özel durum Epilog kodu başına sonra tek bir yönerge oluşursa, bunun yerine, unwinder başarıyla ilk bırakma kodu atlayarak bırakma. İşlem kodları arasında bire bir eşleme verilen ve yönerge geriye doğru izleme varsa kodları, bırakma  *n*  epilog içinde ilk unwinder atlamalısınız  *n*  kodlarının bırakma.  
  
 Giriş için ters benzer mantığı çalışır. Başlangıç Uzaklığı 0'dan geriye doğru izleme, yürütülecek hiçbir şey vardır. Başlangıç bırakma kodlarının ters sırada depolandığından tek bir yönerge geriye doğru izleme bırakma sırası bir bırakma kodu sonundan başlamalısınız. Genel durumda yönerge geriye doğru izleme varsa  *n*  giriş, geriye doğru izleme sırasında yürütme başlaması gereken  *n*  kodlarının listesi sonuna kodlarından bırakma.  
  
 Başlangıç ve epilog bırakma kodlarının tam olarak her zaman eşleşmiyor. Bu durumda, geriye doğru izleme kod dizisi kodlarının birkaç sıraları içeriyor gerekebilir. Kodları işlemesi için uzaklık belirlemek için bu mantığı kullanın:  
  
1.  Gelen işlev gövdesi içinde geriye doğru izleme, dizin 0 konumunda bırakma kodlarının yürütülmeye başlamaya ve son opcode ulaşılana kadar devam edin.  
  
2.  Gelen bir epilog içinde geriye doğru izleme epilog kapsamı tarafından sağlanan epilog özgü başlangıç dizini kullanın. Kaç bilgisayar bayttır epilog başından hesaplayın. Tüm zaten yürütülen yönergeleri dikkate kadar İleri bırakma kodlarının atlayın. Bu noktadan itibaren bırakma sırasının yürütün.  
  
3.  Gelen giriş içinde geriye doğru izleme bırakma kodları 0 dizinden başlatın. Dizisi başlangıç koddan uzunluğu hesaplanması ve kaç bilgisayarın bayttır giriş sonundan hesaplamak. Tüm yürütme geri yönergeleri dikkate kadar İleri bırakma kodlarının atlayın. Bu noktadan itibaren bırakma sırasının yürütün.  
  
 Bırakma kodları giriş için her zaman dizisindeki ilk olması gerekir. Bunlar ayrıca gelen gövdesi içinde geriye doğru izleme, genel durumda bırakma için kullanılan kodlarıdır. Tüm epilog özgü kodu dizilerini hemen başlangıç kod dizisi sonra uygulamanız gerekir.  
  
### <a name="function-fragments"></a>İşlev parçaları  
 Kodu iyileştirme için bir işlev bitişik olmayan parçalara bölmek yararlı olabilir. Bu yapıldığında, her işlevi parça kendi ayrı ve.xdata'yı gerektirir — ve büyük olasılıkla sanal işlem bulunur — kaydı.  
  
 İşlev Giriş işlevi başındaki ve bölünemez varsayılarak, dört işlevi parça durumlar vardır:  
  
-   Yalnızca başlangıç; Tüm sonuçları diğer parçada.  
  
-   Giriş ve bir veya daha fazla sonuçları; Ek sonuçları diğer parçada.  
  
-   Hiçbir giriş veya sonuçları; Başlangıç ve diğer parçada bir veya daha fazla sonuçları.  
  
-   Yalnızca sonuçları; Başlangıç ve diğer parçada büyük olasılıkla ek sonuçları.  
  
 İlk durumda, yalnızca giriş tanımlanmış olmalıdır. Bu compact ve.xdata'yı formunda giriş normalde açıklayan ve belirterek yapılabilir bir *Ret* değeri hiçbir epilog belirtmek için 3. Tam sanal işlem bulunur formunda bu dizin 0 konumunda başlangıç bırakma kodlarının her zamanki gibi sağlama ve epilog sayısı 0 belirterek yapılabilir.  
  
 Yalnızca normal bir işlev gibi ikinci bir durumdur. Parçadaki tek epilog yoktur ve parça sonunda ise, bir compact ve.xdata'yı kaydı kullanılabilir. Aksi halde, bir tam sanal işlem bulunur kayıt kullanılmalıdır. Parça, özgün başlatılmamasına işlevinin başlangıç göreli epilog başlatma için belirtilen uzaklıkları olan aklınızda bulundurun.  
  
 Bir başlangıç içermeyen dışında üçüncü ve dördüncü birinci ve ikinci durumda, çeşitlemelerini sırasıyla örnekleridir. Bu durumlarda epilog başlamadan önce kod yoktur ve genellikle giriş etkilerini geri alma tarafından sapmasına işlevinin gövdesini bir parçası olarak kabul edilir varsayılır. Bu gibi durumlarda bu nedenle bırakma açıklar bir sözde başlangıç ile kodlanmalı gelen gövdesi, ancak belirlerken, 0-uzunluk davranılır içinde kısmi yapılıp yapılmayacağını parça başlangıcında bırakma. Alternatif olarak, bu sözde başlangıç büyük olasılıkla eşdeğer işlemler gerçekleştirdiğinden epilog aynı bırakma kodlarını kullanarak açıklanan.  
  
 Üçüncü ve dördüncü durumlarda ya da göre ayarlama sözde başlangıç varlığını belirtilen *bayrağı* 2 ya da ayarlayarak compact ve.xdata'yı kaydının alan *F* 1 sanal işlem bulunur üstbilgisinde bayrağı. Her iki durumda da onay kısmi başlangıç bırakma göz ardı edilir ve epilog olmayan tüm unwinds olarak kabul edilir tam olmalıdır.  
  
#### <a name="large-functions"></a>Büyük işlevleri  
 Parçaları, İşlevler sanal işlem bulunur başlığındaki bit alanları tarafından uygulanan 512 KB sınırdan daha büyük tanımlamak için kullanılabilir. Çok büyük bir işlev tanımlamak için yalnızca bu parçaları 512 KB'den küçük bölün. Böylece bir epilog birden çok parçalara bölmediğinden her parça düşüncesiyle ayarlanması gerekir.  
  
 İlk parça işlevinin yalnızca bir giriş içerir; diğer tüm parçaları, hiçbir giriş sahip olarak işaretlenir. Sonuçları sayısına bağlı olarak, her parça sıfır veya daha fazla sonuçları içerebilir. Her bir parça epilog kapsamda başlatılmamasına işlevinin parça başlangıcı göre kendi başlangıç uzaklığı belirtir aklınızda bulundurun.  
  
 Hiçbir giriş ve hiçbir epilog bir parçaya sahipse, kendi ve.xdata'yı hala gerektirdiği — ve büyük olasılıkla sanal işlem bulunur — kayıt gelen işlev gövdesi içinde bırakma açıklar.  
  
#### <a name="shrink-wrapping"></a>Sabit  
 Daha karmaşık bir özel durum işlevi parçaların: *sabit*, kayıt ertelemek için bir yöntem kaydeder işlevindeki kayıt kaydetme gerektirmeyen basit durumlar için en iyi duruma getirmek için daha sonra işleve başlangıcı. Bu, yığın alan ayırır ancak yazmaçlar en az sayıda kaydeder bir dış bölgesi ve kaydeder ve ek kayıtları geri yükleyen bir iç bölgesi tanımlanabilir.  
  
```  
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
  
 Naylon işlevleri genellikle normal giriş ek kayıt kaydeder için alan önceden ayırmak için beklenen ve kayıt kaydeder kullanarak gerçekleştirin `str` veya `stm` yerine `push`. Bu işlevin özgün başlangıç tüm yığın işaretçisi işleme tutar.  
  
 Örnek naylon işlevi A olarak işaretlenmiş, üç bölgelere ayrılmış olarak B ve C açıklamaları. Bir bölge ek geçici olmayan kaydeder sonuna işleviyle başlangıcı ilk kapsar. Bir başlangıç ve hiçbir sonuçları sahip olarak bu parçasını tanımlamak için bir ve.xdata'yı veya sanal işlem bulunur kaydı oluşturulması gerekir.  
  
 Orta B bölge hiçbir giriş ve hiçbir epilog sahip bir parçasını tanımlayan kendi ve.xdata'yı veya sanal işlem bulunur kaydı alır. Ancak, bu bölge için bırakma kodlarının işlev gövdesi dikkate almıştır çünkü mevcut olmalıdır. Kodları bölge bir başlangıç ve bölge B girmeden önce bir dizi işlemleri tarafından üretilmiş olan gibi kaydedilen ek kayıtları kaydedilen her iki özgün kayıtları temsil eden birleşik bir başlangıç açıklamak gerekir.  
  
 Kayıt için bölge B açıklanan birleşik giriş bölgesi bir başlangıç ve kaydedilmiş ek kayıtları açıklamak gerekir çünkü bir "İç Giriş" B kabul edemiyor bölge için kaydeder. Parça B bir başlangıç sahip olarak açıklandığı gibi bırakma kodlarının bu başlangıç boyutu kapsıyor ve birleşik giriş bire bir olarak yalnızca ek Yazmaçları kaydedemez işlem ile eşleşen bir şekilde tanımlamak için bir yolu yoktur.  
  
 Bunlar tamamlanana kadar bileşik Giriş yığını durumunu doğru şekilde tanımlamaz çünkü ek kayıt kaydeder A bölgesinin bir parçası olarak düşünülmelidir.  
  
 Son C bölgenin hiçbir giriş vardır, ancak bir epilog bir parçasını tanımlayan kendi ve.xdata'yı veya sanal işlem bulunur kaydı alır.  
  
 Bölge B girmeden önce bitti yığını işleme için tek bir yönerge azaltılabilir, alternatif bir yaklaşım da çözüm bulabilirsiniz:  
  
```  
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
  
 Burada her yönerge sınırında yığın bölge için bırakma kodlarının ile tam olarak tutarlı olduğunu anahtardır. Bu örnekte iç itme önce bırakmayla meydana gelirse, bölge bir parçası olarak kabul edilir ve yalnızca bir giriş unwound bölgedir. İç itme sonra bırakma meydana gelirse, hiçbir giriş, ancak iç itme ve özgün giriş A. benzer mantığı bölgesinden açıklayan bırakma kodları içeriyor B bölgesinin bir parçası için iç pop tutan kabul edilir.  
  
### <a name="encoding-optimizations"></a>Kodlama en iyi duruma getirme  
 Bırakma kodlarının ve Dengeleme Sıkıştır ve veri genişletilmiş forms yeteneği zenginliğinin nedeniyle daha fazla alanı azaltmak için kodlama iyileştirmek için birçok fırsatları vardır. Bu teknikler agresif kullanımıyla, İşlevler ve parçaları bırakma kodlarını kullanarak açıklayan net yükünü oldukça minimal düzeyde olabilir.  
  
 En önemli iyileştirme başlangıç/epilog sınırları derleyici açısından mantıksal başlangıç/epilog sınırlarla unwinding amacıyla karıştırır değil dikkatli olacak. Unwinding sınırları küçültülebilir ve verimliliği artırmak için daha sıkı yapılır. Örneğin, ek doğrulama gerçekleştirmek için yığın Kurulumu denetledikten sonra bir başlangıç kodu içerebilir. Ancak tüm yığın işleme tamamlandıktan sonra daha fazla işlem kodlamak için gerek yoktur ve ötesinde herhangi bir şey unwinding giriş kaldırılabilir.  
  
 Bu aynı kural işlevi uzunluğa uygular. Veri ise — örneğin, bir değişmez değer havuzu — bir işlevdeki bir epilog izler, işlevi uzunluğu bir parçası olarak dahil olmamalıdır. İşlev'in bir parçası olan kodu için işlevi küçülterek olasılığını epilog sonuna ve CD olacağını çok büyük. pdata kaydı kullanılabilir.  
  
 Bir giriş, yığın işaretçisi başka bir kasaya kaydedildikten sonra genellikle başka bir işlem kodları kaydetmek için gerek yoktur. İşlev bırakma için yapmıştır ilk şey SP kaydedilmiş kasadan kurtarmak için ve bu nedenle daha fazla işlem herhangi bir etki bırakma üzerinde sahip değil.  
  
 Tek yönerge sonuçları hiç, kapsam olarak da kodlanması gerekmez veya olarak kodlarının bırakma. Bu yönerge yürütülmeden önce bırakmayla yer alıyorsa, ardından bu işlev gövdesi içinde arasında için kabul edilebilir ve yalnızca giriş bırakma kodlarının yürütme yeterlidir. Tek yönerge yürütüldükten sonra bırakma yer alıyorsa, ardından tanım olarak, başka bir bölgede gerçekleşir.  
  
 Önceki noktası olarak aynı nedenden dolayı epilog ilk talimat kodlamak çok yönerge sonuçları gerekmez: Bu yönerge yürütülmeden önce bırakma gerçekleşir, bir tam giriş bırakma yeterli olur. Bırakma sonra bu yönerge yer alıyorsa, yalnızca sonraki işlemleri kabul edilmesi gerekir.  
  
 Bırakma kodu yeniden kullanma agresif olmalıdır. Dizide bir rastgele başlangıç noktası bırakma kodlarının her epilog kapsam noktalarına tarafından belirtilen dizin. Önceki sıra başlangıcına işaret edecek şekilde yok; Ortadaki gösterebilir. En iyi burada istenen kod sırası oluşturmak ve sıralarının zaten kodlanmış havuzundaki tam bayt eşleştirmesi için tarama ve yeniden kullanım için mükemmel bir ikili bir başlangıç noktası olarak kullanmak için bir yaklaşımdır.  
  
 Tek yönerge sonuçları göz ardı edilir sonra varsa, hiçbir kalan sonuçları compact ve.xdata'yı form; kullanmayı düşünün çok daha büyük bir olasılıkla bir epilog olmaması durumunda olur.  
  
## <a name="examples"></a>Örnekler  
 Bu örneklerde, 0x00400000 görüntü tabanıdır.  
  
### <a name="example-1-leaf-function-no-locals"></a>Örnek 1: Yaprak işlevi, hiçbir yerel öğeler  
  
```  
Prologue:  
  004535F8: B430      push        {r4-r5}  
Epilogue:  
  00453656: BC30      pop         {r4-r5}  
  00453658: 4770      bx          lr  
```  
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* (= 0x004535F8 0x00400000) 0x000535F8 =  
  
-   Word 1  
  
    -   *Bayrak* = 1, kurallı başlangıç ve epilog biçimlerinin belirten  
  
    -   *İşlev uzunluğu* 0x31 = (0x62/2 =)  
  
    -   *Ret* = 1, 16 bit şube dönüş belirten  
  
    -   *H* = 0, parametreleri belirten değil bağlantılı  
  
    -   *R*= 0 ve *Reg* = 1, r4 r5 itme/pop belirten  
  
    -   *M* = 0, hiçbir LR kaydedilemiyor/geri belirten  
  
    -   *C* = 0, hiçbir çerçeve zincirleme belirten  
  
    -   *Ayarla yığın* = 0, hiçbir yığın ayarlama belirten  
  
### <a name="example-2-nested-function-with-local-allocation"></a>Örnek 2: İç içe geçmiş işlev yerel ayırma ile  
  
```  
Prologue:  
  004533AC: B5F0      push        {r4-r7, lr}  
  004533AE: B083      sub         sp, sp, #0xC  
Epilogue:  
  00453412: B003      add         sp, sp, #0xC  
  00453414: BDF0      pop         {r4-r7, pc}  
```  
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* 0x000533AC = (0x004533AC =-0x00400000)  
  
-   Word 1  
  
    -   *Bayrak* = 1, kurallı başlangıç ve epilog biçimlerinin belirten  
  
    -   *İşlev uzunluğu* 0x35 = (0x6A/2 =)  
  
    -   *Ret* = 0, dönüş pop {pc} belirten  
  
    -   *H* = 0, parametreleri belirten değil bağlantılı  
  
    -   *R*= 0 ve *Reg* = 3, r4 r7 itme/pop belirten  
  
    -   *M* = 1, LR belirten kaydedilmiş/geri yüklendi  
  
    -   *C* = 0, hiçbir çerçeve zincirleme belirten  
  
    -   *Yığın ayarlamak* = 3 (0x0C/4 =)  
  
### <a name="example-3-nested-variadic-function"></a>Örnek 3: İç içe geçmiş Variadic işlevi  
  
```  
Prologue:  
  00453988: B40F      push        {r0-r3}  
  0045398A: B570      push        {r4-r6, lr}  
Epilogue:  
  004539D4: E8BD 4070 pop         {r4-r6}  
  004539D8: F85D FB14 ldr         pc, [sp], #0x14  
```  
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* (= 0x00453988 0x00400000) 0x00053988 =  
  
-   Word 1  
  
    -   *Bayrak* = 1, kurallı başlangıç ve epilog biçimlerinin belirten  
  
    -   *İşlev uzunluğu* 0x2A = (0x54/2 =)  
  
    -   *Ret* = {pc} pop gösteren 0-stil return (Bu durumda bir ldr pc [sp] #0x14 return)  
  
    -   *H* = 1, parametreleri belirten bağlantılı  
  
    -   *R*= 0 ve *Reg* = 2, r4 r6 itme/pop belirten  
  
    -   *M* = 1, LR belirten kaydedilmiş/geri yüklendi  
  
    -   *C* = 0, hiçbir çerçeve zincirleme belirten  
  
    -   *Ayarla yığın* = 0, hiçbir yığın ayarlama belirten  
  
### <a name="example-4-function-with-multiple-epilogues"></a>Örnek 4: Birden çok sonuçları olan işlevi  
  
```  
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
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* (= 0x004592F4 0x00400000) 0x000592F4 =  
  
-   Word 1  
  
    -   *Bayrak* = 0, sanal işlem bulunur kayıt mevcut belirten (birden çok sonuçları nedeniyle gereklidir)  
  
    -   *Sanal işlem bulunur adresi* -0x00400000  
  
 (değişkeni, 6 sözcükler) sanal işlem bulunur:  
  
-   Word 0  
  
    -   *İşlev uzunluğu* 0x0001A3 (= 0x000346/2) =  
  
    -   *Sürücüleri* xdata ilk sürümünü gösteren 0 =  
  
    -   *X* = 0, hiçbir özel durum verileri belirten  
  
    -   *E* epilog kapsamları listesini gösteren 0 =  
  
    -   *F* = 0, başlangıç dahil olmak üzere tam işlevli açıklamasını gösteren  
  
    -   *Epilog sayısı* 4 toplam epilog kapsamları belirten 0x04 =  
  
    -   *Kod sözcük* bırakma kodlarının bir 32 bit sözcük belirten 0x01 =  
  
-   1-4, 4 konumlara 4 epilog kapsamları açıklayan sözcükler. Her kapsam bırakma kodları, 0x00, uzaklığındaki giriş paylaşılan ortak bir dizi ve koşulsuz koşulu 0x0E belirtme (her zaman).  
  
-   Word 5 başlangıç kodları bırakma: (Başlangıç/epilog arasında paylaşılan)  
  
    -   Bırakma kodu 0 = 0x06: sp += (6 << 2)  
  
    -   Bırakma kodu 1 = 0xDE: pop {r4 r10, lr}  
  
    -   Bırakma kodu 2 = 0xFF: son  
  
### <a name="example-5-function-with-dynamic-stack-and-inner-epilogue"></a>Örnek 5: Dinamik yığını ve iç epilog olan işlevi  
  
```  
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
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* (= 0x00485A20 0x00400000) 0x00085A20 =  
  
-   Word 1  
  
    -   *Bayrak* = 0, sanal işlem bulunur kayıt mevcut belirten (birden çok sonuçları nedeniyle gereklidir)  
  
    -   *Sanal işlem bulunur adresi* -0x00400000  
  
 (değişkeni, 3 sözcükler) sanal işlem bulunur:  
  
-   Word 0  
  
    -   *İşlev uzunluğu* 0x0001A3 (= 0x000346/2) =  
  
    -   *Sürücüleri* xdata ilk sürümünü gösteren 0 =  
  
    -   *X* = 0, hiçbir özel durum verileri belirten  
  
    -   *E* epilog kapsamları listesini gösteren 0 =  
  
    -   *F* = 0, başlangıç dahil olmak üzere tam işlevli açıklamasını gösteren  
  
    -   *Epilog sayısı* 1 toplam epilog kapsamı belirten 0x001 =  
  
    -   *Kod sözcük* bırakma kodlarının bir 32 bit sözcük belirten 0x01 =  
  
-   Word 1: 0x00 ve 0x0E (her zaman) koşuluyla bırakma kodu dizininden başlayarak epilog kapsam uzaklığından 0xC6, (0x18C/2 =)  
  
-   Word 2'de başlangıç kodları bırakma: (Başlangıç/epilog arasında paylaşılan)  
  
    -   Bırakma kodu 0 = 0xC6: sp r6 =  
  
    -   Bırakma kodu 1 = 0xDC: pop {r4 r8, lr}  
  
    -   Bırakma kodu 2 = 0x04: sp += (4 << 2)  
  
    -   Bırakma kodu 3 = 0xFD: son, epilog 16 bit yönergesi olarak sayar  
  
### <a name="example-6-function-with-exception-handler"></a>Örnek 6: Özel durum işleyici işlevi  
  
```  
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
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* (= 0x00488C24 0x00400000) 0x00088C24 =  
  
-   Word 1  
  
    -   *Bayrak* = 0, sanal işlem bulunur kayıt mevcut belirten (birden çok sonuçları nedeniyle gereklidir)  
  
    -   *Sanal işlem bulunur adresi* -0x00400000  
  
 (değişkeni, 5 sözcük) sanal işlem bulunur:  
  
-   Word 0  
  
    -   *İşlev uzunluğu* 0x000027 (= 0x00004E/2) =  
  
    -   *Sürücüleri* xdata ilk sürümünü gösteren 0 =  
  
    -   *X* = 1, mevcut özel durum verileri belirten  
  
    -   *E* = 1, tek bir epilog belirten  
  
    -   *F* = 0, başlangıç dahil olmak üzere tam işlevli açıklamasını gösteren  
  
    -   *Epilog sayısı* epilog bırakma kodlarının başlangıç uzaklığı 0x00 belirten 0x00 =  
  
    -   *Kod sözcük* 0x02, iki 32-bit sözcük bırakma kodlarının belirten =  
  
-   Word 1'den başlayarak kodları bırakma:  
  
    -   Bırakma kodu 0 = 0xC7: sp r7 =  
  
    -   Bırakma kodu 1 = 0x05: sp += (5 << 2).  
  
    -   Bırakma kodu 2 = 0xED/0x90: pop {r4 r7, lr}  
  
    -   Bırakma kodu 4 = 0xFF: son  
  
-   Word 3 belirten bir özel durum işleyici 0x0019A7ED = (0x0059A7ED - = 0x00400000)  
  
-   Sözcükler 4 ve ötesine içermesinden özel durum verileri  
  
### <a name="example-7-funclet"></a>Örnek 7: Funclet  
  
```  
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
  
 ve.xdata'yı (sabit, 2 sözcükler):  
  
-   Word 0  
  
    -   *İşlev başlangıç RVA* (= 0x00488C72 0x00400000) 0x00088C72 =  
  
-   Word 1  
  
    -   *Bayrak* = 1, kurallı başlangıç ve epilog biçimlerinin belirten  
  
    -   *İşlev uzunluğu* 0x0B = (0x16/2 =)  
  
    -   *Ret* = 0, dönüş pop {pc} belirten  
  
    -   *H* = 0, parametreleri belirten değil bağlantılı  
  
    -   *R*= 0 ve *Reg* = 7, hiçbir yazmaçlar belirten kaydedilmiş ve geri  
  
    -   *M* = 1, LR belirten kaydedilmiş/geri yüklendi  
  
    -   *C* = 0, hiçbir çerçeve zincirleme belirten  
  
    -   *Ayarla yığın* = 1, 1 × 4 bayt yığın ayarlama belirten  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ARM ABI kuralları genel bakış](../build/overview-of-arm-abi-conventions.md)   
 [Genel Visual C++ ARM Geçiş Sorunları](../build/common-visual-cpp-arm-migration-issues.md)