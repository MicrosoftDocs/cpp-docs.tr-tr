---
title: Genel Visual C++ ARM Geçiş Sorunları
ms.date: 05/06/2019
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
ms.openlocfilehash: 889eed2b02362f33446cd9441ef84f406817b01a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224077"
---
# <a name="common-visual-c-arm-migration-issues"></a>Genel Visual C++ ARM Geçiş Sorunları

Microsoft C++ derleyicisi (MSVC) kullanılırken, aynı C++ kaynak kodu, ARM mimarisinde x86 veya x64 mimarilerinde olduğundan farklı sonuçlar üretebilir.

## <a name="sources-of-migration-issues"></a>Geçiş sorunları kaynakları

X86 veya x64 mimarilerinden ARM mimarisine kod geçirdiğinizde karşılaşabileceğiniz birçok sorun, tanımsız, uygulama tanımlı veya belirtilmemiş davranışı çağırabilen kaynak kod yapıları ile ilgilidir.

*Tanımsız davranış* , C++ standardının tanımlamaz ve makul bir sonucu olmayan bir işlem nedeniyle oluşur: Örneğin, kayan noktalı bir değeri işaretsiz tamsayıya dönüştürmek ya da değeri negatif olan veya yükseltilen türdeki bitlerin sayısını aşan bir dizi konum ile kaydırma.

*Uygulama tanımlı davranış* , C++ standardının derleyici satıcısının tanımlamasını ve belgeyi gerektirmesidir. Bir program, uygulama tanımlı davranışa güvenle güvenebilse de, taşınabilir olmayabilir. Uygulama tanımlı davranış örnekleri, yerleşik veri türleri ve bunların hizalama gereksinimlerinin boyutlarını içerir. Uygulama tanımlı davranıştan etkilenebilecek bir işlem örneği, değişken bağımsız değişken listesine erişiyor olabilir.

*Belirtilmeyen davranış* , C++ standardının kasıtlı olarak belirleyici olmayan davranış davranışıdır. Davranışı belirleyici olmayan kabul edilse de, belirtilmeyen davranışın belirli bir çağırma yöntemi derleyici uygulamasına göre belirlenir. Ancak, bir derleyici satıcısının sonucu önceden belirlemesi veya karşılaştırılabilir çağırmaları arasındaki tutarlı davranışı garanti etmek için bir gereksinim yoktur ve belge için gereksinim yoktur. Belirtilmeyen davranışa örnek olarak, bir işlev çağrısına bağımsız değişkenler içeren alt ifadelerin sıralaması yapılır.

Diğer geçiş sorunları, C++ standardına göre farklı şekilde etkileşen ARM ve x86 veya x64 mimarileri arasındaki donanım farklılıklarına bağlanabilir. Örneğin, x86 ve x64 mimarisinin güçlü bellek modeli, daha önce **`volatile`** belirli türde iş parçacığı iletişimini kolaylaştırmak için kullanılan bazı ek özellikler sağlar. Ancak ARM mimarisinin zayıf bellek modeli bu kullanımı desteklemez ve C++ standardı bunu gerektirmez.

> [!IMPORTANT]
> **`volatile`**, X86 ve x64 üzerinde iş parçacığı arası iletişimin sınırlı biçimlerini uygulamak için kullanılabilecek bazı özellikler kazanmakla birlikte, bu ek özellikler, genel olarak iş parçacıkları arası iletişim uygulamak için yeterli değildir. C++ standardı, bunun yerine uygun eşitleme temelleri kullanılarak bu iletişimin uygulanması önerilir.

Farklı platformlar bu tür davranışları farklı şekilde ifade edebildiğinden, platformlar arasında yazılım taşıma, belirli bir platformun davranışına bağımlıysa zor ve hataya açıktır. Bu tür davranışların birçoğu gözlemlenebilir ve kararlı görünebilse de, bunlara bağlı olarak en az taşınabilir değildir ve tanımsız veya belirtilmemiş davranış durumlarında de bir hatadır. Bu belgede alıntı yapılan davranış bile buna güvenmemelidir ve gelecekteki derleyicilerde veya CPU uygulamalarında değişebilir.

## <a name="example-migration-issues"></a>Örnek geçiş sorunları

Bu belgenin geri kalanında, bu C++ dili öğelerinin farklı davranışının farklı platformlarda farklı sonuçlar üretmesi açıklanmaktadır.

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>Kayan noktanın işaretsiz tamsayıya dönüştürülmesi

