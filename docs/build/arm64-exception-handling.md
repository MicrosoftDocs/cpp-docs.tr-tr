---
title: ARM64 özel durum işleme | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e24997fa2eb6e6e5c3d8438b137e168c2f70b1f
ms.sourcegitcommit: 9ad287c88bdccee2747832659fe50c2e5d682a0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39034744"
---
# <a name="arm64-exception-handling"></a>ARM64 özel durum işleme

ARM64 üzerinde Windows Donanım tarafından oluşturulan zaman uyumsuz özel durumları ve zaman uyumlu yazılım tarafından oluşturulan özel durumlar için aynı yapılandırılmış özel durum işleme mekanizmasını kullanır. Dile özgü özel durum işleyicileri dil yardımcı işlevleri kullanarak Windows yapılandırılmış özel durum işleme üzerinde oluşturulur. Bu belgede, özel durum işleme Windows Microsoft ARM derleyicisi ve Visual C++ Derleyici tarafından oluşturulan kodu tarafından kullanılan dil yardımcıları ve ARM64 de açıklanmaktadır.

## <a name="goals-and-motivation"></a>Hedefleri ve motivasyon

Özel durumu geriye doğru izleme verileri kuralları ve bu tanım için tasarlanmıştır:

1. Her durumda yoklama kod olmadan geriye doğru izleme izin vermek için yeterli bir açıklama sağlayın.

   - Kod çözümleme disk belleğine alınacak kod gerektirir. Bu yararlı olduğu bazı durumlarda geriye doğru izleme önler (izleme, örnekleme, hata ayıklama).

   - Kod çözümleme karmaşıktır; Derleyici yönergeleri unwinder kod çözme özellikli yalnızca oluşturmak için dikkatli olmanız gerekir.

   - Geriye doğru izleme kullanımı geriye doğru izleme kodları açıklanmaktadır olamaz, sonra bazı durumlarda, kod çözme yönerge dönmesi gerekir. Bu genel karmaşıklık artar ve ideal kaçınılması.

2. Orta Giriş geriye doğru izleme ve orta sonuç desteği.

   - Geriye doğru izleme Windows içinde birden çok özel durum işleme için kullanılan, biz gerçekleştirmek için kritik olacak şekilde, doğru bir bırakma bir giriş veya çıkış kodu dizisi sırasında bile ortasında.

3. Bir en az miktarda alan yararlanın.

   - Geriye doğru izleme kodları ikili boyutu büyük ölçüde artırmak için toplama gerekir değil.

   - Geriye doğru izleme kodları bellekte kilitlenmiş olası olduğundan, küçük ayak izine yüklenen her ikili için en az bir ek yükü sağlar.

## <a name="assumptions"></a>Varsayımlar

Özel durum işleme açıklama içinde varsayımlar şunlardır:

1. Açıklanabilmeleri ve sonuç ya da diğer yansıtma eğilimindedir. Bu ortak nitelik avantajlarından yararlanmaya göre geriye doğru izleme açıklamak için gereken meta veri boyutu büyük ölçüde azaltılabilir. İşlev gövdesi içinde giriş ait işlemler geri alınır veya bitiş'ın işlemler ileriye doğru bir şekilde gerçekleştirilir bir önemi yoktur. Her ikisi de benzer sonuçlar üretmelidir.

2. İşlevler tüm görece küçük olma eğilimindedir. Alanı için çeşitli iyileştirmeler bu verilerin en verimli paketlemeyi elde etmek için kullanır.

3. Sonuç koşullu kodu yok.

4. Ayrılmış çerçeve işaretçisi kaydı: sp giriş olarak başka bir kayıttaki (r29) kaydedilmişse, kayıt işlevi dokunulmadan kalır ve böylece özgün sp herhangi bir zamanda kurtarılabilir.

5. Sp başka bir kayıttaki kaydedilmezse tüm yığın işaretçisi işlenmesini kesinlikle giriş ve bitiş içinde gerçekleşir.

6. Yığın çerçevesi düzeni, sonraki bölümde açıklandığı gibi düzenlenir.

## <a name="arm64-stack-frame-layout"></a>ARM64 yığın çerçevesi düzeni

![yığın çerçevesi düzeni](../build/media/arm64-exception-handling-stack-frame.png "yığın çerçevesi düzeni")

Zincirleme çerçeve işlevler için yerel değişken alanı en iyi duruma getirme konuları bağlı olarak herhangi bir konumda fp ve lr çifti kaydedilebilir. Çerçeve işaretçisini (r29) veya yığın işaretçisi (sp) temel alan bir tek yönerge tarafından erişilebilen Yereller sayısı en üst düzeye çıkarmak için kullanılan hedeftir. Ancak için `alloca` İşlevler, zincirleme gerekir ve r29 yığının sonuna işaret etmelidir. Kalıcı daha iyi register çifti-adresleme-modu kapsamı için izin vermek için yerel yığın üstüne alanları konumlandırılır aave kaydedin. En verimli giriş dizilerini bazılarını gösteren örnekleri aşağıda verilmiştir. Açıklık ve daha iyi önbellek yerleşim yeri için tüm canonical açıklanabilmeleri içinde Çağrılan Kaydedilmiş Yazmaçlar depolamanın "yukarı büyüyen" sırayla sırasıdır. `#framesz` Aşağıda (alloca alanı dışında) tüm yığın boyutunu temsil eder. `#localsz` ve `#outsz` yerel boyutu belirtmek (kaydetme dahil olmak üzere alanı \<r29, lr > çifti) ve parametre boyutu sırasıyla giden.

1. Zincirleme #localsz < = 512

    ```asm
        stp    r19,r20,[sp,-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,16]            // save in FP regs (optional)
        stp    r0,r1,[sp,32]            // home params (optional)
        stp    r2,r3,[sp, 48]
        stp    r4,r5,[sp,64]
        stp    r6,r7,[sp,72]
        stp    r29, lr, [sp, -#localsz]!    // save <r29,lr> at bottom of local area
        mov    r29,sp                   // r29 points to bottom of local
        sub    sp, #outsz               // (optional for #outsz != 0)
    ```

