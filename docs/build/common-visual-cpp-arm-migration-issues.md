---
title: "Genel Visual C++ ARM geçiş sorunları | Microsoft Docs"
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
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bcc34d472fb6db02eb902001ad5aac77dea5baf0
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="common-visual-c-arm-migration-issues"></a>Genel Visual C++ ARM Geçiş Sorunları

Üzerinde x86 veya x64 mimarileri makinelerinden Microsoft Visual C++ (MSVC) kullanırken, aynı C++ kaynak kodu ARM mimariyi farklı sonuçlar doğurabilir.

## <a name="sources-of-migration-issues"></a>Geçiş sorunlarını kaynakları

ARM mimarisi x86 veya x64 mimarileri kod geçirdiğinizde karşılaşabileceğiniz çoğu sorunu tanımlanmamış, uygulama tanımlı veya belirtilmeyen davranışı çağırabilir kaynak kodu yapıları ilişkilidir.

*Tanımsız davranış* C++ Standart tanımlamaz davranıştır ve makul sonuç sahip bir işlem tarafından neden: Örneğin, bir kayan nokta değer imzalanmamış tamsayı dönüştürme veya konum sayısına göre bir değer kaydırma negatif veya yükseltilen türünü bit sayısını aşıyor.

*Uygulama tanımlı davranış* tanımlamak ve belge derleyici satıcı C++ Standart gerektiren bir davranıştır. Bunun nedenle taşınabilir olmayabilir olsa bile bir programın güvenli bir şekilde uygulama tanımlı davranış üzerinde güvenebilirsiniz. Uygulama tanımlı davranış örnekleri yerleşik veri türlerini ve bunların hizalama gereksinimleri boyutları içerir. Uygulama tanımlı davranış tarafından etkilenen bir işlem örneği değişken bağımsız değişken listesi erişiyor.

*Belirtilmeyen davranışı* C++ Standart kasıtlı olarak belirleyici olmayan bırakır davranıştır. Davranış belirleyici değerlendirilir rağmen belirtilmeyen davranışının belirli çağrılarını derleyici uygulaması tarafından belirlenir. Ancak, bir derleyici satıcısının sonucu önceden veya karşılaştırılabilir çağrılarını arasında tutarlı davranışı garanti gereksinimi yoktur ve belgeleri için gereksinimi yoktur. İçinde bir işlev çağrısı için bağımsız değişkenleri dahil, alt ifadelerin değerlendirilme sırasını belirtilmeyen davranışı örnektir.

Diğer geçiş sorunları donanım farklılıkları ARM ve C++ Standart farklı etkileşim x86 veya x64 mimarileri için öznitelikli. Örneğin, x86 hem x64 mimarisi güçlü bellek modelinin verir `volatile`-değişkenleri belirli türde geçmişte arası iş parçacığı iletişimi kolaylaştırmak için kullanılan bazı ek özellikler tam. Ancak bu ARM mimarisi 's zayıf bellek modelini desteklemez ve C++ Standart ihtiyacı yoktur.

> [!IMPORTANT]
>  Ancak `volatile` arası iş parçacığı iletişimin sınırlı forms x86 hem x64, bu ek özellikler uygulamak için kullanılan bazı özellikleri uygulamak için yeterli değil kazançlar arası iş parçacığı iletişimi genel. C++ Standart uygun eşitleme temelleri yerine kullanarak bu tür bir iletişim uygulanması önerir.

Farklı platformlarda bu tür davranış farklı express çünkü yazılım platformları arasında taşıma zor ve hataya yatkın belirli bir platformun davranışını bağımlı olması durumunda olabilir. Çoğu bu tür davranış gözlenen ve kararlı görünebilir, ancak bunlar üzerinde bağlı olan en az olmayan taşınabilir ve tanımlanmamış veya belirtilmeyen davranışı durumlarda da bir hata. Bile bu belgede Alıntı yapılan davranışı üzerinde kullanılmamalıdır ve gelecekte derleyicileri veya CPU uygulamaları değiştirebilirsiniz.

## <a name="example-migration-issues"></a>Örnek geçiş sorunları

Bu belgenin kalan nasıl bu C++ dil öğeleri farklı davranışını farklı platformlarda farklı sonuçlar üretebilir açıklar.

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>İmzasız tamsayı, kayan nokta dönüşümü