ARM mimarisinde, kayan nokta değerinin 32 bitlik bir tamsayıya dönüştürülmesi, kayan nokta değeri tamsayının temsil ettiği aralığın dışındaysa tamsayı temsil edilebilmesi için en yakın değere göre Cumartesi. X86 ve x64 mimarilerinde, tamsayı işaretsiz ise veya tamsayı imzalanmışsa-2147483648 olarak ayarlandıysa dönüştürme etrafında kaydırılır. Bu mimarilerin hiçbiri, kayan nokta değerlerinin küçük tamsayı türlerine dönüştürülmesini doğrudan desteklemez; Bunun yerine, dönüştürmeler 32 bit olarak gerçekleştirilir ve sonuçlar daha küçük bir boyuta kesilir.

ARM mimarisi için, doygunluk ve kesme birleşimi, işaretsiz türlere dönüştürmenin 32 bitlik bir tamsayıyı büyütürse daha küçük işaretsiz türlere doğru bir şekilde büyütülebileceğini, ancak daha 32 küçük bir değerden daha büyük değerler için kesilmiş bir sonuç üretir. Ayrıca, dönüştürme 32 bitlik işaretli tamsayılar için de doğru şekilde Cumartesi, ancak doygun, işaretli tamsayılar, pozitif doygun değerler için 1 ile, olumsuz doygun değerler için 0 ile sonuçlanır. Daha küçük bir işaretli tamsayıya dönüştürme öngörülemeyen bir sonuç üretir.

X86 ve x64 mimarileri için, işaretsiz tamsayı dönüştürmeleri için sarmalama davranışının birleşimi ve taşma üzerinde işaretli tamsayı dönüştürmeleri için açık değerlendirme, kesme ile birlikte, çok büyük olmaları durumunda tahmin edilemeyen birçok vardiyadaki sonuçlara neden olur.

Bu platformlar Ayrıca NaN (bir-Number değil) tamsayı türlerine dönüştürmeyi nasıl işleyseler de farklılık gösterir. ARM 'de NaN, 0x00000000 değerine dönüştürür; x86 ve x64 üzerinde, 0x80000000 öğesine dönüştürür.

Kayan nokta dönüştürme yalnızca değerin dönüştürülmekte olduğu tamsayı türü aralığında olduğunu biliyorsanız, bu, yalnızca bir değere güvenlebilir.

### <a name="shift-operator---behavior"></a>SHIFT işleci ( \<\< >>) davranışı

ARM mimarisinde, model tekrarlamaya başlamadan önce bir değer sola veya 255 bite doğru bir şekilde kaydıreklenebilir. X86 ve x64 mimarilerinde, düzenin kaynağı 64 bitlik bir değişken değilse, bu model her iki 32 katı için yinelenir. Bu durumda, model x64 üzerinde 64 ' un her katı ve bir yazılım uygulamasının çalıştığı x86 üzerinde 256 ' in her katı yinelenir. Örneğin, 32 konumunda sola kaydırılan 1 değeri olan 32 bitlik bir değişken için, ARM 'de sonuç 0, x86 üzerinde sonuç ise 1 ' dir ve sonuç olarak 1 ' dir. Ancak, değerin kaynağı 64 bitlik bir değişkense, üç platformda de elde edilen sonuç 4294967296 ' dir ve değer, x64 üzerinde 64 veya ARM ve x86 üzerinde 256 konumlarda kaydırılana kadar "sarmalama" yapmaz.

Kaynak türündeki bitlerin sayısını aşan bir vardiya işleminin sonucu tanımsız olduğundan, derleyicinin her durumda tutarlı davranışa sahip olması gerekmez. Örneğin, bir vardiyanın her iki işleneni de derleme zamanında biliniyorsa, derleyici, SHIFT 'in sonucunu önceden hesaplamak için bir iç yordam kullanarak programı en iyi hale getirebilir ve ardından SHIFT işleminin yerine sonucu yerine getirebilir. Kaydırma miktarı çok büyük veya negatif ise, iç yordamın sonucu CPU tarafından yürütülen aynı kaydırma ifadesinin sonucundan farklı olabilir.

### <a name="variable-arguments-varargs-behavior"></a>Değişken bağımsız değişkenler (varargs) davranışı

ARM mimarisinde, yığına geçirilen değişken bağımsız değişken listesindeki parametreler hizalamasına tabidir. Örneğin, 64 bitlik bir parametre 64 bit sınırında hizalanır. X86 ve x64 üzerinde, yığına geçirilen bağımsız değişkenler hizalama ve paket sıkı bir şekilde uygulanmaz. Bu fark, `printf` değişken bağımsız değişken listesinin beklenen düzeni tam olarak eşleşmiyorsa, örneğin, x86 veya x64 mimarilerinde bazı değerlerin bir alt kümesi için çalışsa bile, ARM 'de doldurma olarak tasarlanan bellek adreslerini okuma gibi değişen bir işlev oluşmasına neden olabilir. Şu örneği göz önünde bulundurun:

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will "parse" the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