2. Zincirleme #localsz > 512

    ```asm
        stp    r19,r20,[sp,-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,16]            // save in FP regs (optional)
        stp    r0,r1,[sp,32]            // home params (optional)
        stp    r2,r3,[sp, 48]
        stp    r4,r5,[sp,64]
        stp    r6,r7,[sp,72]
        sub    sp,#localsz+#outsz       // allocate remaining frame
        stp    r29, lr, [sp, #outsz]    // save <r29,lr> at bottom of local area
        add    r29,sp, #outsz           // setup r29 points to bottom of local area
    ```

3. Unchained, yaprak işlevleri (kaydedilmemiş lr)

    ```asm
        stp    r19,r20,[sp, -72]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp, 16]
        str    r23 [sp,32]
        stp    d8,d9,[sp,40]            // save FP regs (optional)
        stp    d10,d11,[sp,56]
        sub    sp,#framesz-72           // allocate the remaining local area
    ```

   Tüm yerel öğeler üzerinde SP'yi tabanlı erişilir \<r29, lr > Önceki çerçeveye işaret eder. Çerçeve boyutu için < = 512, "sub sp..." yığını altına kaydedilmiş regs alan taşınırsa hemen iyileştirilebilir. Olumsuz tarafı, söz konusu diğer yukarıdaki düzenleriyle tutarlı değil ve kaydedilen regs çifti regs ve öncesi ve sonrası dizinli uzaklık adresleme modu aralığının bir parçası olması ' dir.

4. (Lr kaydedilen Int alanına kaydedilir) unchained ve yaprak olmayan işlevler

    ```asm
        stp    r19,r20,[sp,-80]!        // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp,16]          // ...
        stp    r23, lr,[sp, 32]         // save last Int reg and lr
        stp    d8,d9,[sp, 48]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,64]          // ...
        sub    sp,#framesz-80           // allocate the remaining local area
    ```

   Veya, çift sayı ile kaydedilmiş Int yazmaçlar,

    ```asm
        stp    r19,r20,[sp,-72]!        // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp,16]          // ...
        str    lr,[sp, 32]              // save lr
        stp    d8,d9,[sp, 40]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,56]          // ...
        sub    sp,#framesz-72           // allocate the remaining local area
    ```

    Yalnızca kaydedilmiş r19:

    ```asm
        sub    sp, sp, #16              // reg save area allocation*
        stp    r19,lr,[sp,0]            // save r19, lr
        sub    sp,#framesz-16           // allocate the remaining local area
    ```

   \* Önceden dizinlenmiş reg lr stp geriye doğru izleme kodları ile gösterilemez çünkü alanı ayırmasını kaydetme reg stp katlanmadı.

   Tüm yerel öğeler üzerinde SP'yi tabanlı erişilir \<r29 > Önceki çerçeveye işaret eder.

5. Zincirleme #framesz < = 512, #outsz = 0

    ```asm
        stp    r29, lr, [sp, -#framesz]!    // pre-indexed, save <r29,lr>
        mov    r29,sp                       // r29 points to bottom of stack
        stp    r19,r20,[sp, #framesz -32]   // save INT pair
        stp    d8,d9,[sp, #framesz -16]     // save FP pair
    ```

   Yukarıdaki #1 giriş için karşılaştırma, avantajı tüm kayıt yönergeleri kaydetme yönerge ayırma sağa tek yığın sonra yürütülecek hazır değildir. Bu nedenle, olduğundan koruma hiçbir bağımlılığı yönerge düzeyi paralellik engelleyen sp.

6. Zincirleme, çerçeve boyutu 512 > (alloca olmayan işlevler için isteğe bağlı)

    ```asm
        stp    r29, lr, [sp, -80]!          // pre-indexed, save <r29,lr>
        stp    r19,r20,[sp,16]              // save in INT regs
        stp    r21,r22,[sp,32]              // ...
        stp    d8,d9,[sp,48]                // save in FP regs
        stp    d10,d11,[sp,64]
        mov    r29,sp                       // r29 points to top of local area
        sub    sp,#framesz-80               // allocate the remaining local area
    ```

   En iyi duruma getirme amacıyla "çifti reg" ve adresleme modu öncesi/sonrası-indexed uzaklığı için daha iyi bir tedarik sağlamak için yerel herhangi bir konumda r29 yeniden koyabilirsiniz. Çerçeve işaretçilerini aşağıda Yereller SP'yi üzerinde temel erişilebilir.

7. Zincirleme, çerçeve ile veya olmadan alloca() > 4K, boyut,

    ```asm
        stp    r29, lr, [sp, -80]!          // pre-indexed, save <r29,lr>
        stp    r19,r20,[sp,16]              // save in INT regs
        stp    r21,r22,[sp,32]              // ...
        stp    d8,d9,[sp,48]                // save in FP regs
        stp    d10,d11,[sp,64]
        mov    r29,sp                       // r29 points to top of local area
        mov    r8, #framesz/16
        bl     chkstk
        sub    sp, r8*16                    // allocate remaining frame
                                            // end of prolog
        ...
        sp = alloca                         // more alloca() in body
        ...
                                            // beginning of epilog
        mov    sp,r29                       // sp points to top of local area
        ldp    d10,d11, [sp,64],
        ...
        ldp    r29, lr, [sp], -80           // post-indexed, reload <r29,lr>
    ```

## <a name="arm64-exception-handling-information"></a>ARM64 özel durum işleme bilgileri

### <a name="pdata-records"></a>.pdata kayıtları

Her bir PE ikili yığın düzenleme işlevi tanımlayan sabit uzunluklu öğelerin sıralı bir dizisi .pdata kayıtlardır. Dikkatli bir şekilde ifade "yığını-düzenleme" Not: herhangi bir yerel depolama alanı gerektirmez ve hangi gerekmez geçici olmayan kayıtları kaydedilemiyor/geri yaprak işlevleri; .pdata kayıt gerektirmez Bunlar açıkça alandan kazanmak için alınmamalıdır. Bu işlevler birinden bir geriye doğru izleme, çağırana taşımak LR gelen dönüş adresi yalnızca elde edebilirsiniz.

ARM64 için her .pdata kayıt 8 bayt uzunluğundadır. İlk sözcük, ikinci ile ardından işlevin 32-bit RVA başlangıç her kayıt yerleri genel biçimi değişken uzunluklu sanal işlem bulunur bloğu için bir işaretçi ya da bir canonical işlevi geriye doğru izleme sırası açıklayan paketlenmiş bir sözcük içeriyor.