ARM mimarisi üzerinde bir 32 bit tamsayı kayan noktalı bir sayıyı dönüştürülmesi kayan nokta değeri tamsayı gösterebilir aralığının dışında olması durumunda, tamsayı gösterebilir en yakın değere dolduruyor. Tamsayı imzasız veya tamsayıyı imzalanmışsa -2147483648 için ayarlanmışsa x86 hem x64 mimarileri dönüştürme çevresinden kaydırılır. Bu mimarileri hiçbiri doğrudan kayan nokta değerlerini dönüştürme küçük tamsayı türleri için destek; Bunun yerine, dönüştürmeleri için 32 bit gerçekleştirilir ve sonuçlar daha küçük bir boyuta kesilir.

ARM mimarisi için bir 32 bit tamsayı dolduruyor ancak büyük değerler için kesilmiş bir sonuç üretir imzasız türler dönüştürme küçük imzasız türler doğru dolduruyor Doygunluk ve kesme birleşimi anlamına gelir daha küçük türü çok küçük tam 32 bit tamsayı saturate için temsil edebilir. Dönüştürme de doğru için 32-bit imzalı tamsayılar dolduruyor ancak doymuş, imzalı tamsayılar kesilmesi olumlu doygunluğa sahip değerleri -1 ve olumsuz doygunluğa sahip değerleri için 0 ile sonuçlanır. Bir küçük işaretli tamsayıyı dönüştürme tahmin edilemez kesilmiş bir sonuç oluşturur.

X86 hem x64 mimari için döner işaretsiz tamsayı dönüştürmeleri için davranış ve kesme, birlikte taşan imzalı tamsayı dönüştürmeleri için açık değerleme birleşimi yapmak çoğu kaydırmalar için sonuçları olmaları durumunda tahmin edilemez çok büyük.

Bu platformlar bunlar tamsayı türleri NaN (bir sayı değil) dönüştürülmesi nasıl işleneceğini içinde farklılık gösterir. ARM üzerinde NaN için 0x00000000 dönüştürür; x86 hem x64 üzerinde 0x80000000 için dönüştürür.

Değer tamsayı türünde için dönüştürülüyor aralıkta olduğunu biliyorsanız, kayan nokta dönüşümü yalnızca üzerinde dayanıyordu.

### <a name="shift-operator---behavior"></a>Kaydırma işleci (\< \< >>) davranışı

Desen başlamadan önce sola veya sağa en çok 255 BITS ARM mimarisi üzerinde bir değer gölgeye. Bir 64-bit değişken deseni kaynağı olmadığı sürece x86 hem x64 mimarileri üzerinde her 32 birden çok düzeni yinelenir; Bu durumda, x 64 ve her bir yazılım uygulaması burada işe x86 üzerinde 256 katları 64 her katları adresindeki düzeni tekrarlar. Örneğin, 32 konumlar tarafından sol gölgeye 1 değerine sahip 32-bit bir değişken, ARM üzerinde sonuç 0'dır, üzerinde x86 sonucu 1. ve üzerinde x64 sonucu de 1. Ancak, kaynak değeri bir 64-bit değişken ise, tüm üç platformlarda sonuç 4294967296 olur ve "64 konumlar x64 veya ARM üzerinde 256 konumlar ve x86 değişme kadar değeri sarma değil".

Kaynak türü bit sayısını aşıyor shift işleminin sonucu tanımsız olduğundan, derleyicinin tüm durumlarda tutarlı davranışı sağlamak için gerekli değildir. Bir kaydırma hem işlenenleri derleme zamanında biliniyorsa, örneğin, derleyici program shift sonucunu önceden hesaplar için bir iç yordamı kullanarak ve kaydırma işlemi yerine sonuç değiştirerek en iyi duruma. Shift tutar çok büyük ya da negatif sayı ise, iç yordamı sonucunu CPU tarafından yürütülen gibi farklı aynı shift ifadenin sonucu olabilir.

### <a name="variable-arguments-varargs-behavior"></a>Değişken bağımsız değişkenler (varargs) davranışı

ARM mimarisi üzerinde yığında geçirilen değişken bağımsız değişkenleri listesinden tabi hizalama parametreleridir. Örneğin, bir 64-bit parametresi bir 64-bit sınırında hizalanır. X86 hem x64 üzerinde yığında geçirilen bağımsız değişkenler hizalama ve paketi tabi sıkı bir şekilde değildir. Bu farkı variadic işlevi gibi neden olabilir `printf` değişken bağımsız değişken listesinin beklenen düzenini tam olarak eşleşmiyorsa x86 üzerinde bazı değerler bir kısmı için çalışabilir olsa bile, ARM doldurma olarak düşünülmemiştir bellek adresleri okunamıyor veya x64 mimarileri. Bu örneği göz önünde bulundurun:

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will “parse” the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

