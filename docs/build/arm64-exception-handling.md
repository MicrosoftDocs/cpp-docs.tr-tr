---
title: ARM64 özel durum işleme
ms.date: 11/19/2018
ms.openlocfilehash: b4f9a5d6f86f8b88ef42525e6a9bb1b4071585ce
ms.sourcegitcommit: a9f1a1ba078c2b8c66c3d285accad8e57dc4539a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2019
ms.locfileid: "72037759"
---
# <a name="arm64-exception-handling"></a>ARM64 özel durum işleme

Windows ARM64 on, zaman uyumsuz donanım tarafından oluşturulan özel durumlar ve zaman uyumlu yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme mekanizmasını kullanır. Dile özgü özel durum işleyicileri dil Yardımcısı işlevleri kullanılarak Windows yapılandırılmış özel durum işlemenin üzerine kurulmuştur. Bu belge, ARM64 üzerinde Windows 'da özel durum işlemeyi ve Microsoft ARM Assembler ve MSVC derleyicisi tarafından oluşturulan kod tarafından kullanılan dil yardımcılarını açıklar.

## <a name="goals-and-motivation"></a>Hedefler ve mosyon

Özel durum, verileri geriye doğru izleme ve bu açıklamanın amacı:

1. Her durumda kod yoklama olmadan geri sarma sağlamak için yeterli açıklama sağlayın.

   - Kodun çözümlenmesi için kodun içinde disk belleği olması gerekir. Bu, yararlı olduğu durumlarda (izleme, örnekleme, hata ayıklama) bazı durumlarda geriye doğru izlemeyi önler.

   - Kodun çözümlenmesi karmaşıktır; Derleyicinin yalnızca unwinder 'in kod çözme yeteneğine sahip olduğu yönergeler oluşturmak için dikkatli olması gerekir.

   - Geriye doğru izleme geri sarma kodlarının kullanımı aracılığıyla tam olarak açıklanmıyorsa, bazı durumlarda yönerge kod çözmede geri dönemelidir. Bu, genel karmaşıklığı artırır ve ideal olarak kaçınılmaz.

1. Orta-giriş ve orta/bitiş sürümünde geriye doğru izlemeyi destekler.

   - Geri sarma, Windows 'da özel durum işleme için kullanılır; bu nedenle, giriş veya bitiş kodu sırasının ortasında bile, doğru bir geriye doğru izleme gerçekleştirebilmemiz önemlidir.

1. En az miktarda alan alın.

   - İkili boyutu önemli ölçüde arttırabileceğiniz bırakma kodlarının toplamı olmamalıdır.

   - Geriye doğru izleme kodları bellekte kilitlenmiş olduğundan küçük bir kaplama, yüklenen her ikili için en az ek yük sağlar.

## <a name="assumptions"></a>Varsayımlar

Özel durum işleme açıklamasında yapılan varsayımlar şunlardır:

1. Prologs ve epııd 'ler diğerini yansıtmaya eğilimlidir. Bu ortak nitelik avantajlarından yararlanarak, geriye doğru izlemeyi anlatmak için gereken meta verilerin boyutu büyük ölçüde azaltılabilir. İşlevin gövdesinde, giriş işlemlerinin geri alınmadığına veya bitiş işlemlerinin ileri bir biçimde gerçekleştirildiğinden bağımsız değildir. Her ikisi de özdeş sonuçlar üretmelidir.

1. İşlevler görece küçük olacak şekilde tamamen eğilimlidir. Alan için birkaç iyileştirme, verilerin en verimli şekilde paketlenmesi için bunu kullanır.

1. Epıte 'ler içinde hiç koşullu kod yok.

1. Adanmış çerçeve işaretçisi kaydı: SP, ana sırada başka bir kayda (x29) kaydedilirse, bu kayıt işlevin tamamında değişmeden kalır, böylece özgün SP herhangi bir zamanda kurtarılabilir.

1. SP başka bir kayda kaydedilmediği takdirde, yığın işaretçisinin tüm düzenlemesi tamamen giriş ve bitiş içinde gerçekleşir.

1. Yığın çerçeve düzeni, sonraki bölümde açıklandığı gibi düzenlenmiştir.

## <a name="arm64-stack-frame-layout"></a>ARM64 Stack çerçeve düzeni

![yığın çerçeve düzeni](media/arm64-exception-handling-stack-frame.png "yığın çerçeve düzeni")

Çerçeve zincirleme işlevleri için, fp ve LR çiftinin, iyileştirme konularına bağlı olarak yerel değişken alanındaki herhangi bir konuma kaydedilebilir. Amaç, çerçeve işaretçisi (x29) veya yığın işaretçisi (SP) temelinde tek bir yönerge tarafından erişilebilecek yerellerin sayısını en üst düzeye çıkarmaktır. Ancak `alloca` işlevleri için, zincirleme olmalıdır ve x29 yığının alt kısmına işaret etmelidir. Daha iyi yazmaç-çift adresleme modu kapsamına izin vermek için, kalıcı kayıt kaydetme alanlarına yerel alan yığınının en üstünde konumlandırılmış. Aşağıda, en verimli giriş dizilerinin birkaçını gösteren örnekler verilmiştir. Netlik ve daha iyi önbellek konumu için, tüm kurallı progünlüklerde çağrılan kayıtlı yazmaçların depolanması sırası "büyümekte" sırada. `#framesz`, yığının tamamının boyutunu (alloca alanı hariç) temsil eder. `#localsz` ve `#outsz`, sırasıyla yerel alan boyutunu (\<x29, LR > çiftinin kaydetme alanı dahil) ve giden parametre boyutunu gösterir.

1. Zincirleme, #localsz \< = 512

    ```asm
        stp    x19,x20,[sp,#-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,#16]            // save in FP regs (optional)
        stp    x0,x1,[sp,#32]            // home params (optional)
        stp    x2,x3,[sp,#48]
        stp    x4,x5,[sp,#64]
        stp    x6,x7,[sp,#72]
        stp    x29,lr,[sp,#-localsz]!   // save <x29,lr> at bottom of local area
        mov    x29,sp                   // x29 points to bottom of local
        sub    sp,sp,#outsz             // (optional for #outsz != 0)
    ```

1. Zincirleme, #localsz > 512

    ```asm
        stp    x19,x20,[sp,#-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,#16]            // save in FP regs (optional)
        stp    x0,x1,[sp,#32]            // home params (optional)
        stp    x2,x3,[sp,#48]
        stp    x4,x5,[sp,#64]
        stp    x6,x7,[sp,#72]
        sub    sp,sp,#(localsz+outsz)   // allocate remaining frame
        stp    x29,lr,[sp,#outsz]       // save <x29,lr> at bottom of local area
        add    x29,sp,#outsz            // setup x29 points to bottom of local area
    ```