![.pdata kayıt düzeni](../build/media/arm64-exception-handling-pdata-record.png ".pdata kayıt düzeni")

Alanları aşağıdaki gibidir:

- **İşlevi Başlat RVA** 32-bit RVA işlevi başlangıcı olduğu.

- **Bayrağı** kalan 30 bit ikinci .pdata word'ün yorumlama gösteren bir 2 bit alanıdır. Varsa **bayrağı** 0'dır ve ardından form kalan bitleri bir **özel durum bilgileri RVA** (düşük iki bit örtük olarak 0). Varsa **bayrağı** form kalan bitleri sonra sıfır olan bir **geriye doğru izleme verileri paketlenmiş** yapısı.

- **Özel durum bilgileri RVA** sanal işlem bulunur bölümde depolanan değişken uzunluklu özel durum bilgisi yapısı adresidir. Bu veriler, 4 bayt hizalı olmalıdır.

- **Geriye doğru izleme verileri paketlenmiş** kurallı biçimi varsayılarak bir işlevden geriye doğru izlemek için gereken işlemleri sıkıştırılmış bir açıklaması verilmektedir. Bu durumda, hiçbir sanal işlem bulunur kayıt gereklidir.

### <a name="xdata-records"></a>Sanal işlem bulunur kayıtları

Paketlenmiş geriye doğru izleme biçimi işlevi geriye doğru izleme açıklamak için yetersiz olduğunda, bir değişken uzunluklu sanal işlem bulunur kaydı oluşturulmalıdır. Bu kaydın adresini .pdata kaydın ikinci Word'de depolanır. Sanal işlem bulunur paketlenmiş değişken uzunluklu bir kelimelerin biçimdedir:

![Sanal işlem bulunur kayıt düzeni](../build/media/arm64-exception-handling-xdata-record.png "sanal işlem bulunur kayıt düzeni")

Bu veriler, dört bölüme ayrılır:

1. Yapı toplam boyutunu açıklayan ve anahtar işlevi veri sağlayan bir 1 veya 2 sözcük üstbilgisi. İkinci sözcük yalnızca her iki mevcut **sonuç sayısı** ve **kod sözcükleri** alanları 0 olarak ayarlayın. Üst bilgisindeki bit alanları şunlardır:

   a. **İşlev uzunluğu** işlevi bölü 4 bayt cinsinden toplam uzunluğunu belirten bir 18-bit alanıdır. Bir işlev 1 milyon büyükse, birden çok pdata ve xdata kayıt işlevi tanımlamak için kullanılmalıdır. Bkz: [büyük işlevleri](#large-functions) ayrıntılı bilgi için.

   b. **Vers** kalan xdata sürümünü tanımlayan bir 2 bit alanıdır. Şu andan itibaren yalnızca sürüm 0 tanımlanır ve bu nedenle 1-3 değerlerinin izin verilmez.

   c. **X** varlığı (1) veya özel durum verileri yokluğu (0) gösteren bir 1 bit alanıdır.

   d. **E** bir bit alanı, tek bir sonuç paketlenmiş üstbilgisine (1) gerek kalmadan ek kapsam bilgileri açıklayan sonraki (0) sözcükleri belirtir.

   e. **Sonuç sayısı** durumuna bağlı olarak iki anlama sahip 5-bit alanı **E** bit:

      1. Varsa **E** 0 olarak ayarlayın: 2. bölümünde açıklanan özel durum kapsamları toplam sayısı sayısını belirtir. Birden fazla 31 kapsamları işlevinde varsa sonra **kod sözcükleri** alan bir uzantı Word'ün gerekli olduğunu belirtmek için 0 olarak ayarlanmalıdır.

      2. Varsa **E** Bu alan bir ve yalnızca sonuç açıklayan ilk geriye doğru izleme kodu dizinini belirten 1 olarak ayarlanır.

   f. **Kod sözcük** tüm bölüm 4'teki geriye doğru izleme kodları içermesi için gerekli 32 bit sözcük sayısını belirten bir 5-bit alanıdır. 31'den fazla sözcük gerekiyorsa (örneğin, kod bayt 124'den fazla bırakma), sonra da bu alanı bir uzantı Word'ün gerekli olduğunu belirtmek için 0 olarak ayarlanması gerekir.

   g. **Sonuç sayısı Genişletilmiş** ve **genişletilmiş kod sözcükleri** 16-bit ve 8-bit alanları, sırasıyla, olağan dışı derecede büyük bir sonuç sayısı kodlama için daha fazla alan sağlayan veya bir çok sayıda kod sözcükleri geriye doğru izleme. Bu alanlar içeren uzantı sözcüğünü yalnızca her iki mevcut **sonuç sayısı** ve **kod sözcükleri** ilk üstbilgi sözcük alanlara 0 olarak ayarlanır.

2. Sonra özel durum verileri varsa **sonuç sayısı** sıfır değil, sonuç kapsamları hakkında bilgi listesi bir Word paketlenmiş ve, başlangıç uzaklığını artan sıraya göre depolanır. Her kapsam, aşağıdaki bit içerir:

   a. **Başlangıç ve bitiş uzaklığı** işlevi başlangıcını göre sonuç 4, bölü, bayt uzaklığı açıklayan bir 18 bit alanı

   b. **Res** gelecekteki genişleme için ayrılmış bir 4-bit alanıdır. Değeri 0 olmalıdır.

   c. **Başlangıç ve bitiş dizin** 10-bit, (2 daha fazla bitten **genişletilmiş kod sözcükleri**) alan ilk bayt dizinini belirten geriye doğru izleme, bu sonuç açıklar.

3. Geriye doğru izleme kodları içeren bir bayt dizisi bitiş kapsam listesi çağrıldıktan sonra bir sonraki bölümde ayrıntılı açıklanmıştır. Bu dizi için en yakın tam sözcük sınırı sonunda sıfır eklenir. Küçük endian modunda doğrudan getirilebilir, böylece bayt little endian sırayla depolanır.

4. Son olarak, geriye doğru izleme kodu bayt sonra (ve **X** bit üst bilgisindeki 1 olarak ayarlanmıştır) özel durum işleyicisi bilgileri alınır. Bu tek bir oluşur **özel durum işleyicisi RVA** adresi özel durum işleyicisinin kendisi, sağlama ve ardından hemen bir özel durum işleyici tarafından gerekli veri değişken uzunluklu miktarı.

Yukarıdaki sanal işlem bulunur kaydı ilk 8 bayt getirmek ve tam boyutunu (eksi aşağıdaki özel durum değişken boyutlu veri uzunluğu) kaydı, işlem olası olduğu şekilde tasarlanmıştır. Aşağıdaki kod parçacığı, kayıt boyutunu hesaplar:

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

Giriş ve her bitiş sahip olsa da, kendi dizine geriye doğru izleme kodları, tablo, bunlar arasında paylaşılır ve tamamen olası (ve tamamen seyrek) unutulmamalıdır bunlar tüm (bkz. örnek 2'de ek A) aynı kodu paylaşabilirsiniz. Belirtilebilecek en büyük dizinden 255 olduğundan derleyici yazıcıları bu durumda, özellikle bu nedenle belirli bir işlev için geriye doğru izleme kodları toplam sayısını sınırlama iyileştirmeniz gerekir.

### <a name="unwind-codes"></a>Geriye doğru izleme kodları

Geriye doğru izleme kodları işlemlerin geri alınması gerekir sırada giriş etkilerini geri nasıl tam olarak açıklayan sıralarının havuzu dizisidir. Geriye doğru izleme kodları, bir bayt dizisi kodlanmış bir mini yönerge kümesi olarak düşünülebilir. Yürütme tamamlandıktan sonra çağıran işlevin dönüş adresi lr kaydıdır ve tüm geçici olmayan kasalar değerlerine işlev çağrıldı zaman geri yüklenir.

Özel durumları her zaman sadece bir işlev gövdesinin içinde (ve hiçbir zaman bir giriş veya herhangi bir sonuç ile) oluşan garanti, yalnızca tek bir dizi gerekli olacaktır. Ancak, Windows geriye doğru izleme modeli biz gelen bir kısmi yürütülen giriş veya çıkış içinde bırakma mümkün olmasını gerektirir. Bunların dönüştürmelerle 1:1 giriş ve bitiş ilgili her kurtularak eşleneceğine şekilde bu gereksinimi karşılamak üzere geriye doğru izleme kodları dikkatli bir şekilde tasarlanmıştır. Bu, birkaç olası etkilere sahiptir:

1. Geriye doğru izleme kodları sayısını sayma tarafından giriş ve bitiş uzunluğunu hesaplamak mümkündür.

2. Başlangıç ve bitiş kapsamın geçmiş yönerge sayısını sayma tarafından geriye doğru izleme kodları eşdeğeri olan sayıyı atlayabilir ve kısmen yürütülen tamamlamak için bir dizi rest yürütmek mümkündür bitiş gerçekleştirmekte olduğu geriye doğru izleme.

3. Yönerge giriş bitmeden önce sayısını sayma tarafından geriye doğru izleme kodları eşdeğeri olan sayıyı atlayabilir ve sırası, yalnızca yürütme tamamlanan giriş bölümlerini geri kalanını yürütmek mümkündür.

Geriye doğru izleme kodları aşağıdaki tabloya göre kodlanır. Tüm geriye doğru izleme kodları dışındaki bir büyük yığın ayıran bir tek veya çift bayt olan. Tamamen 21 geriye doğru izleme kod vardır. Kısmen yürütülen açıklanabilmeleri ve sonuç, geriye doğru izleme izin vermek üzere her geriye doğru izleme kod eşlemeleri tam olarak bir yönergesinde giriş/sonuç.

Kod geriye doğru izleme|BITS ve yorumu
|-|-|
`alloc_s`|000xxxxx: küçük yığın boyutu < 512 ile ayırın (2 ^ 5 * 16).
`save_r19r20_x`|    001zzzzz: Kaydet \<r19, r20 > çifti, [sp #Z * 8]!, önceden dizinlenmiş uzaklığı >-248 =
`save_fplr`|        01zzzzzz: Kaydet \<r29, lr > adresindeki pair [sp + #Z * 8], offset < 504 =.
`save_fplr_x`|        10zzzzzz: Kaydet \<r29, lr > adresindeki pair [sp-(#Z + 1) * 8]!, önceden dizinlenmiş uzaklığı > -512 =
`alloc_m`|        11000xxx\|xxxxxxxx: büyük yığın boyutu 16 k < ayırın (2 ^ 11 * 16).
`save_regp`|        110010xx\|xxzzzzzz: r(19+#X) çifti, kaydetme [sp + #Z * 8], offset < 504 =
`save_regp_x`|        110011xx\|xxzzzzzz: çifti r(19+#X) adresindeki Kaydet [sp-(#Z + 1) * 8]!, önceden dizinlenmiş uzaklığı > -512 =
`save_reg`|        110100xx\|xxzzzzzz: reg r(19+#X) adresindeki Kaydet [sp + #Z * 8], offset < 504 =
`save_reg_x`|        1101010 x\|xxxzzzzz: reg r(19+#X) adresindeki Kaydet [sp-(#Z + 1) * 8]!, önceden dizinlenmiş uzaklığı >-256 =
`save_lrpair`|         1101011 x\|xxzzzzzz: çifti Kaydet \<r19 + 2 *#X, lr > konumundaki [sp + #Z*8], offset < 504 =
`save_fregp`|        1101100 x\|xxzzzzzz: çifti d(8+#X) adresindeki Kaydet [sp + #Z * 8], offset < 504 =
`save_fregp_x`|        1101101 x\|xxzzzzzz: adresindeki çifti d(8+#X) kaydetme [sp-(#Z + 1) * 8]!, önceden dizinlenmiş uzaklığı > -512 =
`save_freg`|        1101110 x\|xxzzzzzz: reg d(8+#X) adresindeki Kaydet [sp + #Z * 8], offset < 504 =
`save_freg_x`|        11011110\|xxxzzzzz: reg d(8+#X) adresindeki Kaydet [sp-(#Z + 1) * 8]!, önceden dizinlenmiş uzaklığı >-256 =
`alloc_l`|         11100000\|xxxxxxxx\|xxxxxxxx\|xxxxxxxx: < 256 M boyutuyla büyük yığın ayırma (2 ^ 24 * 16)
`set_fp`|        11100001: r29 ayarlayın: ile: mov r29 sp
`add_fp`|        11100010\|xxxxxxxx: r29 ile ayarlayın: ekleme r29, sp, #x * 8
`nop`|            11100011: hiçbir bırakma işlemi gerekiyor.
`end`|            11100100: bırakma kod sonu. Gelir bölümünde ret.
`end_c`|        11100101: zincirleme geçerli kapsamda geriye doğru izleme kodu sonu.
`save_next`|        11100110: sonraki geçici olmayan Int kaydedin veya FP çifti kaydedin.
`arithmetic(add)`|    11100111\| 000zxxxx: lr için tanımlama bilgisi reg(z) ekleyin (0 = x28, 1 = sp); lr, lr, reg(z) ekleyin
`arithmetic(sub)`|    11100111\| 001zxxxx: tanımlama bilgisi reg(z) lr'nden alt (0 = x28, 1 = sp); sub lr, lr, reg(z)
`arithmetic(eor)`|    11100111\| 010zxxxx: eor lr tanımlama bilgisi reg(z) ile (0 = x28, 1 = sp); eor lr, lr, reg(z)
`arithmetic(rol)`|    11100111\| 0110xxxx: lr tanımlama bilgisi reg (x28) ile sanal rol; xip0 neg = x28; ror lr, xip0
`arithmetic(ror)`|    11100111\| 100zxxxx: ror lr tanımlama bilgisi reg(z) ile (0 = x28, 1 = sp); ror lr, lr, reg(z)
||            11100111: xxxz---:---ayrılmış
||              11101xxx: aşağıdaki yalnızca asm rutinleri için oluşturulan özel yığının çalışmaları için ayrılmış
||              11101001: özel yığının MSFT_OP_TRAP_FRAME için
||              11101010: özel yığının MSFT_OP_MACHINE_FRAME için
||              11101011: özel yığının MSFT_OP_CONTEXT için
||              1111xxxx: ayrılmış

Birden fazla bayt kapsayan büyük değerlerle yönergelerde en önemli bitleri ilk depolanır. Yukarıdaki geriye doğru izleme kodları yalnızca kod ilk baytı bakarak geriye doğru izleme kodu bayt cinsinden toplam boyut bilmek mümkündür şekilde tasarlanmıştır. Her geriye doğru izleme kodu tam olarak bir giriş ve bitiş yönergesinde eşlenen düşünüldüğünde, giriş veya çıkış, boyutunu hesaplamak için yapmanız gereken tek şey dizinin başından sonuna kadar belirlemek için arama tablosu veya benzer bir cihaz kullanarak yürütmek için ne kadar süreyle düzeltme yanıt veren işlem kodu var.

Uzaklık adresleme sonrası dizine Not giriş bölümünde izin verilmiyor. Tüm uzaklık aralıkları (#Z) dışında STP/STR adresleme kodlama ile `save_r19r20_x` tüm alanları (10 Int kayıtları + 8 FP kayıtları + 8 giriş kayıtları) kaydetmek için hangi 248 yeterlidir.

`save_next` Int kaydetme izleyin veya FP geçici çifti kaydetmek gerekir: `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x`, veya başka bir `save_next`. Sonraki kayıt çiftine sonraki 16 baytlık yuvasındaki "büyüyen" sırayla kaydeder. `save-next` Aşağıdaki bir `save_next` son Int kayıt çiftine başvuruyor ilk FP kayıt çiftine gösterir.

Normal boyutunu döndürür ve yönergeleri aynı bağlantı olmadığından, gerekmez, ayrılmış bir `end` kuyruk çağrısı senaryoları için kod geriye doğru izleme.

`end_c` bitişik olmayan işlev parçalarını en iyi duruma getirme amacıyla işlemek için tasarlanmıştır. A `end_c` geriye doğru izleme kodları geçerli kapsamda sonuna belirten başka bir dizi gerçek ile sona erdi geriye doğru izleme kodu tarafından uyulması gereken `end`. Geriye doğru izleme kodları arasında `end_c` ve `end` üst bölgesi ("hayalet" Giriş) giriş işlemlerinde temsil eder.  Daha fazla bilgi ve örnekler, aşağıdaki bölümde açıklanmıştır.

### <a name="packed-unwind-data"></a>Paketlenmiş veri bırakma

Kurallı biçimi aşağıda olan açıklanabilmeleri ve sonuç izleyin paketlenmiş işlevleri geriye doğru izleme için veri bırakma, bir sanal işlem bulunur kaydı gereksinimini tamamen ortadan kaldırır ve sağlama maliyetini önemli ölçüde azaltarak, veri kullanılabilir. Kurallı açıklanabilmeleri ve sonuç bir özel durum işleyicisi gerektirmez ve standart bir sırada kurulumu ve kaldırma işlemlerini gerçekleştiren basit bir işlevi ortak gereksinimlerini karşılayacak şekilde tasarlanmıştır.

Paketlenmiş bir .pdata kayıt biçimi geriye doğru veri şunun gibi görünür:

![Paketlenmiş .pdata kayıtla veri bırakma](../build/media/arm64-exception-handling-packed-unwind-data.png "paketlenmiş .pdata kaydıyla, veriler geriye doğru izleme")

Alanları aşağıdaki gibidir:

- **İşlevi Başlat RVA** 32-bit RVA işlevi başlangıcı olduğu.
- **Bayrağı** 2 bit alanı yukarıda, aşağıdaki anlamlara ile aynıdır:
  - 00 = paketlenmiş kullanılmıyor; veri bırakma Aşağıda, sanal işlem bulunur kayda kalan bitleri noktası
  - 01 = paketlenmiş tek giriş ve bitiş başlangıcına ve sonuna kapsamı ile aşağıda açıklandığı gibi kullanılan veri bırakma
  - 10 = paketlenmiş herhangi bir giriş ve bitiş; olmadan kod için aşağıda açıklandığı gibi kullanılan veri bırakma Bu, ayrılmış işlevi segmentleri açıklamak için kullanışlıdır.
  - 11 = ayrılmıştır;
- **İşlev uzunluğu** tüm işlevi bölü 4 bayt cinsinden uzunluğunu sağlayan bir 11 bit alanıdır. İşlev 8 k'dan büyükse, bir tam sanal işlem bulunur kaydı yerine kullanılmalıdır.
- **Çerçeve boyutu** 16 tarafından ayrılmış, bu işlev için ayrılan yığınının bayt sayısını gösteren bir 9-bit alanıdır. Büyük (8 k-16) bayt yığın ayırma işlevleri tam bir sanal işlem bulunur kaydı kullanmanız gerekir. Bu parametre alanı, Int ve FP alan ve çağrılan kaydedilmiş ve giriş parametresi alan giden ancak dinamik ayırma alan hariç olmak üzere yerel değişken alan içerir.
- **CR** olan işlev bir çerçeve zinciri ve dönüş bağlantı ayarlamak için ek yönergeler içerip içermeyeceğini belirten bir 2 bit bayrağı:
  - 00 unchained işlevi = \<r29, lr > çifti yığınında kaydedilmez.
  - 01 unchained işlevi = \<lr > yığınında kaydedildi
  - 10 = ayrılmıştır;
  - 11 = zincirleme işlevi, giriş/sonuç deposu/yük çifti yönerge kullanılan \<r29, lr >
- **H** işlevi çok başlangıcında depolayarak olan işlev tam sayı parametresi homes olup olmadığını belirten bir 1 bit bayrağı (r0-r7) kaydeder. (0 = 1 kaydeder ev değil havaalanlarından kayıtları =).
- **RegI** kurallı yığın konuma kaydedildiğinde geçici olmayan INT kayıtları (r28 r19) sayısını gösteren bir 4-bit alanıdır.
- **RegF** kurallı yığın konuma kaydedildiğinde geçici olmayan FP kayıtları (d15 d8) sayısını gösteren bir 3-bit alanıdır. (0 = yok FP kaydı kaydedilir, m > 0: m + 1 FP kayıtları kaydedilir). İşlevi yalnızca bir paketin FP kaydına, geriye doğru izleme kaydetmek için veri uygulanamaz.

Yukarıdaki bölümde 1, 2 (olmadan Giden parametre alanı), 3 ve 4 kategorilere giren kurallı açıklanabilmeleri paketlenmiş geriye doğru izleme biçimi tarafından temsil edilebilir.  Kurallı işlevler çok benzer bir form izleyin başlangıçları dışındaki **H** hiçbir etkisi `set_fp` yönerge atlanırsa ve adımları ve bunun yanı sıra her bir adımın yönergeleri sırasını bölümünde tersine çevrilir. Paketlenmiş xdata algoritması, aşağıdaki tabloda ayrıntılı adımları izler:

0. adım: her alanı boyutunu hesaplama gerçekleştirin.

1. adım: Int ve Çağrılan Kaydedilmiş Yazmaçlar kaydedin.

2. adım: Bu adım türü erken bölümlerde 4 için özeldir. LR Int alan sonunda kaydedilir.

3. adım: FP Çağrılan Kaydedilmiş Yazmaçlar kaydedin.

4. adım: Giriş bağımsız değişkeni giriş parametre alanında kaydedin.

5. adım: yerel ağ dahil olmak üzere, kalan yığın ayırma \<r29, lr > eşleştirme ve parametre alanı giden. 5a 1 kurallı türüne karşılık gelir. 5b ve 5c kurallı tür 2 ' dir. 5d ve 5e her iki tür için 3 ve 4 yazın.

Adım #|Bayrak değerleri|yönerge sayısı|Opcode|Kod geriye doğru izleme
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1.|0 < **regI** < 10 =|RegI / 2 + **RegI** % 2|`stp r19,r20,[sp,#savsz]!`<br/>`stp r21,r22,[sp,16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**01 == *|1.|`str lr,[sp, #intsz-8]`\*|`save_reg`
3|0 < **RegF** < = 7|(RegF + 1) / 2 +<br/>(RegF + 1) % 2).|`stp d8,d9,[sp, #intsz]`\*\*<br/>`stp d10,d11,[sp, #intsz+16]`<br/>`...`<br/>`str d(8+RegF),[sp, #intsz+#fpsz-8]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** 1 ==|4|`stp r0,r1,[sp, #intsz+#fpsz]`<br/>`stp r2,r3,[sp, #intsz+#fpsz+16]`<br/>`stp r4,r5,[sp, #intsz+#fpsz+32]`<br/>`stp r6,r7,[sp, #intsz+#fpsz+48]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5a|**CR** 11 == & & #locsz<br/> < = 512|2|`stp r29,lr,[sp,-#locsz]!`<br/>`mov r29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5b|**CR** 11 == &AMP; &AMP;<br/>512 < #locsz < 4088 =|3|`sub sp,sp, #locsz`<br/>`stp r29,lr,[sp,0]`<br/>`add r29, sp, 0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5c|**CR** 11 == & & #locsz > 4088|4|`sub sp,sp,4088`<br/>`sub sp,sp, (#locsz-4088)`<br/>`stp r29,lr,[sp,0]`<br/>`add r29, sp, 0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5d|(**CR** 00 == \| \| **CR**01 ==) &AMP; &AMP;<br/>#locsz < 4088 =|1.|`sub sp,sp, #locsz`|`alloc_s`/`alloc_m`
5e|(**CR** 00 == \| \| **CR**01 ==) &AMP; &AMP;<br/>#locsz > 4088|2|`sub sp,sp,4088`<br/>`sub sp,sp, (#locsz-4088)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\*: Eğer **CR** 01 == ve **RegI** tek sayı, adım 2 ve 1. adımda son save_rep bir save_regp birleştirilir.

\*\* Varsa **RegI** == **CR** == 0, ve **RegF** ! = 0 ise, ilk stp kayan nokta azaltma için.

\*\*\* Yönerge için karşılık gelen `mov r29, sp` bölümünde yok. Biz kullanamazsınız sp geri r29'nden bir işlev gerektiriyorsa, paketli veri bırakma.

### <a name="unwinding-partial-prologs-and-epilogs"></a>Geriye doğru izleme kısmi açıklanabilmeleri ve sonuç

En yaygın geriye doğru izleme durumu giriş ve tüm sonuç uzağa işlevinin gövdesi içinde özel durum veya çağrı nerede oluştuğunu biridir. Geriye doğru izleme bu durumda, oldukça basittir: unwinder yalnızca geriye doğru izleme dizi dizini 0 başlangıç ve bitiş opcode algılandığında kadar devam kodları yürütme başlar.

Bir giriş veya çıkış yürütülürken bir özel durum veya kesinti nerede oluştuğunu durumda doğru bırakma daha zordur. Bu gibi durumlarda, yığın çerçevesinin yalnızca kısmen oluşturulmuş olan ve ux'in tam olarak ne doğru geri almak için yapılmıştır belirlemektir.

Örneğin, bu giriş ve bitiş dizisi alır:

```asm
0000:    stp    r29, lr, [sp, -256]!        // save_fplr_x  256 (pre-indexed store)
0004:    stp    d8,d9,[sp,224]              // save_fregp 0, 224
0008:    stp    r19,r20,[sp,240]            // save_regp 0, 240
000c:    mov    r29,sp                      // set_fp
         ...
0100:    mov    sp,r29                      // set_fp
0104:    ldp    r19,r20,[sp,240]            // save_regp 0, 240
0108:    ldp    d8,d9,[sp,224]              // save_fregp 0, 224
010c:    ldp    r29, lr, [sp, -256]!        // save_fplr_x  256 (post-indexed load)
0110:    ret     lr                         // end
```

Her opcode yanında, bu işlem açıklayan uygun geriye doğru izleme kodudur. Dikkat edilecek ilk şey geriye doğru izleme kodları giriş için bir dizi geriye doğru izleme kodları bitiş (Bitiş'ın son yönergede sayılmaz) için tam bir Ayna görüntüsünü olmasıdır. Bu yaygın bir durumdur ve bu nedenle geriye doğru izleme kodları giriş için her zaman girişin yürütme siparişi ters sırada depolanır varsayılır.

Bu nedenle, hem giriş ve sonuç için biz geriye doğru izleme kodları ortak bir dizi kalır:

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

Temizlik henüz bitti olarak içinde (Bu işlevde 0x100 uzaklığında başlar) ve bitiş uzaklığı 0 sonuç durumu (daha fazla açık normal sırada olduğu gibi) ile başlayan, biz tam geriye doğru izleme sırası yürütülecek beklenir. Biz kendimize tek bir yönerge (en bitiş uzaklığı 2) bulursanız, biz başarıyla ilk geriye doğru izleme kodu atlayarak geriye doğru izleyebilirsiniz. Bu durum Genelleştirme, işlem kodları arasında 1:1 eşleme varsayılarak ve geriye doğru izleme kodları, biz yönerge h bitiş'dan geriye doğru, size ilk n geriye doğru izleme kodları atlayın ve buradan yürütmeye başlamak emin ediyoruz belirtin.

Benzer bir mantık için giriş, dışında geriye doğru çalıştığını ortaya çıkmıştır. Biz giriş uzaklığı 0'dan geriye doğru izleme, biz hiçbir şey çalıştırmak istersiniz. Biz 2 uzaklığı çağrıdan, tek bir yönerge olduğu ve biz sonundan geriye doğru izleme sırası bir geriye doğru izleme kodu yürütmeye başlamak istiyorsunuz (unutmayın kodları ters sırada depolanır). Ve biz giriş yönerge n'dan geriye doğru izleme, biz n geriye doğru izleme kodları kodlarının listesi sonundan yürütme başlamalıdır, burada çok biz genelleştirebilirsiniz.

Artık, her zaman giriş ve sonuç kodları tam olarak eşleşen bir durum değildir. Bu nedenle, geriye doğru izleme dizisi kodlarının birkaç dizileri içeren gerekebilir. Nereye kodları işlemesi uzaklığı belirlemek için aşağıdaki mantık kullanın:

1. İçinde farklı dan geriye doğru izleme işlevinin gövdesi yalnızca geriye doğru izleme kodları dizin 0 konumunda yürütmeye başlamak ve "Bitiş" opcode basmak kadar devam edin.

2. Gelen bir bitiş içinde geriye doğru izleme, sonuç kapsamlı bir başlangıç noktası olarak sağlanan bitiş özgü başlangıç dizini kullanın. İşlem kaç bayt söz konusu bilgisayar bitiş başlangıcından. Ardından tüm zaten yürütüldü yönergeleri muhasebesi kadar geriye doğru izleme kodları atlanıyor geriye doğru izleme kodları aracılığıyla İleri ilerleyin. Ardından bu noktada başlangıç yürütün.

3. Dizin 0 gelen giriş içinde geriye doğru izleme, başlangıç noktası olarak kullanın. Giriş kodu dizisinin uzunluğunu hesaplamak ve ardından söz konusu bilgisayarı kaç bayt giriş sonundan işlem. Ardından tüm henüz yürütülen yönergeleri muhasebesi kadar geriye doğru izleme kodları atlanıyor geriye doğru izleme kodları aracılığıyla İleri ilerleyin. Ardından bu noktada başlangıç yürütün.

Sonuç olarak bu kurallar, giriş için geriye doğru izleme kodları her zaman dizideki ilk olmalıdır ve ayrıca genel gelen gövdesi içinde geriye doğru izleme kullanım durumu geriye doğru izlemek için kullanılan kodları oldukları. Tüm özel Sonuç kodu dizilerinizi hemen sonra uygulamanız gerekir.

### <a name="function-fragments"></a>İşlev parçaları

Kod optimizasyon ve diğer nedenleriyle bir işlev (bölge olarak da bilinir) ayrı parçaları bölme tercih edilebilir. Bu yapıldığında, oluşturulan her işlev parça kendi ayrı .pdata (ve muhtemelen .xdata) gerektirir. kayıt.

Kendi giriş sahip ayrılmış ikincil parça için hiçbir yığın ayarlama, giriş bölümünde yapılır beklenmektedir. Tüm yığın için ayrılan alan gerekli ikincil bölgede gerekir önceden ayrılan kendi üst bölgesi (veya çağrılan ana bölge). Bu yığın işaretçisi işleme kesinlikle işlevin özgün giriş bölümünde tutar.

Bir normal işlev parçalarını durumudur "ayırma ile derleyicinin kod" kod ana işlevini dışında bir bölge taşıma. Kod ayırma ile sonuçlanan üç olağandışı durumlar vardır.

#### <a name="example"></a>Örnek:

- (bölge 1: başlar)

    ```asm
        stp     r29, lr, [sp, -256]!    // save_fplr_x  256 (pre-indexed store)
        stp     r19,r20,[sp,240]        // save_regp 0, 240
        mov     r29,sp                  // set_fp
        ...
    ```

- (bölge 1: Son)
- (bölge 3: başlar)

    ```asm
        ...
    ```

- (bölge 3: Bitiş)
- (bölge 2: başlar)

    ```asm
    ...
        mov     sp,r29                  // set_fp
        ldp     r19,r20,[sp,240]        // save_regp 0, 240
        ldp     r29, lr, [sp, -256]!    // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (bölge 2: Son)

1. Yalnızca giriş (bölge 1: ayrılmış bölgelerde tüm başlangıçları durumdadır):

   Yalnızca giriş açıklanan gerekir. Bu kısa .pdata biçimi tarafından gösterilemez. Tam sanal işlem bulunur durumda da, bu sonuç sayısı ayarlayarak temsil edilebilir = 0. Bölge 1 yukarıdaki örnekte bkz.

   Geriye doğru izleme kodları: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

2. Yalnızca başlangıçları (bölge 2: giriş olan ana bölge)

   Tüm prolog kodları bu bölgeye atlama zaman denetim tarafından görülebilmesini varsayılır. Kısmi geriye doğru izleme bir normal işlev aynı şekilde sonuç oluşabilir. Bu tür bir bölge compact .pdata tarafından gösterilemez. Tam xdata kaydında, bunu köşeli parantez içindeki tarafından bir "hayalet" giriş ile kodlanabilir bir `end_c` ve `end` kod çifti geriye doğru izleme.  Başında `end_c` giriş boyutu sıfır olduğunu gösterir. Sonuç başlangıç dizini tek bitiş noktası `set_fp`.

   Bölge 2 için kod geriye doğru izleme: `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

3. Açıklanabilmeleri veya sonuç yok (bölge 3: açıklanabilmeleri ve tüm sonuç olan diğer parçaları):

   Bayrak ayarlandığında aracılığıyla Compact .pdata biçimi uygulanabilir = 10. Tam sanal işlem bulunur kaydıyla sonuç sayısı = 1. Geriye doğru izleme kodu ile aynı bölge yukarıdaki 2. ancak de başlangıç ve bitiş dizini işaret `end_c`. Kısmi geriye doğru izleme hiçbir zaman kod bu bölgede gerçekleşir.

Başka bir daha karmaşık işlevi parçaları "ile derleyicinin sarmalama küçültme" dışında işlev girişi giriş kadar bazı Çağrılan Kaydedilmiş Yazmaçlar kaydetme gecikme tercih edebilirsiniz durumudur.

- (bölge 1: başlar)

    ```asm
        stp     r29, lr, [sp, -256]!    // save_fplr_x  256 (pre-indexed store)
        stp     r19,r20,[sp,240]        // save_regp 0, 240
        mov     r29,sp                  // set_fp
        ...
    ```

- (bölge 2: başlar)

    ```asm
        stp     r21,r22,[sp,224]        // save_regp 2, 224
        ...
        ldp     r21,r22,[sp,224]        // save_regp 2, 224
    ```

- (bölge 2: Son)

    ```asm
        ...
        mov     sp,r29                  // set_fp
        ldp     r19,r20,[sp,240]        // save_regp 0, 240
        ldp     r29, lr, [sp, -256]!    // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (bölge 1: Son)

Bölge 1 giriş bölümünde yığın alanı, önceden ayrılmış. Bu bölge 2 bile onun ana işlevini dışına taşınırsa aynı geriye doğru izleme koda sahip unutmayın.

Bölge 1: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end` başlangıç ve bitiş diziniyle işaret `set_fp` zamanki.

Bölge 2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`. Başlangıç ve bitiş dizini işaret ilk kod geriye doğru izleme `save_regp 2, 224`.

### <a name="large-functions"></a>Büyük işlevleri

Parçaları, İşlevler sanal işlem bulunur üst bilgisindeki bit alanları tarafından uygulanan 1 milyon sınırdan daha büyük açıklamak için yararlanılabilir. Böyle çok büyük bir işlev tanımlamak için basitçe parçalar 1 milyon daha küçük olarak bozuk durumda gerekir. Her parça, böylece birden fazla parçaya bir sonuç bölmediğinden düşüncesiyle ayarlanması gerekir.

Yalnızca ilk parçasını işlev bir giriş içerir; diğer tüm parçaları hiçbir giriş sahip olarak işaretlenir. Mevcut başlangıçları sayısına bağlı olarak, her parça, sıfır veya daha fazla sonuç içeriyor olabilir. Her sonuç kapsam içinde bir parça parça, start işlevin başlangıcını göreli başlangıç uzaklığı belirtir aklınızda bulundurun.

Bir parça, hiçbir giriş ve hiçbir sonuç varsa, yine de kendi .pdata (ve muhtemelen .xdata) gerektiriyor gelen işlevinin gövdesi içinde bırakma nasıl açıklamak için kaydı.

## <a name="examples"></a>Örnekler

### <a name="example-1-frame-chained-compact-form"></a>Örnek 1: Zincirleme çerçeve, CD-formu

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

### <a name="example-2-frame-chained-full-form-with-mirror-prolog--epilog"></a>Örnek 2: Zincirleme çerçeve, tam biçimli yansıtma Prolog ve Epilog ile

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

EpilogStart dizini [0] giriş geriye doğru izleme kodu aynı dizi için işaret ettiğini unutmayın.

### <a name="example-3-variadic-unchained-function"></a>Örnek 3: Bağımsız değişken içeren işlevi unchained.

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

Not: EpilogStart dizini [4], giriş geriye doğru izleme kodu (kısmen yeniden geriye doğru izleme dizisi) ortasını işaret eder.

## <a name="see-also"></a>Ayrıca bkz.

[ARM64 ABI kurallarına genel bakış](arm64-windows-abi-conventions.md)  
[ARM Özel Durum İşleme](../build/arm-exception-handling.md)  