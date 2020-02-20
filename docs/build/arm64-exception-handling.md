---
title: ARM64 özel durum işleme
description: ARM64 üzerinde Windows tarafından kullanılan özel durum işleme kurallarını ve verileri açıklar.
ms.date: 11/19/2018
ms.openlocfilehash: 2304c04c5e9be31299e30bb48771f7c9777d1cd5
ms.sourcegitcommit: b9aaaebe6e7dc5a18fe26f73cc7cf5fce09262c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504488"
---
# <a name="arm64-exception-handling"></a>ARM64 özel durum işleme

Windows ARM64 on, zaman uyumsuz donanım tarafından oluşturulan özel durumlar ve zaman uyumlu yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme mekanizmasını kullanır. Dile özgü özel durum işleyicileri dil Yardımcısı işlevleri kullanılarak Windows yapılandırılmış özel durum işlemenin üzerine kurulmuştur. Bu belge, ARM64 üzerinde Windows 'da özel durum işlemeyi ve Microsoft ARM Assembler ve MSVC derleyicisi tarafından oluşturulan kod tarafından kullanılan dil yardımcılarını açıklar.

## <a name="goals-and-motivation"></a>Hedefler ve mosyon

Özel durum, verileri geriye doğru izleme ve bu açıklamanın amacı:

1. Her durumda kod yoklama olmadan geri sarma sağlamak için yeterli açıklama sağlayın.

   - Kodun çözümlenmesi için kodun içinde disk belleği olması gerekir. Bu, yararlı olduğu bazı durumlarda (izleme, örnekleme, hata ayıklama) geriye doğru izlemeyi önler.

   - Kodun çözümlenmesi karmaşıktır; Derleyici yalnızca unwinder 'in çözebildiği yönergeler oluşturmak için dikkatli olmalıdır.

   - Geriye doğru izleme geri sarma kodlarının kullanımı ile tam olarak açıklanmıyorsa, bazı durumlarda yönerge kod çözmede geri dönemelidir. Bu, genel karmaşıklığı artırır ve ideal olarak kaçınılmalıdır.

1. Orta-giriş ve orta/bitiş sürümünde geriye doğru izlemeyi destekler.

   - Geri sarma, Windows 'da özel durum işleme için kullanılır. Bir giriş veya bitiş kodu sırasının ortasında bile kodun doğru şekilde geri doğru bir şekilde geri yüklenebilmeidir.

1. En az miktarda alan alın.

   - İkili boyutu önemli ölçüde arttırabileceğiniz bırakma kodlarının toplamı olmamalıdır.

   - Geriye doğru izleme kodları bellekte kilitlenmiş olduğundan küçük bir kaplama, yüklenen her ikili için en az ek yük sağlar.

## <a name="assumptions"></a>Varsayımlar

Bu varsayımlar özel durum işleme açıklamasında yapılır:

1. Prologs ve epıte 'ler birbirini yansıtmaya eğilimlidir. Bu ortak nitelik avantajlarından yararlanarak, geriye doğru izlemeyi anlatmak için gereken meta verilerin boyutu büyük ölçüde azaltılabilir. İşlevin gövdesinde, giriş işlemlerinin geri alınmadığına veya bitiş işlemlerinin ileri bir şekilde yapıldığından bağımsız değildir. Her ikisi de özdeş sonuçlar üretmelidir.

1. İşlevler görece küçük olacak şekilde tamamen eğilimlidir. Alan için birkaç iyileştirme, verilerin en verimli şekilde paketlenmesi için bu olguyu kullanır.

1. Epıte 'ler içinde hiç koşullu kod yok.

1. Adanmış çerçeve işaretçisi kaydı: SP, giriş bölümünde başka bir Register (x29) olarak kaydedilirse, bu kayıt işlevin tamamında dokunulmadan kalır. Özgün SP 'nin herhangi bir zamanda kurtarılabileceği anlamına gelir.

1. SP başka bir kayda kaydedilmediği takdirde, yığın işaretçisinin tüm düzenlemesi tamamen giriş ve bitiş içinde gerçekleşir.

1. Yığın çerçeve düzeni, sonraki bölümde açıklandığı gibi düzenlenmiştir.

## <a name="arm64-stack-frame-layout"></a>ARM64 Stack çerçeve düzeni

![yığın çerçevesi düzeni](media/arm64-exception-handling-stack-frame.png "yığın çerçevesi düzeni")

Çerçeve zincirleme işlevleri için, fp ve LR çifti, iyileştirme konularına bağlı olarak yerel değişken alanındaki herhangi bir konuma kaydedilebilir. Amaç, çerçeve işaretçisi (x29) veya yığın işaretçisi (SP) temelinde tek bir yönerge tarafından erişilebilecek yerellerin sayısını en üst düzeye çıkarmaktır. Ancak, `alloca` işlevleri için zincirleme olması gerekir ve x29 yığının alt kısmına işaret etmelidir. Daha iyi yazmaç-çift adresleme modu kapsamına izin vermek için, kalıcı kayıt kaydetme alanlarına yerel alan yığınının en üstünde konumlandırılmış. Aşağıda, en verimli giriş dizilerinin birkaçını gösteren örnekler verilmiştir. Netlik ve daha iyi önbellek konumu için, tüm kurallı progünlüklerde çağrılan kayıtlı yazmaçların depolanması sırası "büyümekte" sırada. Aşağıdaki `#framesz` tüm yığının boyutunu temsil eder (alloca alanı hariç). `#localsz` ve `#outsz`, sırasıyla yerel alan boyutunu (\<x29, LR > çiftinin kaydetme alanı dahil) ve giden parametre boyutunu gösterir.