Bu durumda, bağımsız değişkenin hizalaması kabul edilebilmesi için doğru biçim belirtiminin kullanıldığından emin olarak hata düzeltilebilir. Bu kod doğru:

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>Bağımsız değişken değerlendirme sırası

ARM, x86 ve x64 işlemciler bu kadar farklı olduğundan, derleyici uygulamalarına farklı gereksinimler ve ayrıca iyileştirmeler için farklı fırsatlar sunabilir. Bu nedenle, çağırma kuralı ve iyileştirme ayarları gibi diğer faktörlerle birlikte, bir derleyici, işlev bağımsız değişkenlerini farklı mimarilerde farklı bir sırada veya diğer faktörler değiştirildiğinde değerlendirebilirler. Bu, belirli bir değerlendirme sırasını kullanan bir uygulamanın davranışının beklenmedik şekilde değişmesine neden olabilir.

Bu tür bir hata, bir işlevin bağımsız değişkenlerinin, diğer bağımsız değişkenleri aynı çağrıda işleve etkileyen yan etkileri olduğunda meydana gelebilir. Genellikle bu tür bağımlılığın önlenmesi kolaydır, ancak bazen ayırt edilmesi zor olan bağımlılıklar veya operatör aşırı yüklemesi tarafından görünmeyebilir. Aşağıdaki kod örneğini göz önünde bulundurun:

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

Bu, iyi tanımlanmış görünüyor, ancak `->` ve `*` aşırı yüklenmiş işleçlerdir, bu kod şuna benzer bir şeye çevrilir:

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

Ve arasında bir bağımlılık varsa `operator->(memory_handle)` `operator*(p)` , özgün kod olası bir bağımlılık olmadığı gibi görünse de, kod belirli bir değerlendirme sırasına bağlı olabilir.

### <a name="volatile-keyword-default-behavior"></a>geçici anahtar sözcüğü varsayılan davranışı

MSVC derleyicisi, **`volatile`** derleyici anahtarları kullanarak belirtebileceğiniz depolama niteleyicisi 'nin iki farklı yorumleyicisini destekler. [/Volatile: MS](reference/volatile-volatile-keyword-interpretation.md) anahtarı, bu mimarilerde güçlü bellek modeli nedeniyle, x86 ve x64 için geleneksel durum olduğundan, güçlü sıralamayı garanti eden Microsoft genişletilmiş geçici semantiğini seçer. [/Volatile: ISO](reference/volatile-volatile-keyword-interpretation.md) anahtarı, güçlü sıralama garantisi olmayan katı C++ standart geçici semantiğini seçer.

ARM mimarisinde, ARM işlemcilerin zayıf sıralı bir bellek modeli olduğundan ve ARM yazılımının, **/volatile: MS** genişletilmiş semantiğine bağlı olmadığından ve genellikle bunu yapan yazılımlarla arabirim içermediği için, varsayılan olarak **/volatile: ISO** ' dur. Ancak bazen genişletilmiş semantiğini kullanmak için bir ARM programı derlemek için de kullanışlı veya hatta gereklidir. Örneğin, bir programın ISO C++ semantiğini kullanması için bağlantı noktası çok pahalı olabilir veya sürücü yazılımının doğru çalışması için geleneksel semantiklere uyması gerekebilir. Bu durumlarda, **/volatile: MS** anahtarını kullanabilirsiniz; Bununla birlikte, ARM hedeflerinde geleneksel geçici semantiğini yeniden oluşturmak için derleyicinin, bir değişkenin her okuma veya yazma çevresinde **`volatile`** , performansı olumsuz etkileyecek bir etkisi olabilen, bir değişken için her okuma veya yazma sırasında bellek engelleri eklemesi gerekir.

X86 ve x64 mimarilerinde, MSVC kullanılarak bu mimarilerin zaten oluşturulmuş olduğu yazılımların çoğu için **/volatile: MS** varsayılandır. X86 ve x64 programları derlerken, geleneksel geçici semantiklere gereksiz bir şekilde güvenilmesini ve taşınabilirliği yükseltmeyi önlemeye yardımcı olmak için **/volatile: iso** anahtarını belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++’ı ARM işlemciler için yapılandırma](configuring-programs-for-arm-processors-visual-cpp.md)
