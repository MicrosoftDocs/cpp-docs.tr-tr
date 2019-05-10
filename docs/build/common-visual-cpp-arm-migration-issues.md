---
title: Genel Visual C++ ARM Geçiş Sorunları
ms.date: 05/06/2019
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
ms.openlocfilehash: 78d87000240acd394edf823a778ae29060c6d09c
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220887"
---
# <a name="common-visual-c-arm-migration-issues"></a>Genel Visual C++ ARM Geçiş Sorunları

Microsoft kullanırken C++ derleyici (MSVC) aynı C++ kaynak kodu, ARM mimarisi üzerinde farklı sonuçlar üretebilir, x86 veya x64 mimarilerde gösterilenden.

## <a name="sources-of-migration-issues"></a>Geçiş sorunlarını kaynakları

ARM mimarisi için x86 veya x64 mimarilerin arasından kod geçirdiğinizde karşılaşabileceğiniz çok sayıda sorunu tanımlanmamış, uygulama tanımlı veya belirtilmeyen davranışı çağırabilir kaynak kodu yapıları için ilgilidir.

*Tanımsız davranış* C++ Standart tanımlamaz, davranıştır ve makul hiçbir sonucu olan bir işlem tarafından neden: Örneğin, bir kayan nokta değeri işaretsiz tamsayıya dönüştürmek veya konumlarını sayısına göre bir değer değiştirme negatif veya yükseltilen tür bit sayısını aşıyor.

*Uygulama tanımlı davranış* tanımlamak ve belge derleyici tedarikçisi C++ Standart gerektiren bir davranıştır. Bunu yaptığınızda bu nedenle taşınabilir olmayabilir rağmen bir programın güvenli bir şekilde uygulama tanımlı davranış üzerinde güvenebilirsiniz. Uygulama tanımlı davranış örnekleri, hizalama gereksinimlerinin yerleşik veri türleri ve boyutları içerir. Uygulama tanımlı davranış tarafından etkilenebilecek bir işlem örneği değişken bağımsız değişkenler listesi erişir.

*Belirtilmeyen davranışı* C++ Standart kasıtlı olarak belirleyici bırakır, davranıştır. Davranış belirleyici olarak kabul edilir olsa da, belirtilmeyen davranışının belirli çağrılarını derleyici uygulaması tarafından belirlenir. Ancak, bir derleyici tedarikçisi sonucu önceden veya karşılaştırılabilir çağrıları arasında tutarlı davranışı garantilemek için bir gereksinimi yoktur ve belgeler için bir gereksinimi yoktur. Bir işlev çağrısı için bağımsız değişken içeren alt ifadelerin değerlendirilme sırasını belirtilmeyen davranışı örneğidir.

Diğer geçiş sorunları, ARM ve C++ standardı ile farklı şekilde etkileşime x86 veya x64 mimarileri donanım farklılıkları ilişkilendirilebildiği. Örneğin, güçlü bellek modeli x86 ve x64 mimarisinin verir `volatile`-değişkenleri belirli bir türdeki iş parçacıkları arası iletişim geçmişte kolaylaştırmak için kullanılan bazı ek özellikleri nitelenmiş. Ancak bu kullanım ARM mimarisinin zayıf bellek modeli desteklemiyor ya da C++ Standart gerekli olmadığı.

> [!IMPORTANT]
>  Ancak `volatile` x86 ve x64, bu ek özellikleri üzerinde sınırlı forms iş parçacıkları arası iletişim uygulamak için kullanılan bazı özellikleri uygulamak yeterli değil kazançlar arası iş parçacığı iletişim genel. C++ standardına uygun eşitleme temellerine kullanarak bu tür bir iletişim uygulanması önerir.

Farklı platformlar bu tür davranış farklı express çünkü platformlar arasında yazılım taşıma zor ve hata yapmaya açık belirli bir platformun davranışa bağlıysa olabilir. Bu tür davranış birçoğu gösterilebilir ve kararlı görünebilir ancak bunlar üzerinde bağlı olan en az taşınabilir değildir ve davranışı tanımlanmamış veya belirtilmeyen durumlarda, aynı zamanda bir hatadır. Bile bu belgede alıntı davranışı üzerinde kullanılmamalıdır ve derleyicilerini veya CPU uygulamaları gelecekte değişebilir.

## <a name="example-migration-issues"></a>Örnek geçiş sorunları