1. Zincirleme, #localsz \<= 512

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

   Tüm Yereller SP 'ye göre erişilir. \<x29, LR > Önceki çerçeveye işaret eder. Çerçeve boyutu için \<= 512, "sub SP,..." Regs kaydedilmiş alanı yığının altına taşınırsa en iyi duruma getirilebilir. Altkenar, yukarıdaki diğer düzenlerle tutarlı değildir ve çift Regs ve dizin oluşturma öncesi ve dizinli konum adresleme modu için kaydedilen Regs aralığın bir parçasını alır.

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

   \*, ön dizinli bir reg-LR STP, bırakma kodlarıyla temsil edilemediğinden, reg save alanının ayrılması STP 'ye katlanmıyor.

   Tüm Yereller SP 'ye göre erişilir. \<x29 > Önceki çerçeveye işaret eder.

1. Zincirleme, #framesz \<= 512, #outsz = 0

    ```asm
        stp    x29,lr,[sp,#-framesz]!       // pre-indexed, save <x29,lr>
        mov    x29,sp                       // x29 points to bottom of stack
        stp    x19,x20,[sp,#(framesz-32)]   // save INT pair
        stp    d8,d9,[sp,#(framesz-16)]     // save FP pair
    ```

   Yukarıdaki ilk giriş örneğine kıyasla, buradaki avantaj, tüm Register kaydetme yönergelerinin yalnızca bir yığın ayırma yönergesinden sonra yürütülmeye hazır olmasını sağlar. Yani, yönerge düzeyi paralelliği önleyen, SP üzerinde hiçbir koruma bağımlılığı yoktur.

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

. Pdata kayıtları, bir PE ikilisindeki yığın işleme işlevinin her birini tanımlayan sabit uzunluklu öğelerin sıralı dizisidir. "Yığın işleme" ifadesi önemlidir: herhangi bir yerel depolama gerektirmeyen ve geçici olmayan kayıtları kaydetme/geri yükleme gerektirmeyen yaprak işlevleri,. pdata kaydına gerek yoktur. Alan kazanmak için bu kayıtlar açıkça atlanmalıdır. Bu işlevlerden birinden geriye doğru dönme, return adresini doğrudan LR 'den çağırana kadar hareket ettirmek için alabilir.

ARM64 için her. pdata kaydının uzunluğu 8 bayttır. Her kaydın genel biçimi, işlevin 32-bit RVA 'Sı ilk sözcüğe başlar, ardından değişken uzunluklu bir. xdata bloğunun işaretçisini içeren ikinci bir kelime veya kurallı bir işlev geri sarma sırasını açıklayan paketlenmiş bir sözcük gelir.

![. pdata kayıt düzeni](media/arm64-exception-handling-pdata-record.png ". pdata kayıt düzeni")

Alanlar aşağıdaki gibidir:

- **Işlev başlangıç RVA** , işlevin başlangıcına ait 32 bitlik RVA 'ya sahiptir.

- **Bayrak** , ikinci. pdata sözcüğünün kalan 30 bitini nasıl yorumlayacağını belirten 2 bitlik bir alandır. **Bayrak** 0 ise, kalan bit bir **özel durum bilgisi RVA** (en düşük bit olarak 0) oluşturur. **Bayrak** sıfır olmayan bir değer ise, kalan bitler **paketlenmiş bir geriye doğru izleme veri** yapısı oluşturur.

- **Özel durum BILGISI RVA** ,. xdata bölümünde depolanan değişken uzunluklu özel durum bilgisi yapısının adresidir. Bu veriler 4 bayt hizalı olmalıdır.

- **Paketlenmiş geriye doğru Izleme verileri** , bir işlevden geri dönmek için gereken işlemlerin sıkıştırılmış bir açıklamasıdır; kurallı bir form kabul edilir. Bu durumda, hiçbir. xdata kaydı gerekli değildir.

### <a name="xdata-records"></a>. xdata kayıtları

Paketlenmiş bırakma biçimi, bir işlevin geri sarılini anlatmak için yetersizse, değişken uzunluklu bir. xdata kaydı oluşturulmalıdır. Bu kaydın adresi. pdata kaydının ikinci sözcüğündeki saklanır. . Xdata biçimi, paketlenmiş değişken uzunlukta bir sözcük kümesidir:

![. xdata kayıt düzeni](media/arm64-exception-handling-xdata-record.png ". xdata kayıt düzeni")

Bu veriler dört bölümden ayrılır:

1. Yapının genel boyutunu açıklayan ve anahtar işlev verileri sağlayan 1 veya 2 sözcüklü bir üst bilgi. İkinci sözcük yalnızca, hem **bitiş sayısı** hem de **kod sözcükleri** alanları 0 olarak ayarlandığında bulunur. Başlıkta bu bit alanları vardır:

   a. **Işlev uzunluğu** 18 bitlik bir alandır. İşlevin toplam uzunluğunu bayt cinsinden belirtir ve 4 ' ü bölünür. Bir işlev 1M değerinden büyükse, işlevi anlatmak için birden çok. pdata ve. xdata kaydı kullanılmalıdır. Daha fazla bilgi için, [büyük işlevler](#large-functions) bölümüne bakın.

   b. Sunucular 2 bitlik bir alandır. Kalan. xdata 'ın sürümünü açıklar. Şu anda yalnızca sürüm 0 tanımlanmıştır, bu nedenle 1-3 değerlerine izin verilmez.

   c. **X** , 1 bitlik bir alandır. Özel durum verilerinin varlığını (1) veya devamsızlığını (0) gösterir.

   d. **E** , 1 bitlik bir alandır. Tek bir bir bitiş tanımlayan bilgilerin, daha sonra ek kapsam sözcükleri gerektirmek yerine üstbilgiye (1) paketlendiğini gösterir (0).

   e. **Bitiş sayısı** , **E** bit durumuna bağlı olarak iki anlamı olan 5 bitlik bir alandır:

      1. **E** 0 ise, Bölüm 2 ' de açıklanan toplam bitiş kapsamı sayısının sayısını belirtir. İşlevde 31 ' den fazla kapsam varsa, bir uzantı sözcüğünün gerekli olduğunu göstermek için **kod kelimeleri** alanının 0 olarak ayarlanması gerekir.

      2. **E** 1 ise, bu alan ilk bırakma kodunun dizinini ve yalnızca bir bitiş olduğunu tanımlar.

   f. **Kod sözcükleri** , Bölüm 3 ' teki tüm bırakma kodlarını içermesi gereken 32 bitlik sözcüklerin sayısını belirten 5 bitlik bir alandır. 31 ' den fazla sözcük gerekliyse (yani, 124 ' den fazla bırakma kodu baytı varsa), bir uzantı sözcüğünün gerekli olduğunu göstermek için bu alan 0 olmalıdır.

   g. **Genişletilmiş bitiş sayısı** ve **genişletilmiş kod kelimeleri** sırasıyla 16 bit ve 8 bit alanlardır. Bu kişiler, alışılmadık çok sayıda epıya ya da çok sayıda bırakma kodu sözcüklerini kodlamak için daha fazla alan sağlar. Bu alanları içeren uzantı sözcüğü yalnızca ilk üstbilgi sözcükündeki **bitiş sayısı** ve **kod sözcükleri** alanları 0 olduğunda mevcuttur.

1. Bu **sayı** sıfır değilse, bir sözcüğe paketlenmiş bir bir sözcüğe kadar olan, üst bilgi ve isteğe bağlı genişletilmiş üst bilgiden sonra gelen bir bilgi listesi. Bunlar, başlangıç kaydırmasının artırılması sırasında depolanır. Her kapsam aşağıdaki bitleri içerir:

   a. **Bitiş başlangıç boşluğu** , işlevin başlangıcına göre, bayt cinsinden uzaklığa, 4 ' e bölünen bir 18 bit alandır.

   b. **Res** , gelecekteki genişlemeye ayrılmış 4 bitlik bir alandır. Değeri 0 olmalıdır.

   c. **Bitiş başlangıç dizini** 10 bit alandır ( **genişletilmiş kod sözcüklerinden**daha fazla bit). Bu, bu bitiş kodunu açıklayan ilk bırakma kodunun bayt dizinini gösterir.

1. Bitiş kapsamları listesi sonrasında, sonraki bölümde ayrıntılı olarak açıklanan geriye doğru izleme kodları içeren bir bayt dizisi gelir. Bu dizi, sonda en yakın tam sözcük sınırına doldurulur. Geriye doğru izleme kodları bu diziye yazılır. Bunlar, işlevin gövdesine en yakın bir ile başlar ve işlevin kenarlarına doğru hareket ederler. Her bir açılım kodu için baytlar büyük endian düzeninde depolanır, bu sayede, işlemi ve kodun geri kalanının uzunluğunu tanımlayan en önemli bayttan başlayarak doğrudan getirilebilirler.

1. Son olarak, geri bırakma kodu baytından sonra, üstbilgideki **X** biti 1 olarak ayarlandıysa, özel durum işleyicisi bilgilerini verir. Özel durum işleyicisinin kendi adresini sağlayan tek bir **özel durum işleyici RVA 'sı** içerir. Bundan sonra, özel durum işleyicisi için gereken değişken uzunlukta veri miktarı tarafından hemen izlenir.

. Xdata kaydı, ilk 8 baytı getirmek için tasarlanmıştır ve bu verileri kaydın tam boyutunu hesaplamak için kullanın ve aşağıdaki değişken boyutlu özel durum verilerinin uzunluğunu eksi olarak kullanabilirsiniz. Aşağıdaki kod parçacığı, kayıt boyutunu hesaplar:

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

Giriş ve her bitiş, geriye doğru bırakma kodlarına kendi dizinine sahip olsa da tablo aralarında paylaşılır. Hepsi aynı kodları paylaştıkları için tamamen mümkün değildir (ve tamamen seyrek değildir). (Örneğin, [örnekler](#examples) bölümünde örnek 2 ' ye bakın.) Belirtilen en büyük dizin, belirli bir işlevin toplam bırakma kodu sayısını sınırlayan 255 olduğundan, derleyici yazarları bu durum için iyileştirmelidir.

### <a name="unwind-codes"></a>Bırakma kodları

Geriye doğru izleme kodları dizisi, giriş işlemlerinin tam olarak nasıl geri alınacağını tanımlayan sıraların havuzudur ve işlemler geri alınması gereken sırayla saklanır. Geriye doğru izleme kodları, bir bayt dizesi olarak kodlanmış küçük bir yönerge kümesi olarak düşünülebilir. Yürütme tamamlandığında, çağırma işlevine döndürülen adres LR kaydındaki ' dir. Ve tüm geçici olmayan Yazmaçları, işlevin çağrıldığı zaman değerlerine geri yüklenir.

Özel durumların yalnızca bir işlev gövdesinde gerçekleşmesi ve bir giriş ya da herhangi bir bitiş içinde hiç gerçekleşmemesi durumunda yalnızca tek bir sıra gereklidir. Ancak, Windows unsargı modeli kodun kısmen yürütülen bir giriş veya bitiş içinden geriye doğru bir şekilde yürütülmesini gerektirir. Bu gereksinimi karşılamak için, geriye doğru izleme kodları, giriş ve bitiş içindeki ilgili her Opcode 1:1 ' i önemli bir şekilde eşlemenizi sağlayacak biçimde dikkatle tasarlanmıştı. Bu tasarımın çeşitli etkileri vardır:

1. Bırakma kodlarının sayısını sayarak, giriş ve bitiş uzunluğunu hesaplamak mümkündür.

1. Bir bitiş kapsamının başlangıcından geçmiş yönergelerin sayısını sayarak, geriye doğru izleme kodları sayısını atlamak mümkündür. Daha sonra, bir sıranın geri kalanını yürütülebilmemiz için, bitiş tarafından gerçekleştirilen kısmen yürütülen geriye doğru bırakma işleminin tamamlanmasını sağlayabilirsiniz.

1. Giriş sonundaki yönergelerin sayısını sayarak, geriye doğru bırakma kodları sayısını atlamak mümkündür. Daha sonra, yalnızca yürütmeyi tamamlamış olan giriş parçalarını geri almak için sıranın geri kalanını yürütebiliriz.

Geriye doğru izleme kodları aşağıdaki tabloya göre kodlanır. Tüm bırakma kodları, büyük bir yığını ayıran tek bir/çift bayttır. 21 bırakma kodu tamamen vardır. Her bir açılım kodu, kısmen yürütülen prologs ve epıların geri sarılarına izin vermek için giriş/bitiş içinde tam olarak bir yönergeyi eşler.

|Bırakma kodu|BITS ve yorum|
|-|-|
|`alloc_s`|000xxxxx: \< 512 (2 ^ 5 * 16) boyutunda küçük yığın ayırın.|
|`save_r19r20_x`|    001zzzzz: \<x19, x20 > Pair `[sp-#Z*8]!`, önceden dizinli uzaklığında Kaydet > =-248 |
|`save_fplr`|        01zzzzzz: \<x29, LR > çiftini `[sp+#Z*8]`, fark \<= 504 olarak kaydedin. |
|`save_fplr_x`|        10zzzzzz: \<x29, LR > çiftinin `[sp-(#Z+1)*8]!`, önceden dizinli uzaklığında Kaydet > =-512 |
|`alloc_m`|        11000xxx'xxxxxxxx: boyut \< 16k ile büyük yığın ayırın (2 ^ 11 * 16). |
|`save_regp`|        110010xx'xxzzzzzz: x (19 + #X) çiftini `[sp+#Z*8]`, fark \<= 504 olarak kaydet |
|`save_regp_x`|        110011xx'xxzzzzzz: x çiftini Kaydet (19 + #X) `[sp-(#Z+1)*8]!`, önceden dizinli fark > =-512 |
|`save_reg`|        110100xx'xxzzzzzz: reg x 'i kaydedin (19 + #X) `[sp+#Z*8]`, fark \<= 504 |
|`save_reg_x`|        1101010x'xxxzzzzz: `[sp-(#Z+1)*8]!`, önceden dizinli uzaklığında reg x (19 + #X) kaydetme > =-256 |
|`save_lrpair`|         1101011x'xxzzzzzz: \<x (19 + 2 * #X), LR > `[sp+#Z*8]`, fark \<= 504 |
|`save_fregp`|        1101100x'xxzzzzzz: d (8 + #X) çiftini `[sp+#Z*8]`, fark \<= 504 olarak kaydet |
|`save_fregp_x`|        1101101x'xxzzzzzz: 1 çiftini kaydet d (8 + #X), `[sp-(#Z+1)*8]!`, önceden dizinli fark > =-512 |
|`save_freg`|        1101110x'xxzzzzzz: reg d 'yi (8 + #X) `[sp+#Z*8]`, fark \<= 504 |
|`save_freg_x`|        11011110 ' xxxzzzzz: `[sp-(#Z+1)*8]!`, önceden dizinli uzaklığında (8 + #X) Kaydet > =-256 |
|`alloc_l`|         11100000 ' xxxxxxxx'xxxxxxxx'xxxxxxxx: boyut ile büyük yığın ayır \< 256 milyon (2 ^ 24 * 16) |
|`set_fp`|        11100001: x29 ayarla:: `mov x29,sp` |
|`add_fp`|        11100010 ' xxxxxxxx: set up x29 with: `add x29,sp,#x*8` |
|`nop`|            11100011: geriye doğru izleme işlemi gerekli değil. |
|`end`|            11100100: bırakma kodu sonu. Bitiş sırasında ret anlamına gelir. |
|`end_c`|        11100101: geçerli zincir kapsamındaki geri açılım kodu sonu. |
|`save_next`|        11100110: sonraki geçici olmayan tamsayı veya FP kayıt çiftini Kaydet. |
|`arithmetic(add)`|    11100111 ' 000zxxxx: (0 = x28, 1 = SP) için tanımlama bilgisi reg (z) ekleyin; `add lr, lr, reg(z)` |
|`arithmetic(sub)`|    11100111 ' 001zxxxx: LR 'den alt tanımlama bilgisi reg (z) (0 = x28, 1 = SP); `sub lr, lr, reg(z)` |
|`arithmetic(eor)`|    11100111 ' 010zxxxx: EOR LR, tanımlama bilgisi reg (z) (0 = x28, 1 = SP); `eor lr, lr, reg(z)` |
|`arithmetic(rol)`|    11100111 ' 0110xxxx: tanımlama bilgisi reg (x28) ile sanal LR xip0 = neg x28; `ror lr, xip0` |
|`arithmetic(ror)`|    11100111 (z) tanımlama bilgisi ile ' 100zxxxx: ROR LR (0 = x28, 1 = SP); `ror lr, lr, reg(z)` |
| |            11100111: xxxz----:----ayrılmış |
| |              11101xxx: yalnızca aşağıdaki asm yordamları için oluşturulan özel yığın durumları için ayrılmıştır |
| |              11101000: MSFT_OP_TRAP_FRAME için özel yığın |
| |              11101001: MSFT_OP_MACHINE_FRAME için özel yığın |
| |              11101010: MSFT_OP_CONTEXT için özel yığın |
| |              11101100: MSFT_OP_CLEAR_UNWOUND_TO_CALL için özel yığın |
| |              1111xxxx: ayrılmış |

Birden çok bayt kapsayan büyük değerleri olan yönergelerde, en önemli bitler önce depolanır. Bu tasarım, kodun yalnızca ilk baytını arayarak, toplam boyutunu geriye doğru izleme kodunun bayt cinsinden bulmayı mümkün kılar. Her bir açılım kodu, giriş veya bitiş içindeki bir yönergeyle tam olarak eşlendiğinden, giriş veya bitiş boyutunu hesaplamanız gerekir. Sıra başından sonuna kadar ileredebilir ve ilgili Opcode 'ın ne kadar süreyle olduğunu anlamak için bir arama tablosu veya benzer bir cihaz kullanabilirsiniz.

Giriş sonrasında dizin oluşturma sırasında adresleme kullanılamaz. Tüm fark aralıkları (#Z), `save_r19r20_x`dışındaki STP/STR adreslemesinin kodlamasıyla eşleşir, burada 248, tüm kaydetme alanlarında yeterlidir (10 Int Yazmaçları + 8 FP Yazmaçları + 8 giriş kayıtları).

`save_next`, INT veya FP geçici kayıt çiftinin bir kaydını izlemelidir: `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x`veya başka bir `save_next`. Sonraki kayıt çiftini, sonraki 16 baytlık yuvada "büyüme" sırasıyla kaydeder. `save_next`, son Int kayıt çiftini gösteren `save-next` izleyen ilk FP kayıt çiftine başvurur.

Düzenli dönüş ve geçiş yönergelerinin boyutu aynı olduğundan, tail çağrı senaryoları için ayrılmış bir `end` bırakma kodu gerekmez.

`end_c`, en iyi duruma getirme amacıyla bitişik olmayan işlev parçalarını işlemek için tasarlanmıştır. Geçerli kapsamdaki geriye doğru izleme kodlarının sonunu belirten `end_c`, gerçek bir `end`biten başka bir geriye doğru izleme kodu serisi gelmelidir. `end_c` ve `end` arasındaki bırakma kodları, ana bölgedeki ("hayalet" giriş) giriş işlemlerini temsil eder.  Diğer ayrıntılar ve örnekler aşağıdaki bölümde açıklanmıştır.

### <a name="packed-unwind-data"></a>Paketlenmiş geriye doğru izleme verileri

Prologs ve epıtalar işlevleri aşağıda açıklanan kurallı formu izleyen işlevler için, paketlenmiş geriye doğru izleme verileri kullanılabilir. . Xdata kaydına yönelik gereksinimi tamamen ortadan kaldırır ve geriye doğru izleme verileri sağlama maliyetini önemli ölçüde azaltır. Kurallı işlem günlükleri ve epediler, basit bir işlevin ortak gereksinimlerini karşılayacak şekilde tasarlanmıştır: bir özel durum işleyicisi gerektirmeyen ve kurulum ve kaldırma işlemlerini standart sırada yapan bir.

Paketlenmiş geriye doğru izleme verileriyle bir. pdata kaydının biçimi şöyle görünür:

![paketlenmiş geriye doğru izleme verileriyle. pdata kaydı](media/arm64-exception-handling-packed-unwind-data.png "paketlenmiş geriye doğru izleme verileriyle. pdata kaydı")

Alanlar aşağıdaki gibidir:

- **Işlev başlangıç RVA** , işlevin başlangıcına ait 32 bitlik RVA 'ya sahiptir.
- **Bayrak** , yukarıda açıklandığı gibi 2 bitlik bir alandır ve aşağıdaki anlamlara sahiptir:
  - 00 = paketlenmiş bırakma verileri kullanılmıyor; kalan BITS bir. xdata kaydına işaret
  - 01 = tek bir giriş ile kullanılan ve kapsamın başındaki ve sonundaki bitiş ile kullanılan paketlenmiş geri bırakma verileri
  - 10 = bir giriş ve bitiş olmadan kod için kullanılan paketlenmiş bırakma verileri. Ayrılmış işlev segmentlerini açıklamak için yararlıdır
  - 11 = ayrılmış.
- **Işlev uzunluğu** , 5 ' i bölünen tüm işlevin uzunluğunu sağlayan 11 bitlik bir alandır. İşlev 8k değerinden büyükse, bunun yerine tam bir. xdata kaydı kullanılmalıdır.
- **Çerçeve boyutu** , bu işlev için ayrılan, 16 ' ya bölünmüş, yığın bayt sayısını gösteren 9 bitlik bir alandır. Yığın (8k-16) bayttan daha büyük olmayan işlevlerin tam. xdata kaydı kullanması gerekir. Yerel değişken alanı, giden parametre alanı, aranan-kaydedilmiş Int ve FP alanı ve ana parametre alanı dahil, ancak dinamik ayırma alanını dışlar.
- **CR** , işlevin bir çerçeve zinciri ve dönüş bağlantısı kurmak için ek yönergeler içerip içermediğini belirten 2 bitlik bir bayrak:
  - 00 = zincirleme olmayan işlev, \<x29, LR > çifti yığında kaydedilmez.
  - 01 = zincirleme olmayan işlev, \<LR > yığına kaydedilir
  - 10 = ayrılmış;
  - 11 = zincirleme işlevi, giriş/bitiş \<x29, LR > için bir mağaza/yük çifti yönergesi kullanılır
- **H** işlevi, işlevin tamsayı parametresini (x0-x7), işlevin çok başlangıcında depolayarak saklamadığını belirten 1 bitlik bir bayrak. (0 = ana kayıt kayıtları, 1 = ev kayıtları).
- **Regi** , kurallı yığın konumunda kaydedilmiş, GEÇICI olmayan Int yazmaçların (x19-x28) sayısını gösteren 4 bitlik bir alandır.
- **Regf** , kurallı yığın konumunda kaydedilen, GEÇICI olmayan FP saklayıcıları (D8-D15) sayısını gösteren 3 bitlik bir alandır. (RegF = 0: hiçbir FP kaydı kaydedilmez; RegF > 0: RegF + 1 FP Yazmaçları kaydedilir). Paketlenmiş geriye doğru izleme verileri yalnızca bir FP kaydını kaydeden işlev için kullanılamaz.

Yukarıdaki bölümde 1, 2 (giden parametre alanı olmadan), 3 ve 4 kategorilerine giren kurallı prologs paketlenmiş bırakma biçimiyle temsil edilebilir.  Kurallı işlevler için epıg 'ler benzer bir biçimde, **H** 'nin herhangi bir etkisi olmaması, `set_fp` yönergesinin Atlanmasının ve adımların sırası ile her adımdaki yönergelerin ters çevrilme işlemi. Paketlenmiş. xdata için algoritma aşağıdaki tabloda açıklandığı gibi adımları izler:

0\. Adım: her alanın boyutunun ön işlemi.

1\. Adım: tamsayı olarak kaydedilen kayıtları kaydetme.

2\. Adım: Bu adım, ilk bölümlerde 4. tür için özeldir. LR, INT alanının sonuna kaydedilir.

3\. Adım: FP aranan-kayıtlı Yazmaçları kaydetme.

4\. Adım: giriş bağımsız değişkenlerini giriş parametre alanına kaydedin.

5\. Adım: yerel alan, \<x29, LR > Pair ve giden parametre alanı dahil olmak üzere kalan yığını ayır. 5A kurallı tür 1 ' e karşılık gelir. 5B ve 5c kurallı tür 2 içindir. 5D ve 5e her iki tür 3 ve tür 4 içindir.

Indan #|Bayrak değerleri|yönerge sayısı|Ml|Bırakma kodu
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1|0 < **Regi** < = 10|RegI/2 + **Regi** %2|`stp x19,x20,[sp,#savsz]!`<br/>`stp x21,x22,[sp,#16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**= = 01 *|1|`str lr,[sp,#(intsz-8)]`\*|`save_reg`
3|0 < **regf** < = 7|(RegF + 1)/2 +<br/>(RegF + 1) %2)|`stp d8,d9,[sp,#intsz]`\*\*<br/>`stp d10,d11,[sp,#(intsz+16)]`<br/>`...`<br/>`str d(8+RegF),[sp,#(intsz+fpsz-8)]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** = = 1|4|`stp x0,x1,[sp,#(intsz+fpsz)]`<br/>`stp x2,x3,[sp,#(intsz+fpsz+16)]`<br/>`stp x4,x5,[sp,#(intsz+fpsz+32)]`<br/>`stp x6,x7,[sp,#(intsz+fpsz+48)]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5A|**CR** = = 11 & & #locsz<br/> < = 512|2|`stp x29,lr,[sp,#-locsz]!`<br/>`mov x29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5B|**CR** = = 11 & &<br/>512 < #locsz < = 4080|3|`sub sp,sp,#locsz`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5 c|**CR** = = 11 & & #locsz > 4080|4|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
'de|(**CR** = = 00 \|\| **CR**= = 01) & &<br/>#locsz < = 4080|1|`sub sp,sp,#locsz`|`alloc_s`/`alloc_m`
5E|(**CR** = = 00 \|\| **CR**= = 01) & &<br/>#locsz > 4080|2|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\*, **CR** = = 01 ve **Regi** tek bir sayı ise, adım 2 ve son save_rep 1. adım tek bir save_regp birleştirilir.

**Regi** == **CR** = = 0 ve **regf** ! = 0 ise, kayan nokta için ilk stp predecrement öğesini yapar. \* \*

\*\*\* bitiş içinde `mov x29,sp` karşılık gelen hiçbir yönerge yok. Bir işlev x29 'den SP 'nin geri yüklenmesini gerektiriyorsa, paketlenmiş geriye doğru izleme verileri kullanılamaz.

### <a name="unwinding-partial-prologs-and-epilogs"></a>Kısmi progünlükleri ve epıları geri sarma

En yaygın geri sarma, durum veya çağrının, işlevin gövdesinde gerçekleştiği, giriş ve tüm epilenlerden uzakta olduğu bir durumdur. Bu durumda, geriye doğru izleme basit bir işlemdir: unwinder yalnızca, 0 dizininde başlayan geri sarma dizisindeki kodları yürütmeye başlar ve bir bitiş Opcode saptanana kadar devam eder.

Bir giriş veya bitiş yürütülürken bir özel durum ya da kesme gerçekleştiğinde, doğru bir şekilde geri dönmek daha zordur. Bu durumlarda, yığın çerçevesi yalnızca kısmen oluşturulur. Bu sorun, tam olarak geri alınması için ne yapılması gerektiğini belirlemektir.

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

Her Opcode 'ın yanında, bu işlemi açıklayan uygun bir bırakma kodu bulunur. Giriş için bırakma kodlarının serisinin, bitiş için bırakma kodlarının tam bir yansıtma görüntüsü olduğunu görebilirsiniz (bitiş yönergesinin son yönergesini saymaz). Bu, yaygın bir durumdur ve neden her zaman giriş için bırakma kodlarının, giriş sırasının yürütme siparişinden ters sırada depolandığını varsayalım.

Bu nedenle, hem giriş hem de bitiş için ortak bir geriye doğru izleme kodları kümesiyle çalışıyoruz:

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

Normal sırada olduğundan, bitiş durumu basittir. Bitiş içinde 0 uzaklığında başlayarak (işlevde 0x100 uzaklığında başlar), temizleme işlemi henüz yapılmamıştır çünkü tam geriye doğru izleme dizisinin yürütülmesi beklenir. İçinde kendimize bir yönerge bulduk (sonunda 2. uzaklığında), ilk geriye doğru izleme kodunu atlayarak geri doğru bir şekilde geri yüklenebilir. Bu durumu genelleştiriyoruz ve işlem kodları ile bırakma kodları arasında 1:1 eşleme varsayabiliyoruz. Ardından, bitiş içindeki yönerge *n* ' den geri sarıya başlamak için ilk *n* bırakma kodunu atlayabilmelidir ve buradan yürütmeye başlayacağız.

Ters bir mantığı, tersi dışında, giriş için de geçerlidir. Giriş bölümünde 0 ' dan geriye doğru izleme başladığımızda hiçbir şey yürütmek istiyoruz. ' De bir yönerge olan 2. sapmayı geriye doğru geri alıyorsa, son olarak bir geriye doğru izleme sırasını yürütmeye başlamak istiyoruz. (Kodların ters sırada depolandığını unutmayın.) Burada, genelleştiriyoruz: giriş bölümündeki yönerge n ' den geri sarım başladığımızda, kod listesinin sonundan itibaren n bırakma kodlarını yürütmeyi başlattık.

Giriş ve bitiş kodlarının tam olarak eşleşmesi her zaman değildir. Geriye doğru izleme dizisinin çeşitli kod dizilerini içermesi gerekebilir. Kodların işlenme konumunu öğrenmek için aşağıdaki mantığı kullanın:

1. İşlevin gövdesi içinden geri sarılıyor ise, dizin 0 ' da bırakma kodlarını yürütmeye başlayın ve bir "End" işlem koduna gelene kadar devam edin.

1. Bir bitiş içinden geriye doğru geri sarılıyorsanız başlangıç noktası olarak bitiş kapsamıyla birlikte sunulan başlangıç dizinini kullanın. Söz konusu BILGISAYARıN, başlangıçtan itibaren kaç bayt olduğunu hesaplama. Daha sonra, tüm önceden yürütülmüş yönergelerin hesaba gelene kadar bırakma kodlarını atlayarak geriye doğru izleme kodları üzerinden ilerleyin. Sonra bu noktadan başlayarak yürütün.

1. Giriş içinden geri sarılıyor ise başlangıç noktanız olarak dizin 0 ' ı kullanın. Sıradaki giriş kodunun uzunluğunu hesaplamanız ve ardından bilgisayarın, söz konusu bilgisayarın giriş sonundan itibaren kaç bayt olduğunu hesaplama. Ardından, henüz yürütülmemiş tüm yönergelerin hesaba gelene kadar bırakma kodlarını atlayarak geriye doğru izleme kodları aracılığıyla ilerleyin. Sonra bu noktadan başlayarak yürütün.

Bu kurallar, giriş için bırakma kodlarının her zaman dizide ilk olması gerekir. Ayrıca, gövdenin içinden geri doğru bir şekilde geçiş yapmak için kullanılan kodlardır. Tüm bitiş kod dizileri hemen sonrasında gelmelidir.

### <a name="function-fragments"></a>İşlev parçaları

Kod iyileştirme amaçları ve diğer nedenlerle bir işlevi ayrılmış parçalara bölmek tercih edilebilir (bölge olarak da bilinir). Ayırma sırasında, sonuçta elde edilen her işlev parçası kendi ayrı. pdata (ve muhtemelen. xdata) kaydını gerektirir.

Kendi giriş girişi olan her ayrılmış ikincil parça için, ara penceresinde yığın ayarlamasının yapılmamalarından biri beklenmektedir. İkincil bir bölge için gereken tüm yığın alanı, üst bölgesi (veya adı verilen konak bölgesi) tarafından önceden ayrılmış olmalıdır. Bu, yığın işaretçisini işlevin özgün giriş bölümünde kesin olarak tutar.

İşlev parçalarının tipik bir durumu "kod ayrımı" ve bu derleyici, bir kod bölgesini ana bilgisayar işlevinin dışına taşıyamayabilir. Kod ayrımı nedeniyle sonuçlanmış üç olağandışı durum vardır.

#### <a name="example"></a>Örnek

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

   Yalnızca giriş açıklanmalıdır. Bu, Compact. pdata biçiminde gösterilemez. Full. xdata durumunda, bitiş sayısı = 0 ayarlanarak temsil edilebilir. Yukarıdaki örnekteki bölge 1 ' i inceleyin.

   Bırakma kodları: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Yalnızca epıtalar (bölge 2: giriş, ana bilgisayar bölgesinde)

   Bu bölgeye atlama zaman denetimi tarafından, tüm giriş kodlarının yürütüldüğü varsayılır. Kısmi geriye doğru izleme, normal bir işlevle aynı şekilde meydana gelebilir. Bu bölge türü Compact. pdata ile gösterilemez. Full. xdata kaydında, bir "hayalet" giriş, bir `end_c` `end` ve geriye doğru bırakma kodu çifti tarafından ayraç ile kodlanabilen.  Önde gelen `end_c`, giriş boyutunun sıfır olduğunu gösterir. `set_fp`için tek bitiş noktalarının başlangıç dizini.

   Bölge 2 için bırakma kodu: `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Prologs veya epıte yok (bölge 3: prologs ve tüm epılar diğer parçalardır):

   Compact. pdata biçimi, flag = 10 ayarı aracılığıyla uygulanabilir. Full. xdata kaydıyla, bitiş sayısı = 1. Geriye doğru izleme kodu, yukarıdaki bölge 2 kodu ile aynıdır, ancak bitiş başlangıç dizini de `end_c`gösterir. Bu kod bölgesinde kısmi geri bırakma hiçbir şekilde gerçekleşmeyecektir.

İşlev parçalarının daha karmaşık bir örneği "küçültme sarmalama" dir. Derleyici, işlev giriş girişi dışında bir şekilde, bazı çağrılardan kaydedilmiş yazmaçların kaydedilmesini erteleyebilir.

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

Bölge 1 ' in giriş bölümünde, yığın alanı önceden ayrılır. 2\. bölge, ana bilgisayar işlevinin dışına taşınsa bile aynı bırakma koduna sahip olacağını görebilirsiniz.

Bölge 1: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end` bitiş başlangıç dizini noktalarıyla her zamanki gibi `set_fp`.

Bölge 2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`. Başlangıç dizin noktalarını ilk bırakma kodu `save_regp 2, 224`.

### <a name="large-functions"></a>Büyük işlevler

Parçalar,. xdata üstbilgisindeki bit alanları tarafından uygulanan 1M sınırından daha büyük işlevleri betimleyerek kullanılabilir. Bunun gibi çok büyük bir işlevi betimleyen, 1 milyon ' den küçük parçalara bölünmelidir. Her parça birden çok parçaya bölünemeyecek şekilde ayarlanmalıdır.

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

Bitiş başlangıç dizini [0], aynı giriş geri bırakma kodu dizisine işaret ediyor.

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

Bitiş başlangıç dizini [4], giriş geri bırakma kodunun ortasına işaret eder (geriye doğru yeniden kullanım dizisi).

## <a name="see-also"></a>Ayrıca bkz.

[ARM64 ABı kurallarına genel bakış](arm64-windows-abi-conventions.md)<br/>
[ARM Özel Durum İşleme](arm-exception-handling.md)