Bu durumda, hatayı doğru biçim belirtimi kullanılır sağlayarak giderilip giderilemeyeceğini böylece hizalama bağımsız değişken olarak kabul edilen. Bu kod doğrudur:

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>Bağımsız değişken değerlendirme sırası

Çünkü x 86 ve x64 ARM işlemcileri çok farklı, derleyici uygulamaları ve aynı zamanda başka fırsatları iyileştirmeler için farklı gereksinimleri sunabilir. Bu nedenle, arama kuralı ve en iyi duruma getirme ayarları gibi diğer faktörlere birlikte bir derleyici işlev bağımsız değişkenleri farklı mimari veya diğer etkenlere ne zaman değiştirildiğini farklı bir düzende değerlendirebilir. Bu, beklenmedik bir şekilde değiştirmek için belirli değerlendirme sırası üzerinde güvenen bir uygulamanın davranışı neden olabilir.

Bir işlev bağımsız değişkenleri aynı çağrı işlevi için başka bir bağımsız değişken etkisi yan etkileri varsa bu tür bir hata oluşabilir. Genellikle bu tür bir bağımlılığı kaçınmak kolaydır, ancak, bazen keşfedilir zor olan bağımlılıkları veya İşleç aşırı yüklemesi tarafından görünmeyebilir. Bu kod örneği göz önünde bulundurun:

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

Bu iyi tanımlanmış görünür ancak `->` ve `*` bu kodu bu benzer bir şey için çevrilir sonra aşırı yüklenmiş işleçler şunlardır:

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

Ve arasında bir bağımlılık ise `operator->(memory_handle)` ve `operator*(p)`kodu üzerinde belirli değerlendirme sırası bağlı, özgün kod gibi görünse de olası bir bağımlılık yoktur.

### <a name="volatile-keyword-default-behavior"></a>volatile anahtar sözcüğü varsayılan davranışı

MSVC derleyici, iki farklı yorumlar destekleyen `volatile` derleyici anahtarları kullanarak belirtebilirsiniz depolama niteleyicisi. [/Volatile:ms](../build/reference/volatile-volatile-keyword-interpretation.md) anahtar x86 hem x64 geleneksel bu durum güçlü bellek modelini bu mimariyi temel nedeniyle bırakıldı gibi güçlü sıralamasını, garanti volatile semantiği genişletilmiş Microsoft seçer. [/Volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) anahtar güçlü sıralama garanti etmez katı C++ Standart volatile semantiği seçer.

ARM mimarisine varsayılandır **/volatile:iso** ARM işlemcileri zayıf bir bellek modeli sıralı olduğundan ve ARM yazılım üzerinde Genişletilmiş semantiği bağlı olan eski sahip olmadığından **/volatile:ms**  ve genellikle yok mu yazılım ile arabirim oluşturmak için. Ancak, yine bazen uygun ya da Genişletilmiş semantiğini kullanmak için bir ARM programı derlemek için bile gerekli değildir. Örneğin, ISO C++ semantiğini kullanmak için bir program bağlantı noktasına pahalı olabilir veya sürücü yazılımı düzgün çalışması için geleneksel semantiğini bağlı olması olabilir. Bu durumlarda, kullandığınız **/volatile:ms** anahtar; ancak, geleneksel volatile semantiğini ARM hedeflerde yeniden oluşturmak için derleyici her okuma veya yazma işlemini geçici bellek engelleri eklemelisiniz bir `volatile` zorlamak için değişken Güçlü sıralama, performansı olumsuz etkileyebilir sahip.

X86 hem x64 mimarileri varsayılandır **/volatile:ms** MSVC kullanarak bu mimari için zaten oluşturuldu yazılımın çoğu üzerlerinde kullandığından. X86 hem x64 programlar derlerken belirtebilirsiniz **/volatile:iso** anahtarı geleneksel volatile semantiğini gereksiz bağımlılık önlemeye yardımcı olmak ve taşınabilirlik yükseltmek için.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++’ı ARM işlemciler için yapılandırma](../build/configuring-programs-for-arm-processors-visual-cpp.md)  