Bu belgenin geri kalan nasıl bu C++ dil öğeleri farklı bir davranış farklı platformlarda farklı sonuçlar üretebilir açıklar.

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>İşaretsiz tamsayı, kayan nokta dönüştürme

ARM mimarisini temel bir kayan nokta değerine dönüştürülmesi 32-bit tamsayı, kayan nokta değeri bir tamsayı temsil edebilen aralığı dışında ise bir tamsayı temsil edebilen en yakın değere dolduruyor. Tamsayı imzasız ya da işaretli bir tamsayı, -2147483648 ile ayarlanır x86 ve x64 mimarilerde dönüştürme etrafında sarmalar. Bu mimarileri hiçbiri kayan nokta değerlerine dönüştürme küçük tamsayı türleri için doğrudan desteği: Bunun yerine, 32 bit dönüştürmeler gerçekleştirilir ve sonuçları daha küçük bir boyuta kesilir.

ARM mimarisi için bir 32 bit tamsayı dolduruyor ancak daha büyük değerler için kısaltılmış bir sonuç işaretsiz türlere dönüşüm için doğru küçük imzasız türler dolduruyor Doygunluk ve kesme birleşimi anlamına gelir daha küçük tür çok küçük tam 32-bit tamsayı saturate için temsil edebilir. Dönüştürme de doğru için 32-bit imzalı tamsayı dolduruyor ancak olumlu doygun değerleri için -1 ve 0 olumsuz doygun değerler için kesme doymuş, imzalı tamsayı sonuçlanır. Bir küçük işaretli tamsayıya dönüştürme tahmin edilemez kesilmiş bir sonuç üretir.

X86 ve x64 mimarileri için işaretsiz tamsayı dönüştürmeleri davranışını döner ve kesilmesi, birlikte taşmada işaretli tamsayı dönüştürmeleri için açık değerleme hale çoğu kaydırmalar sonuçları olmaları durumunda öngörülemeyen çok büyük.

Aşağıdaki platformları tamsayı türleri NaN (bir sayı değil) dönüştürülmesi işledikleri olarak nasıl farklılık gösterir. ARM üzerinde NaN için 0x00000000 dönüştürür; x86 ve x64 0x80000000 için dönüştürür.

Değer aralığı için dönüştürülüyor tamsayı türünün içinde olduğunu biliyorsanız, kayan nokta dönüştürme yalnızca yararlandı.

### <a name="shift-operator---behavior"></a>Kaydırma işleci (\< \< >>) davranışı

Desen başlamadan önce ARM mimarisine bir değer sola veya sağa en çok 255 bit kaydırılmasına. Bir 64-bit değişken desen kaynağı olmadığı sürece x86 ve x64 mimarilerde 32 her birden çok desen yinelenir; Bu durumda, her 64 x 64 ve her bir yazılım uygulamasını nerede işe x86, 256 katları katları adresindeki deseni tekrarlar. Örneğin, 32 konumları tarafından sola kaydırılacak 1 değeri olan bir 32-bit değişken için ARM üzerinde sonucu 0'dır, üzerinde x86 sonuç 1'dir ve üzerinde x64 sonucu da 1. Ancak, kaynak değeri bir 64-bit değişken ise 4294967296 üç tüm platformlarda sonuç olur ve "64 konumları x64 veya ARM 256 konumlarda ve x86 değişmiştir kadar değer sarma değil".

Kaynak türü bit sayısı aşan bir kaydırma işleminin sonucu tanımsız olduğundan, derleyici her durumda tutarlı bir davranış sağlamak için gerekli değildir. Bir kaydırma her iki işleneni de derleme zamanında biliniyorsa, örneğin, derleyici program shift sonucunu önceden hesaplar için bir iç yordamı kullanarak ve ardından sonucu kaydırma işlemi yerine değiştirerek en iyi duruma. Değiştirme miktarı çok büyük veya negatif ise, iç yordamı sonucunu CPU tarafından yürütülen gibi farklı aynı kaydırma ifadesinin sonucu olabilir.

### <a name="variable-arguments-varargs-behavior"></a>Değişken bağımsız değişkenler (varargs) davranışı

ARM mimarisini temel yığın üzerine geçirilir değişken bağımsız değişken listesinden tabi hizalama parametreleridir. Örneğin, bir 64-bit parametresi bir 64-bit sınırında hizalanır. X86 ve x64, bağımsız değişkenler yığında geçirilir hizalama ve paketi tabi sıkı bir şekilde değildir. Bu fark, değişen sayıda bağımsız değişken işlev gibi neden olabilir `printf` değişken bağımsız değişken listesinin beklenen düzenini tam olarak eşleşmiyorsa x86 üzerinde bazı değerlerin bir alt kümesi için bu işe yarayabilir olsa da, ARM doldurma olarak hedeflenen bellek adresleri okunamıyor veya x64 mimariler. Bu örneği göz önünde bulundurun:

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will “parse” the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