1. Zincirleme olmayan, yaprak işlevleri (LR kaydedilmemiş)

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]
        str    x23,[sp,#32]
        stp    d8,d9,[sp,#40]           // save FP regs (optional)
        stp    d10,d11,[sp,#56]
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   Tüm Yereller SP 'ye göre erişilir. \<x29, LR > Önceki çerçeveye işaret eder. Çerçeve boyutu için \< = 512, "sub SP,..." Regs kaydedilmiş alanı yığının altına taşınırsa en iyi duruma getirilebilir. Bunun aşağı tarafında, yukarıdaki diğer düzenlerle tutarlı olmadığı ve kayıtlı Regs, Çift Regs ve ön ve dizinli Adres belirleme modu için aralığın bir kısmını alır.

1. Zincirsiz, yaprak olmayan işlevler (LR, INT kaydedilmiş alana kaydedilir)

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]         // ...
        stp    x23,lr,[sp,#32]          // save last Int reg and lr
        stp    d8,d9,[sp,#48]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,#64]         // ...
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   Ya da, hatta sayı kaydedilmiş Int Yazmaçları,

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]         // ...
        str    lr,[sp,#32]              // save lr
        stp    d8,d9,[sp,#40]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,#56]         // ...
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   Yalnızca x19 kaydedildi:

    ```asm
        sub    sp,sp,#16                // reg save area allocation*
        stp    x19,lr,[sp]              // save x19, lr
        sub    sp,sp,#(framesz-16)      // allocate the remaining local area
    ```

   \* ön dizinli bir reg-LR STP, bırakma kodlarıyla temsil edilemediğinden, reg save alanı ayırması STP 'ye katlanmaz.

   Tüm Yereller SP 'ye göre erişilir. \<x29 > Önceki çerçeveye işaret eder.

1. Zincirleme, #framesz \< = 512, #outsz = 0

    ```asm
        stp    x29,lr,[sp,#-framesz]!       // pre-indexed, save <x29,lr>
        mov    x29,sp                       // x29 points to bottom of stack
        stp    x19,x20,[sp,#(framesz-32)]   // save INT pair
        stp    d8,d9,[sp,#(framesz-16)]     // save FP pair
    ```

   Yukarıdaki #1 giriş ile karşılaştırıldığında, tüm Register kaydetme yönergelerinin tek bir yığın ayırma yönergesinden hemen sonra çalıştırılmaya hazırlanması avantajıdır. Bu nedenle, yönerge düzeyi paralelliği önleyen, SP üzerinde koruma önleyici bir CE yoktur.

1. Zincirleme, çerçeve boyutu > 512 (alloca olmayan işlevler için isteğe bağlı)

    ```asm
        stp    x29,lr,[sp,#-80]!            // pre-indexed, save <x29,lr>
        stp    x19,x20,[sp,#16]             // save in INT regs
        stp    x21,x22,[sp,#32]             // ...
        stp    d8,d9,[sp,#48]               // save in FP regs
        stp    d10,d11,[sp,#64]
        mov    x29,sp                       // x29 points to top of local area
        sub    sp,sp,#(framesz-80)          // allocate the remaining local area
    ```

   En iyi duruma getirme amacıyla, x29, "Reg-Pair" ve pre-/post-dizinli fark adresleme modu için daha iyi bir kapsam sağlamak üzere yerel alandaki herhangi bir konuma yerleştirilebilir. Çerçeve işaretçilerine aşağıdaki Yereller SP 'ye dayalı olarak erişilebilir.

1. Zincirleme, çerçeve boyutu > 4K, alloca () ile veya olmadan

    ```asm
        stp    x29,lr,[sp,#-80]!            // pre-indexed, save <x29,lr>
        stp    x19,x20,[sp,#16]             // save in INT regs
        stp    x21,x22,[sp,#32]             // ...
        stp    d8,d9,[sp,#48]               // save in FP regs
        stp    d10,d11,[sp,#64]
        mov    x29,sp                       // x29 points to top of local area
        mov    x15,#(framesz/16)
        bl     __chkstk
        sub    sp,sp,x15,lsl#4              // allocate remaining frame
                                            // end of prolog
        ...
        sub    sp,sp,#alloca                // more alloca() in body
        ...
                                            // beginning of epilog
        mov    sp,x29                       // sp points to top of local area
        ldp    d10,d11,[sp,#64]
        ...
        ldp    x29,lr,[sp],#80              // post-indexed, reload <x29,lr>
    ```

## <a name="arm64-exception-handling-information"></a>ARM64 özel durum işleme bilgileri

### <a name="pdata-records"></a>. pdata kayıtları

. Pdata kayıtları, bir PE ikilisindeki yığın işleme işlevinin her birini açıklayan sabit uzunluklu öğelerin sıralı dizisidir. "Yığın işleme" ifadesini dikkatle not edin: herhangi bir yerel depolama gerektirmeyen ve geçici olmayan kayıtların kaydedilmesi/geri yüklenmesi gerekmeyen yaprak işlevleri. pdata kaydı gerektirmez; Bu, boş alan kazanmak için açıkça atlanmalıdır. Bu işlevlerden birinden geriye doğru dönmek için, yalnızca LR 'den dönüş adresini alabilir.

ARM64 için her. pdata kaydının uzunluğu 8 bayttır. Her kaydın genel biçimi, işlevin 32 bit RVA 'Sı olan ilk sözcüğe, sonra da değişken uzunluklu bir. xdata bloğuna yönelik bir işaretçi veya kurallı bir işlevin sargı sırasını açıklayan paketlenmiş bir sözcüğe sahiptir.

![. pdata kayıt düzeni](media/arm64-exception-handling-pdata-record.png ". pdata kayıt düzeni")

Alanlar aşağıdaki gibidir:

- **Işlev başlangıç RVA** , işlevin başlangıcına ait 32 bitlik RVA 'ya sahiptir.

- **Bayrak** , ikinci. pdata sözcüğünün kalan 30 bitini nasıl yorumlayacağını belirten 2 bitlik bir alandır. **Bayrak** 0 ise, kalan bit bir **özel durum bilgisi RVA** (düşük iki bit örtülü 0) oluşturur. **Bayrak** sıfır olmayan bir değer ise, kalan bitler **paketlenmiş bir geriye doğru izleme veri** yapısı oluşturur.

- **Özel durum BILGISI RVA** ,. xdata bölümünde depolanan değişken uzunluklu özel durum bilgisi yapısının adresidir. Bu veriler 4 bayt hizalı olmalıdır.

- **Paketlenmiş geriye doğru Izleme verileri** , bir işlevden geri dönmek için gereken işlemlerin sıkıştırılmış bir açıklamasıdır; kurallı bir form kabul edilir. Bu durumda, hiçbir. xdata kaydı gerekli değildir.

### <a name="xdata-records"></a>. xdata kayıtları

Paketlenmiş bırakma biçimi, bir işlevin geri sarılini anlatmak için yetersizse, değişken uzunluklu bir. xdata kaydı oluşturulmalıdır. Bu kaydın adresi. pdata kaydının ikinci sözcüğündeki saklanır. . Xdata biçimi, paketlenmiş değişken uzunlukta bir sözcük kümesidir:

![. xdata kayıt düzeni](media/arm64-exception-handling-xdata-record.png ". xdata kayıt düzeni")

Bu veriler dört bölümden ayrılır:

1. Yapının genel boyutunu açıklayan ve anahtar işlev verileri sağlayan 1 veya 2 sözcüklü bir üst bilgi. İkinci sözcük yalnızca, hem **bitiş sayısı** hem de **kod sözcükleri** alanları 0 olarak ayarlandığında bulunur. Başlıktaki bit alanları şunlardır:

   a. **Işlev uzunluğu** , işlevin toplam uzunluğunu bayt cinsinden gösteren 18 bitlik bir alandır. Bir işlev 1M değerinden büyükse, işlevi anlatmak için birden çok pData ve XData kaydı kullanılmalıdır. Daha fazla ayrıntı için [büyük işlevler](#large-functions) bölümüne bakın.

   b. Sunucular **, kalan** XData 'ın sürümünü açıklayan 2 bitlik bir alandır. Bu yazma itibariyle, yalnızca sürüm 0 tanımlı ve bu nedenle 1-3 değerlerine izin verilmez.

   c. **X** , varlık (1) veya Devamsızlık (0) özel durum verilerinin olduğunu gösteren 1 bitlik bir alandır.

   d. **E** , bir bit alanı, tek bir bir bitiş tanımlayan bilgilerin, daha sonra ek kapsam sözcükleri gerektirmek yerine üstbilgiye (1) paketlendiğini belirtir.

   e. **Bitiş sayısı** , **E** bit durumuna bağlı olarak iki anlamı olan 5 bitlik bir alandır:

      1. **E** 0 olarak ayarlandıysa: Bölüm 2 ' de açıklanan toplam bitiş kapsamı sayısının sayısını belirtir. İşlevde 31 ' den fazla kapsam varsa, bir uzantı sözcüğünün gerekli olduğunu göstermek için **kod kelimeleri** alanının 0 olarak ayarlanması gerekir.

      2. **E** 1 olarak ayarlandıysa, bu alan ilk bırakma kodunun dizinini ve yalnızca bir bitiş olduğunu tanımlar.

   f. **Kod sözcükleri** , Bölüm 3 ' teki tüm bırakma kodlarını içermesi gereken 32 bitlik sözcüklerin sayısını belirten 5 bitlik bir alandır. 31 ' den fazla sözcük gerekliyse (örneğin, 124 'den daha fazla bırakma kodu baytı), bir uzantı sözcüğünün gerekli olduğunu göstermek için bu alanın 0 olarak ayarlanması gerekir.

   g. **Genişletilmiş bitiş sayısı** ve **genişletilmiş kod kelimeleri** sırasıyla, genellikle çok fazla sayıda epıte veya alışılmadık sayıda bırakma kodu sözcüklerini kodlamak için daha fazla alan sağlayan 16 bit ve 8 bit alanlardır. Bu alanları içeren uzantı sözcüğü yalnızca ilk üstbilgi sözcükündeki **bitiş sayısı** ve **kod sözcükleri** alanları 0 olarak ayarlandığında bulunur.

1. Üst bilgi ve yukarıda açıklanan isteğe bağlı genişletilmiş üst bilgiden sonra, **bitiş sayısı** sıfır değilse, bitiş kapsamları hakkında bilgi listesi, bir sözcüğe paketlenmiş ve başlangıç sapmasını artırma sırasına göre depolanır. Her kapsam aşağıdaki bitleri içerir:

   a. **Bitiş başlangıç boşluğu** , işlevin başlangıcına göre toplam değeri 4 ' e bölünen bir 18 bit alandır

   b. **Res** , gelecekteki genişlemeye ayrılmış 4 bitlik bir alandır. Değeri 0 olmalıdır.

   c. **Bitiş başlangıç dizini** , bu başlangıcı açıklayan ilk bırakma kodunun bayt dizinini gösteren 10 bit ( **genişletilmiş kod kelimeden**2 daha fazla bit) alanıdır.

1. Bitiş kapsamları listesi sonrasında, sonraki bölümde ayrıntılı olarak açıklanan geriye doğru izleme kodları içeren bir bayt dizisi gelir. Bu dizi, sonda en yakın tam sözcük sınırına doldurulur. Geriye doğru izleme kodları, işlevin kenarlarına doğru bir şekilde hareket eden bir işlev gövdesine başlayarak bu diziye yazılır. Her bir açılım kodu için baytlar büyük endian düzeninde depolanır, bu sayede, işlemi ve kodun geri kalanının uzunluğunu tanımlayan en önemli bayttan başlayarak doğrudan getirilebilirler.

1. Son olarak, geri bırakma kodu baytından sonra, üstbilgideki **X** biti 1 olarak ayarlandıysa, özel durum işleyicisi bilgilerini verir. Bu, özel durum işleyicisinin kendisinin adresini sağlayan tek bir **özel durum IŞLEYICI RVA** ve ardından, özel durum işleyicisi için gereken değişken uzunluklu bir veri miktarıyla hemen oluşur.

Yukarıdaki. xdata kaydı, ilk 8 baytı getirmek ve bu işlem için kaydın tam boyutunu (izleyen değişken boyutlu özel durum verilerinin uzunluğu eksi) getirmek mümkün olduğu için tasarlanmıştır. Aşağıdaki kod parçacığı, kayıt boyutunu hesaplar:

```cpp
ULONG ComputeXdataSize(PULONG *Xdata)
{
    ULONG EpilogScopes;
    ULONG Size;
    ULONG UnwindWords;

    if ((Xdata[0] >> 27) != 0) {
        Size = 4;
        EpilogScopes = (Xdata[0] >> 22) & 0x1f;
        UnwindWords = (Xdata[0] >> 27) & 0x0f;
    } else {
        Size = 8;
        EpilogScopes = Xdata[1] & 0xffff;
        UnwindWords = (Xdata[1] >> 16) & 0xff;
    }

    Size += 4 * EpilogScopes;
    Size += 4 * UnwindWords;
    if (Xdata[0] & (1 << 20)) {
        Size += 4;        // exception handler RVA
    }
    return Size;
}
```

Hem giriş hem de her bir bitiş 'nin geri bırakma kodlarına ait dizini olmasına rağmen, tablo aralarında paylaşıldığından ve tamamen mümkün değildir (ve tamamen seyrek olmasa da), hepsi aynı kodları paylaşabildiklerinden emin olur (örnekler bölümünde bkz. örnek 2 ow). Derleyici yazarları bu durum için iyileştirmelidir, çünkü belirtilen en büyük dizin 255, bu nedenle belirli bir işlev için toplam bırakma kodu sayısını kısıtlar.

### <a name="unwind-codes"></a>Bırakma kodları

Geriye doğru izleme kodları dizisi, giriş işlemlerinin etkilerini tam olarak nasıl geri alınacağını açıklayan sıraların havuzudur. Geriye doğru izleme kodları, bayt dizesi olarak kodlanmış bir mini yönerge kümesi olarak düşünülebilir. Yürütme tamamlandığında, çağırma işlevine döndürülen adres, LR kaydına, geçici olmayan tüm Yazmaçları ise işlevin çağrıldığı zaman değerlerine geri yüklenir.

Özel durumların yalnızca bir işlev gövdesinde (ve hiçbir zaman bir giriş ya da herhangi bir bitiş ile) oluşması garantilenir ise yalnızca tek bir sıra gereklidir. Ancak, Windows unsargı modeli, kısmen yürütülen bir giriş veya bitiş içinden geriye doğru izleme yapabilmemiz için gereklidir. Bu gereksinime uyum sağlamak için, geriye doğru izleme kodları, giriş ve bitiş içindeki ilgili her Opcode 1:1 ' i önemli bir şekilde eşlemenizi sağlayacak biçimde dikkatle tasarlanmıştır. Bu çeşitli etkilere sahiptir:

1. Bırakma kodlarının sayısını sayarak, giriş ve bitiş uzunluğunu hesaplamak mümkündür.

1. Bir bitiş kapsamının başlangıcından geçmiş yönergelerin sayısını sayarak, geriye doğru izleme kodlarının sayısını atlayıp, bir sıranın geri kalanını yürüterek, bu da bir sıranın gerçekleştirdiği geriye doğru gerçekleştirilen geriye doğru izleme işlemini tamamlar.

1. Giriş sonundaki yönergelerin sayısını sayarak, geriye doğru izleme kodlarının sayısını atlayıp, yalnızca yürütmeyi tamamlamış olan giriş parçalarını geri almak için sıranın geri kalanını yürütün.

Geriye doğru izleme kodları aşağıdaki tabloya göre kodlanır. Tüm bırakma kodları, büyük bir yığını ayıran tek bir/çift bayttır. 21 bırakma kodu tamamen vardır. Her bir açılım kodu, kısmen yürütülen prologs ve epıların geri sarılarına izin vermek için giriş/bitiş içinde tam olarak bir yönergeyi eşler.

|Bırakma kodu|BITS ve yorum|
|-|-|
|`alloc_s`|000xxxxx: \< 512 (2 ^ 5 * 16) boyutunda küçük yığın ayır.|
|`save_r19r20_x`|    001zzzzz: \<x19, x20 > çiftini [SP-#Z * 8]!, önceden dizinli uzaklığında Kaydet > =-248 |
|`save_fplr`|        01zzzzzz: \<x29, LR > çiftini [SP + #Z * 8], fark \< = 504 olarak kaydet. |
|`save_fplr_x`|        10zzzzzz: \<x29, LR > çiftini [SP-(#Z + 1) * 8]!, önceden dizinli uzaklığında Kaydet > =-512 |
|`alloc_m`|        11000xxx'xxxxxxxx: \< 16k (2 ^ 11 * 16) boyutunda büyük yığın ayır. |
|`save_regp`|        110010xx'xxzzzzzz: [SP + #Z * 8] konumundaki x (19 + #X) çiftini Kaydet, fark \< = 504 |
|`save_regp_x`|        110011xxixxzzzzzz: [SP-(#Z + 1) * 8]!, önceden dizinli fark > =-512) konumundaki x (19 + #X) çiftini Kaydet |
|`save_reg`|        110100xx'xxzzzzzz: [SP + #Z * 8], fark \< = 504) konumundaki reg x (19 + #X) kaydetme |
|`save_reg_x`|        1101010x'xxxzzzzz: [SP-(#Z + 1) * 8]!, önceden dizinli fark > =-256) konumundaki reg x (19 + #X) kaydetme |
|`save_lrpair`|         1101011x'xxzzzzzz: \<x (19 + 2 *#X), lr > at [SP + #Z*8], konum \< = 504 |
|`save_fregp`|        1101100x'xxzzzzzz: [SP + #Z * 8], fark \< = 504) konumundaki d (8 + #X) çiftini Kaydet |
|`save_fregp_x`|        1101101xixxzzzzzz #X: [SP-(#Z + 1) * 8]!, önceden dizinli fark > =-512 |
|`save_freg`|        1101110x'xxzzzzzz: [SP + #Z * 8] konumundaki reg d 'yi (8 + #X) Kaydet, fark \< = 504 |
|`save_freg_x`|        11011110 ' xxx Xzzzzz: [SP-(#Z + 1) * 8]!, önceden dizinli fark > =-256) konumundaki reg d (8 + #X) kaydetme |
|`alloc_l`|         11100000 ' xxxxxxxx'xxxxxxxx'xxxxxxxx: boyut ile büyük yığın ayır \< 256D (2 ^ 24 * 16) |
|`set_fp`|        11100001: set up x29: WITH: MOV x29, SP |
|`add_fp`|        11100010 ' xxxxxxxx: set up x29 with: Add x29, SP, #x * 8 |
|`nop`|            11100011: geriye doğru izleme işlemi gerekli değil. |
|`end`|            11100100: bırakma kodu sonu. Bitiş sırasında ret anlamına gelir. |
|`end_c`|        11100101: geçerli zincir kapsamındaki geri açılım kodu sonu. |
|`save_next`|        11100110: sonraki geçici olmayan tamsayı veya FP kayıt çiftini Kaydet. |
|`arithmetic(add)`|    11100111 ' 000zxxxx: (0 = x28, 1 = SP) için tanımlama bilgisi reg (z) ekleyin; LR, LR, reg (z) Ekle |
|`arithmetic(sub)`|    11100111 ' 001zxxxx: LR 'den alt tanımlama bilgisi reg (z) (0 = x28, 1 = SP); Sub LR, LR, reg (z) |
|`arithmetic(eor)`|    11100111 ' 010zxxxx: EOR LR, tanımlama bilgisi reg (z) (0 = x28, 1 = SP); EOR LR, LR, reg (z) |
|`arithmetic(rol)`|    11100111 ' 0110xxxx: tanımlama bilgisi reg (x28) ile sanal LR xip0 = neg x28; ROR, xip0 |
|`arithmetic(ror)`|    11100111 (z) tanımlama bilgisi ile ' 100zxxxx: ROR LR (0 = x28, 1 = SP); ROR, LR, reg (z) |
| |            11100111: xxxz----:----ayrılmış |
| |              11101xxx: yalnızca aşağıdaki asm yordamları için oluşturulan özel yığın durumları için ayrılmıştır |
| |              11101000: MSFT_OP_TRAP_FRAME için özel yığın |
| |              11101001: MSFT_OP_MACHINE_FRAME için özel yığın |
| |              11101010: MSFT_OP_CONTEXT için özel yığın |
| |              11101100: MSFT_OP_CLEAR_UNWOUND_TO_CALL için özel yığın |
| |              1111xxxx: ayrılmış |

Birden çok bayt kapsayan büyük değerleri olan yönergelerde, en önemli bitler önce depolanır. Yukarıdaki geriye doğru izleme kodları, kodun yalnızca ilk baytına bakarak, geriye doğru kodun bayt cinsinden toplam boyutunu bildirmek için tasarlanmıştır. Her bir açılım kodu giriş/bitiş içindeki bir yönergeye tam olarak eşlendiğine göre, giriş veya bitiş boyutunu hesaplamak için yapılması gereken tek şey, bir arama tablosu veya benzer bir cihaz kullanarak, Cor 'ın ne kadar süreyle olacağını belirlemektir. Yanıt verme Opcode.

Prolog 'da, dizin oluşturma sırasında Adres bilgisine izin verilmeyeceğini unutmayın. Tüm fark aralıkları (#Z), her bir kayıt alanı için 248 (10 Int Yazmaçları + 8 FP Yazmaçları + 8 giriş kayıtları) için yeterli olan `save_r19r20_x` hariç, STP/STR adreslemesinin kodlaması ile eşleşir.

`save_next`, INT veya FP geçici kayıt çiftinin bir kaydını izlemelidir: `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x` veya başka bir `save_next`. Sonraki kayıt çiftini, sonraki 16 baytlık yuvada "büyüme" sırasıyla kaydeder. Son Int kayıt çiftinin ilk FP kayıt çiftine başvurduğu bir `save_next` `save-next` ' dır.

Düzenli dönüş ve sıçrama yönergelerinin boyutu aynı olduğundan, tail çağrısı senaryoları için ayrılmış `end` bırakma kodu gerekmez.

`end_c`, en iyi duruma getirme amacıyla bitişik olmayan işlev parçalarını işlemek için tasarlanmıştır. Geçerli kapsamdaki geriye doğru izleme kodlarının sonunu belirten `end_c`, gerçek bir `end` ile biten başka bir geriye doğru izleme kodu serisi izlemelidir. @No__t-0 ve `end` arasındaki bırakma kodları, ana bölgedeki ("hayalet" giriş) giriş işlemlerini temsil eder.  Diğer ayrıntılar ve örnekler aşağıdaki bölümde açıklanmıştır.

### <a name="packed-unwind-data"></a>Paketlenmiş geriye doğru izleme verileri

Prologs ve epılan 'lar aşağıda açıklanan kurallı formu izleyen işlevler için, paketlenmiş geriye doğru izleme verileri kullanılabilir, bir. xdata kaydına yönelik gereksinimi tamamen ortadan kaldırır ve geriye doğru izleme verileri sağlama maliyetini önemli ölçüde azaltır. Kurallı işlemler ve epediler, özel durum işleyicisi gerektirmeyen basit bir işlevin ortak gereksinimlerini karşılamak üzere tasarlanmıştır ve kurulum ve test işlemlerini standart sırada gerçekleştirir.

Paketlenmiş geriye doğru izleme verileriyle bir. pdata kaydının biçimi şöyle görünür:

paketlenmiş geriye doğru izleme verileri(media/arm64-exception-handling-packed-unwind-data.png "içeren") ![.]pData kaydı.

Alanlar aşağıdaki gibidir:

- **Işlev başlangıç RVA** , işlevin başlangıcına ait 32 bitlik RVA 'ya sahiptir.
- **Bayrak** , yukarıda açıklandığı gibi 2 bitlik bir alandır ve aşağıdaki anlamlara sahiptir:
  - 00 = paketlenmiş bırakma verileri kullanılmıyor; kalan BITS bir. xdata kaydına işaret
  - 01 = aşağıda açıklandığı şekilde kullanılan paketlenmiş geriye doğru izleme verileri, kapsamın başlangıcında ve sonundaki tek giriş ve bitiş ile aşağıda açıklanmıştır
  - 10 = bir giriş ve bitiş olmadan kod için aşağıda açıklandığı şekilde kullanılan paketlenmiş bırakma verileri; Bu, ayrılmış işlev segmentlerini açıklamak için yararlıdır.
  - 11 = ayrılmış;
- **Işlev uzunluğu** , 5 ' i bölünen tüm işlevin uzunluğunu sağlayan 11 bitlik bir alandır. İşlev 8k değerinden büyükse, bunun yerine tam bir. xdata kaydı kullanılmalıdır.
- **Çerçeve boyutu** , bu işlev için ayrılan, 16 ' ya bölünmüş, yığın bayt sayısını gösteren 9 bitlik bir alandır. Yığın (8k-16) bayttan daha büyük olmayan işlevlerin tam. xdata kaydı kullanması gerekir. Buna yerel değişken alanı, giden parametre alanı, aranan-kaydedilmiş Int ve FP alanı ve ana parametre alanı dahildir, ancak dinamik ayırma alanı dışlanıyor.
- **CR** , işlevin bir çerçeve zinciri ve dönüş bağlantısı kurmak için ek yönergeler içerip içermediğini belirten 2 bitlik bir bayrak:
  - 00 = zincirleme olmayan işlev, \<x29, LR > çifti yığında kaydedilmez.
  - 01 = zincirleme olmayan işlev, \<Lr > yığına kaydedilir
  - 10 = ayrılmış;
  - 11 = zincirleme işlevi, giriş/bitiş \<x29, LR > için bir mağaza/yük çifti yönergesi kullanılır
- **H** işlevi, işlevin tamsayı parametresini (x0-x7), işlevin çok başlangıcında depolayarak saklamadığını belirten 1 bitlik bir bayrak. (0 = ana kayıt kayıtları, 1 = ev kayıtları).
- **Regi** , kurallı yığın konumunda kaydedilmiş, GEÇICI olmayan Int yazmaçların (x19-x28) sayısını gösteren 4 bitlik bir alandır.
- **Regf** , kurallı yığın konumunda kaydedilen, GEÇICI olmayan FP saklayıcıları (D8-D15) sayısını gösteren 3 bitlik bir alandır. (RegF = 0: hiçbir FP kaydı kaydedilmez; RegF > 0: RegF + 1 FP Yazmaçları kaydedilir). Paketlenmiş bırakma verileri yalnızca bir FP kaydını kaydeden işlev için kullanılamaz.

Yukarıdaki bölümde 1, 2 (giden parametre alanı olmadan), 3 ve 4 kategorilerine giren kurallı prologs paketlenmiş bırakma biçimiyle temsil edilebilir.  Kurallı işlevler için epıg 'ler çok benzer bir biçimde, **H** 'nin hiçbir etkisi olmadığından, `set_fp` yönergesi atlanmaz ve adımların sırası ve her adımın yönergeleri de bitiş olarak tersine çevrilir. Paketlenmiş XData algoritması aşağıdaki tabloda açıklandığı gibi adımları izler:

0\. Adım: her bir alanın boyutunun ön hesaplamasını gerçekleştirin.

1\. Adım: tamsayı olarak kaydedilen kayıtları kaydetme.

2\. Adım: Bu adım, ilk bölümlerde 4. tür için özeldir. LR, INT alanının sonuna kaydedilir.

3\. Adım: FP aranan-kayıtlı Yazmaçları kaydetme.

4\. Adım: giriş bağımsız değişkenlerini giriş parametre alanına kaydedin.

5\. Adım: yerel alan, \<x29, LR > Pair ve giden parametre alanı dahil olmak üzere kalan yığını ayır. 5A kurallı tür 1 ' e karşılık gelir. 5B ve 5c kurallı tür 2 içindir. 5D ve 5e her iki tür 3 ve tür 4 içindir.

Indan #|Bayrak değerleri|yönerge sayısı|Ml|Bırakma kodu
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1|0 < **Regi** < = 10|RegI/2 + **Regi** % 2|`stp x19,x20,[sp,#savsz]!`<br/>`stp x21,x22,[sp,#16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**= = 01 *|1|`str lr,[sp,#(intsz-8)]`\*|`save_reg`
3|0 < **regf** < = 7|(RegF + 1)/2 +<br/>(RegF + 1)% 2)|`stp d8,d9,[sp,#intsz]`\*\*<br/>`stp d10,d11,[sp,#(intsz+16)]`<br/>`...`<br/>`str d(8+RegF),[sp,#(intsz+fpsz-8)]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** = = 1|4|`stp x0,x1,[sp,#(intsz+fpsz)]`<br/>`stp x2,x3,[sp,#(intsz+fpsz+16)]`<br/>`stp x4,x5,[sp,#(intsz+fpsz+32)]`<br/>`stp x6,x7,[sp,#(intsz+fpsz+48)]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5A|**CR** = = 11 & & #locsz<br/> < = 512|2|`stp x29,lr,[sp,#-locsz]!`<br/>`mov x29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5B|**CR** = = 11 & &<br/>512 < #locsz < = 4080|3|`sub sp,sp,#locsz`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5 c|**CR** = = 11 & & #locsz > 4080|4|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
'de|(**CR** = = 00 \| @ no__t-2 **CR**= = 01) & &<br/>#locsz < = 4080|1|`sub sp,sp,#locsz`|`alloc_s`/`alloc_m`
5E|(**CR** = = 00 \| @ no__t-2 **CR**= = 01) & &<br/>#locsz > 4080|2|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\* **CR** = = 01 ve **Regi** tek bir sayı ise, adım 2 ve son save_rep adım 1 ' de bir save_regp birleştirilir.

\* @ no__t-1 IF **regı** == **CR** = = 0 ve **regf** ! = 0 ise, kayan nokta için ilk STP predecrement öğesini yapar.

\* @ no__t-1 @ no__t-2 `mov x29,sp` ' e karşılık gelen hiçbir yönerge bitiş içinde mevcuttur. Bir işlev x29 'den SP 'nin geri yüklenmesini gerektiriyorsa, paketlenmiş geriye doğru izleme verileri kullanılamaz.

### <a name="unwinding-partial-prologs-and-epilogs"></a>Kısmi progünlükleri ve epıları geri sarma

En yaygın geri sarma, durum veya çağrının, işlevin gövdesinde gerçekleştiği, giriş ve tüm epilenlerden uzakta olduğu bir durumdur. Bu durumda, geriye doğru izleme basit bir işlemdir: unwinder yalnızca, 0 dizininde başlayan geri sarma dizisindeki kodları yürütmeye başlar ve bir bitiş Opcode saptanana kadar devam eder.

Bir giriş veya bitiş yürütülürken bir özel durum ya da kesme gerçekleştiğinde, doğru bir şekilde geri dönmek daha zordur. Bu durumlarda, yığın çerçevesi yalnızca kısmen oluşturulur ve bu, el ile geri almak için tam olarak nelerin yapıldığını belirlemektir.

Örneğin, bu giriş ve bitiş sırasını alın:

```asm
0000:    stp    x29,lr,[sp,#-256]!          // save_fplr_x  256 (pre-indexed store)
0004:    stp    d8,d9,[sp,#224]             // save_fregp 0, 224
0008:    stp    x19,x20,[sp,#240]           // save_regp 0, 240
000c:    mov    x29,sp                      // set_fp
         ...
0100:    mov    sp,x29                      // set_fp
0104:    ldp    x19,x20,[sp,#240]           // save_regp 0, 240
0108:    ldp    d8,d9,[sp,224]              // save_fregp 0, 224
010c:    ldp    x29,lr,[sp],#256            // save_fplr_x  256 (post-indexed load)
0110:    ret    lr                          // end
```

Her Opcode 'ın yanında, bu işlemi açıklayan uygun bir bırakma kodu bulunur. Not edilecek ilk şey, giriş için bırakma kodlarının serisinin bitiş için bırakma kodlarının tam bir yansıtma görüntüsü olduğu (bitiş yönergesinin son yönergesini saymamasıdır). Bu, yaygın bir durumdur ve bu nedenle giriş için bırakma kodlarının, giriş sırasının yürütme siparişinden ters sırada depolanacağı varsayılır.

Bu nedenle, hem giriş hem de bitiş için ortak bir geriye doğru izleme kodları kümesiyle ayrıldık:

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

Başlangıç durumuyla başlayarak (normal sırada olduğu kadar basittir), bitiş içinde 0 uzaklığında (işlev içinde 0x100 uzaklığında başlar), hiçbir temizleme işlemi yapılmadıysa, tam geriye doğru sırayı yürütmeyi bekletireceğiz. İçinde kendimize bir yönerge bulduk (sonunda 2. uzaklığında), ilk geriye doğru izleme kodunu atlayarak geri doğru bir şekilde geri yüklenebilir. Bu durumu genelleştirerek, işlem kodları ve bırakma kodları arasında 1:1 eşleme olduğunu varsayarsak, ilk n bırakma kodunu atlayabilmemiz ve buradan yürütmeye başlayabilmemiz gerektiğini belirtebilirsiniz.

Ters bir mantığı, tersi dışında, giriş için de geçerlidir. Giriş alanındaki 0 ' dan geri doğru bir şekilde bir şey yürütmek istiyoruz. ' De bir yönerge olan 2. sapmayı kaldırırsam, geriye doğru izleme sırası bir bırakma kodu yürütmeye başlamak istiyoruz (kodların ters sırada depolandığını unutmayın). İşte, giriş bölümündeki yönerge n ' den geri doğru bir şekilde başlıyoruz, kod listesinin sonundaki n bırakma kodlarını yürütmeyi başlatdığımızda genelleştireceğiz.

Şimdi, giriş ve bitiş kodlarının tam olarak eşleşmesi her zaman değildir. Bu nedenle, geriye doğru izleme dizisinin çeşitli kod dizilerini içermesi gerekebilir. Kodların işlenme konumunu öğrenmek için aşağıdaki mantığı kullanın:

1. İşlevin gövdesinin içinden geri sarıyorsa, 0 dizininden bırakma kodlarını yürütmeye başlayıp bir "End" işlem koduna gelene kadar devam edebilirsiniz.

1. Bir bitiş içinden geriye doğru geri sarılıyorsanız başlangıç noktası olarak bitiş kapsamıyla birlikte sunulan başlangıç dizinini kullanın. Söz konusu BILGISAYARıN, başlangıçtan itibaren kaç bayt olduğunu hesaplama. Daha sonra, tüm önceden yürütülmüş yönergelerin hesaba gelene kadar bırakma kodlarını atlayarak geriye doğru izleme kodları üzerinden ilerleyin. Sonra bu noktadan başlayarak yürütün.

1. Giriş içinden geri sarılıyor ise başlangıç noktanız olarak dizin 0 ' ı kullanın. Sıradaki giriş kodunun uzunluğunu hesaplamanız ve ardından bilgisayarın, söz konusu bilgisayarın giriş sonundan itibaren kaç bayt olduğunu hesaplama. Ardından, henüz yürütülmemiş tüm yönergelerin hesaba gelene kadar bırakma kodlarını atlayarak geriye doğru izleme kodları aracılığıyla ilerleyin. Sonra bu noktadan başlayarak yürütün.

Bu kuralların bir sonucu olarak, giriş için bırakma kodlarının her zaman dizide ilk olması gerekir ve aynı zamanda gövdeden geri doğru bir şekilde geçiş yapmak için kullanılan kodlardır. Tüm bitiş kod dizileri hemen sonrasında gelmelidir.

### <a name="function-fragments"></a>İşlev parçaları

Kod iyileştirme amaçları ve diğer nedenlerle bir işlevi ayrılmış parçalara bölmek tercih edilebilir (bölge olarak da bilinir). Bu tamamlandığında, sonuçta elde edilen her işlev parçası kendi ayrı. pdata (ve muhtemelen. xdata) kaydını gerektirir.

Kendi girişi olan ayrılmış ikincil parça için, durumunda yığın ayarlamasının yapılmamamalıdır. İkincil bölgeler için gereken tüm yığın alanı, üst bölgesi (veya adlandırılmış konak bölgesi) tarafından önceden ayrılmış olmalıdır. Bu, yığın işaretçisini işlevin özgün giriş bölümünde kesin olarak tutar.

İşlev parçalarının tipik bir durumu "kod ayrımı" ve bu derleyici, bir kod bölgesini ana bilgisayar işlevinin dışına taşıyamayabilir. Kod ayrımı nedeniyle sonuçlanmış üç olağandışı durum vardır.

#### <a name="example"></a>Örnek:

- (bölge 1: başlangıç)

    ```asm
        stp     x29,lr,[sp,#-256]!      // save_fplr_x  256 (pre-indexed store)
        stp     x19,x20,[sp,#240]       // save_regp 0, 240
        mov     x29,sp                  // set_fp
        ...
    ```

- (bölge 1: bitiş)
- (bölge 3: başlangıç)

    ```asm
        ...
    ```

- (bölge 3: bitiş)
- (bölge 2: başlangıç)

    ```asm
    ...
        mov     sp,x29                  // set_fp
        ldp     x19,x20,[sp,#240]       // save_regp 0, 240
        ldp     x29,lr,[sp],#256        // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (bölge 2: bitiş)

1. Yalnızca giriş (bölge 1: tüm epıg 'ler ayrılmış bölgelerde):

   Yalnızca giriş bölümünün açıklanması gerekir. Bu, Compact. pdata biçimi ile gösterilemez. Full. xdata durumunda bu, bitiş sayısı = 0 ayarlanarak temsil edilebilir. Yukarıdaki örnekteki bölge 1 ' i inceleyin.

   Bırakma kodları: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Yalnızca epıtalar (bölge 2: giriş, ana bilgisayar bölgesinde)

   Bu bölgeye atlama zaman denetimi tarafından, tüm giriş kodlarının yürütüldüğü varsayılır. Kısmi geriye doğru izleme, normal bir işlevle aynı şekilde meydana gelebilir. Bu bölge türü Compact. pdata ile gösterilemez. Tam XData kaydında bir "hayalet" giriş, bir `end_c` ve `end` geriye doğru izleme kodu çifti tarafından çizili olarak kodlanır.  Önde gelen `end_c`, giriş boyutunun sıfır olduğunu gösterir. Tek bitiş noktalarının başlangıç dizinini `set_fp` ' a gidin.

   Bölge 2 için bırakma kodu: `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Prologs veya epıte yok (bölge 3: prologs ve tüm epılar diğer parçalardır):

   Compact. pdata biçimi, flag = 10 ayarı aracılığıyla uygulanabilir. Full. xdata kaydıyla, bitiş sayısı = 1. Bırakma kodu yukarıdaki bölge 2 ' de olanlarla aynıdır, ancak bitiş başlangıç dizini `end_c` ' a işaret eder. Bu kod bölgesinde kısmi geri bırakma hiçbir şekilde gerçekleşmeyecektir.

İşlev parçalarının daha karmaşık bir örneği olan "küçültme kaydırması", bu derleyici, işlev giriş girişi dışında bazı Çağrılı kaydedilmiş kayıtları kaydetmeyi erteleyebilir.

- (bölge 1: başlangıç)

    ```asm
        stp     x29,lr,[sp,#-256]!      // save_fplr_x  256 (pre-indexed store)
        stp     x19,x20,[sp,#240]       // save_regp 0, 240
        mov     x29,sp                  // set_fp
        ...
    ```

- (bölge 2: başlangıç)

    ```asm
        stp     x21,x22,[sp,#224]       // save_regp 2, 224
        ...
        ldp     x21,x22,[sp,#224]       // save_regp 2, 224
    ```

- (bölge 2: bitiş)

    ```asm
        ...
        mov     sp,x29                  // set_fp
        ldp     x19,x20,[sp,#240]       // save_regp 0, 240
        ldp     x29,lr,[sp],#256        // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (bölge 1: bitiş)

Bölge 1 ' in giriş bölümünde, yığın alanı önceden ayrılır. 2\. bölge, ana makinesi işlevinin dışına taşınsa bile aynı bırakma koduna sahip olacaktır.

Bölge 1: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end` ' i bitiş başlangıç dizinini her zamanki gibi `set_fp` ' e gösterir.

Bölge 2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`. Başlangıç dizin noktalarını ilk bırakma koduna `save_regp 2, 224`.

### <a name="large-functions"></a>Büyük işlevler

Parçalar,. xdata üstbilgisindeki bit alanları tarafından uygulanan 1M sınırından daha büyük işlevleri yararlanılabilir olabilir. Bunun gibi çok büyük bir işlevi açıklamak için, işlevin 1 milyon 'den küçük parçalara bölünmesinin yeterli olması gerekir. Her parça birden çok parçaya bölünemeyecek şekilde ayarlanmalıdır.

Yalnızca işlevin ilk parçası bir giriş içerecektir; diğer tüm parçalar giriş olmadan işaretlenir. Mevcut epıte 'lerin sayısına bağlı olarak, her parça sıfır veya daha fazla EPG içerebilir. Bir parçadaki her bir bitiş kapsamının, işlevin başlangıcına değil, parçanın başlangıcına göre başlangıç sapmasını belirttiğinden emin olmak için aklınızda bulundurun.

Bir parçanın giriş süresi yoksa ve Hayır ise, işlevin gövdesinin içinden geriye doğru nasıl geri alınacağını betimleyen kendi. pdata (ve muhtemelen. xdata) kaydını da gerektirir.

## <a name="examples"></a>Örnekler

### <a name="example-1-frame-chained-compact-form"></a>Örnek 1: çerçeve zincirleme, Compact form

```asm
|Foo|     PROC
|$LN19|
    str     x19,[sp,#-0x10]!        // save_reg_x
    sub     sp,sp,#0x810            // alloc_m
    stp     fp,lr,[sp]              // save_fplr
    mov     fp,sp                   // set_fp
                                    //  end of prolog
    ...

|$pdata$Foo|
    DCD     imagerel     |$LN19|
    DCD     0x416101ed
    ;Flags[SingleProEpi] functionLength[492] RegF[0] RegI[1] H[0] frameChainReturn[Chained] frameSize[2080]
```

### <a name="example-2-frame-chained-full-form-with-mirror-prolog--epilog"></a>Örnek 2: çerçeve Zincirli, tam biçimli & bitiş girişi

```asm
|Bar|     PROC
|$LN19|
    stp     x19,x20,[sp,#-0x10]!    // save_regp_x
    stp     fp,lr,[sp,#-0x90]!      // save_fplr_x
    mov     fp,sp                   // set_fp
                                    // end of prolog
    ...
                                    // begin of epilog, a mirror sequence of Prolog
    mov     sp,fp
    ldp     fp,lr,[sp],#0x90
    ldp     x19,x20,[sp],#0x10
    ret     lr

|$pdata$Bar|
    DCD     imagerel     |$LN19|
    DCD     imagerel     |$unwind$cse2|
|$unwind$Bar|
    DCD     0x1040003d
    DCD     0x1000038
    DCD     0xe42291e1
    DCD     0xe42291e1
    ;Code Words[2], Epilog Count[1], E[0], X[0], Function Length[6660]
    ;Epilog Start Index[0], Epilog Start Offset[56]
    ;set_fp
    ;save_fplr_x
    ;save_r19r20_x
    ;end
```

EpilogStart dizini [0], giriş geri bırakma kodu dizisinin aynısını işaret ettiğini unutmayın.

### <a name="example-3-variadic-unchained-function"></a>Örnek 3: değişken bağımsız değişken olmayan bir Işlev

```asm
|Delegate| PROC
|$LN4|
    sub     sp,sp,#0x50
    stp     x19,lr,[sp]
    stp     x0,x1,[sp,#0x10]        // save incoming register to home area
    stp     x2,x3,[sp,#0x20]        // ...
    stp     x4,x5,[sp,#0x30]
    stp     x6,x7,[sp,#0x40]        // end of prolog
    ...
    ldp     x19,lr,[sp]             // beginning of epilog
    add     sp,sp,#0x50
    ret     lr

    AREA    |.pdata|, PDATA
|$pdata$Delegate|
    DCD     imagerel |$LN4|
    DCD     imagerel |$unwind$Delegate|

    AREA    |.xdata|, DATA
|$unwind$Delegate|
    DCD     0x18400012
    DCD     0x200000f
    DCD     0xe3e3e3e3
    DCD     0xe40500d6
    DCD     0xe40500d6
    ;Code Words[3], Epilog Count[1], E[0], X[0], Function Length[18]
    ;Epilog Start Index[4], Epilog Start Offset[15]
    ;nop        // nop for saving in home area
    ;nop        // ditto
    ;nop        // ditto
    ;nop        // ditto
    ;save_lrpair
    ;alloc_s
    ;end
```

Note: Epılogstart dizini [4], giriş geri bırakma kodunun ortasına işaret eder (geriye doğru izleme dizisinin boyutunu kısmen kullanın).

## <a name="see-also"></a>Ayrıca bkz.

[ARM64 ABı kurallarına genel bakış](arm64-windows-abi-conventions.md)<br/>
[ARM özel durum Işleme](arm-exception-handling.md)