Bu durumda, hatayı hizalama bağımsız değişken olarak kabul edilir, böylece doğru biçim belirtimi kullanılmamasını sağlayarak düzeltilebilir. Bu kod doğrudur:

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>Bağımsız değişken değerlendirme sırası

Çünkü, x 86 ve x64 ARM işlemcileri çok farklı, derleyici uygulamaları ve farklı fırsatları iyileştirmeler için farklı gereksinimler ortaya çıkarabilir. Bu nedenle, çağırma kuralı ve iyileştirme ayarları gibi diğer etkenler birlikte bir derleyici işlev bağımsız değişkenleri farklı mimari veya diğer etkenler ne zaman değiştirildiğini farklı bir sırada değerlendirebilir. Bu, beklenmedik bir şekilde değiştirmek için belirli bir değerlendirme sırası üzerinde bağımlı bir uygulamanın davranış şekli neden olabilir.

Bağımsız değişken bir işleve diğer bağımsız değişkenler aynı çağrı işlevine etkileyen yan etkileri varsa bu türde bir hata oluşabilir. Genellikle bu tür bir bağımlılık kaçınmak kolaydır, ancak, bazen elde edilmesi güç olan bağımlılıkların veya İşleç aşırı yüklemesi görünmeyebilir. Bu kod örneği göz önünde bulundurun:

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

Bu, iyi tanımlanmış görünür ancak `->` ve `*` sonra bu kodu bu benzeyen bir şey için çevrilir aşırı yüklenmiş işleçler şunlardır:

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

Ve arasında bir bağımlılık ise `operator->(memory_handle)` ve `operator*(p)`, kodu belirli bir değerlendirme sırasını bağlı olabilir, özgün koda benzer olsa da olası hiçbir bağımlılık yoktur.

### <a name="volatile-keyword-default-behavior"></a>volatile anahtar sözcüğü varsayılan davranışı

MSVC derleyicisi, iki farklı ınterpretations destekler `volatile` depolama niteleyicisi, derleyici anahtarlarını kullanarak belirtebilirsiniz. [/Volatile:ms](reference/volatile-volatile-keyword-interpretation.md) anahtar, Microsoft geleneksel durum x86 hem x64 nedeniyle bu mimarilerde güçlü bellek modeli olduğu güçlü sıralama, garanti geçici semantiği genişletilmiş seçer. [/Volatile:iso](reference/volatile-volatile-keyword-interpretation.md) anahtar, güçlü sıralama garanti etmez katı C++ Standart geçici semantiklerini seçer.

ARM mimarisini temel varsayılandır **/volatile:iso** bellek modeli sıralı ARM işlemcileri sahipli sahip olduğundan ve ARM yazılım üzerinde Genişletilmiş semantiği bağlı olan, eski olmadığından **/volatile:ms**  ve genellikle yok mu yazılım ile arabirim oluşturmak için. Ancak, yine de bazı durumlarda kullanışlı ya da bir ARM programın genişletilmiş semantiğini kullanmasına derlemek için bile gerekli değildir. Örneğin, ISO C++ semantiği kullanılacak bir program bağlantı noktasına pahalı olabilir veya yazılımı düzgün çalışması için geleneksel semantiği kullanan gerekebilir. Bu gibi durumlarda, kullandığınız **/volatile:ms** ancak ARM hedefleri geleneksel geçici semantiği yeniden oluşturmak için derleyici her bir okuma veya yazma etrafında belleği engelleri eklemeniz gerekir; anahtar bir `volatile` zorlamak için değişkeni Güçlü sıralama, tera negatif bir etkiye performans.

X86 ve x64 mimarilerde varsayılandır **/volatile:ms** MSVC kullanarak bu mimari için önceden oluşturulmuş yazılım çoğunu bunlara bağımlı olduğundan. X86 ve x64 programları derlediğinizde, belirtebileceğiniz **/volatile:iso** geleneksel geçici semantiği gereksiz güvenme önlemeye yardımcı olmak ve taşınabilirlik yükseltmek için anahtar.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++’ı ARM işlemciler için yapılandırma](configuring-programs-for-arm-processors-visual-cpp.md)
