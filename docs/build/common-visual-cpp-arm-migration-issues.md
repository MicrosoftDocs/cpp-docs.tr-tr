---
title: Genel Visual C++ ARM Geçiş Sorunları
ms.date: 05/06/2019
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
ms.openlocfilehash: 2c29b4ffa5344b309622314970ce52c47a0ebd05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328805"
---
# <a name="common-visual-c-arm-migration-issues"></a>Genel Visual C++ ARM Geçiş Sorunları

Microsoft C++ derleyicisini (MSVC) kullanırken, aynı C++ kaynak kodu ARM mimarisinde x86 veya x64 mimarilerinde olduğundan farklı sonuçlar üretebilir.

## <a name="sources-of-migration-issues"></a>Göç sorunlarının kaynakları

X86 veya x64 mimarilerinden ARM mimarisine kod geçirdiğinizde karşılaşabileceğiniz birçok sorun, tanımlanmamış, uygulama tanımlı veya tanımlanmamış davranışı çağırabilecek kaynak kodu yapıları ile ilişkilidir.

*Tanımlanmamış davranış,* C++ standardının tanımlamadığı davranıştır ve bunun nedeni makul bir sonucu olmayan bir işlemdir: örneğin, kayan nokta değerini imzasız bir tamsayıya dönüştürmek veya bir değeri negatif olan veya tanıtılan türündeki bit sayısını aşan bir dizi pozisyona kaydırmak.

*Uygulama tanımlı davranış,* C++ standardının derleyici satıcısının tanımlamasını ve belgelemasını gerektirdiği davranıştır. Bir program, taşınabilir olmasa da, uygulama tanımlı davranışa güvenle güvenebilir. Uygulama tanımlı davranış örnekleri yerleşik veri türlerinin boyutları ve bunların hizalama gereksinimleri içerir. Uygulama tanımlı davranıştan etkilenebilecek bir işlem örneği değişken bağımsız değişkenler listesine erişmektir.

*Belirtilmeyen davranış,* C++ standardının kasıtlı olarak belirleyici olmayan bıraktığı davranıştır. Davranış deterministik olmayan olarak kabul edilmiştir, ancak belirtilmemiş davranışın özellikle çağrıları derleyici uygulaması tarafından belirlenir. Ancak, bir derleyici satıcısının sonucu önceden belirlemesi veya karşılaştırılabilir çağırmalar arasında tutarlı davranışı garanti etmesi için bir gereklilik yoktur ve belgeleme gereksinimi yoktur. Belirtilmeyen davranışa örnek olarak, işlev çağrısına bağımsız değişkenler içeren alt ifadelerin değerlendirildiği sıradır.

Diğer geçiş sorunları, ARM ve x86 veya C++ standardıyla farklı şekilde etkileşimde olan x64 mimarileri arasındaki donanım farklılıklarına bağlanabilir. Örneğin, x86 ve x64 mimarisinin güçlü `volatile`bellek modeli -nitelikli değişkenlere geçmişte belirli iş parçacıkları arası iletişimi kolaylaştırmak için kullanılan bazı ek özellikler verir. Ancak ARM mimarisinin zayıf bellek modeli bu kullanımı desteklemez ve C++ standardı bunu gerektirmez.

> [!IMPORTANT]
> X86 ve x64'te sınırlı iş parçacıkları iletişimi biçimleri uygulamak için kullanılabilecek bazı özellikler kazansa `volatile` da, bu ek özellikler genel olarak iş parçacıkları arası iletişimi uygulamak için yeterli değildir. C++ standardı, bu tür iletişimin uygun eşitleme ilkelleri kullanılarak uygulanmasını önerir.

Farklı platformlar bu tür davranışları farklı ifade edebileceğinden, yazılımı platformlar arasında taşıma yapmak, belirli bir platformun davranışına bağlı ysa zor ve hataya açık olabilir. Bu tür davranışların çoğu gözlemlenebilir ve kararlı görünebilir, ancak onlara güvenmek en azından taşınabilir değildir ve tanımlanmamış veya belirtilmemiş davranış durumlarında da bir hatadır. Bu belgede belirtilen davranışlara bile güvenilmemelidir ve gelecekteki derleyicilerde veya CPU uygulamalarında değişebilir.

## <a name="example-migration-issues"></a>Örnek geçiş sorunları

Bu belgenin geri kalanı, bu C++ dil öğelerinin farklı davranışlarının farklı platformlarda nasıl farklı sonuçlar üretebileceğini açıklar.

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>Kayan noktanın imzasız bir sasayıya dönüştürülmesi

ARM mimarisinde, kayan nokta değerinin 32 bittamsayıya dönüştürülmesi, kayan nokta değeri tamsedintemsil edebileceği aralığın dışındaysa tamsanın temsil edebileceği en yakın değere doygunluk eder. x86 ve x64 mimarilerinde, isterse imzalanmamışsa veya kisit imzalanmışsa -2147483648 olarak ayarlanmışsa dönüştürme tamamlanır. Bu mimarilerin hiçbiri kayan nokta değerlerinin daha küçük tamsayı türlerine dönüştürülmesini doğrudan desteklemez; bunun yerine, dönüşümler 32 bit olarak gerçekleştirilir ve sonuçlar daha küçük bir boyuta kesilir.

ARM mimarisi için doygunluk ve kesilme birleşimi, imzasız türlere dönüştürmenin 32 bit'lik bir tamsayıyı doygunlaştırdığında daha küçük imzasız türleri doğru şekilde doygunlaştırdığı, ancak daha küçük türdeki ancak tam 32 bit tamsayıyı doygunlaştıramayacak kadar küçük değerler için kesilmiş bir sonuç ürettiği anlamına gelir. Dönüştürme de 32 bit imzalı tamsayılar için doğru doygunluk, ancak doymuş, imzalı tamsonlar doygunluk sonuçları -1 pozitif doymuş değerler için ve 0 negatif doymuş değerler için. Daha küçük imzalı bir tamsayıya dönüştürme, öngörülemeyen kesilmiş bir sonuç üretir.

x86 ve x64 mimarileri için, imzasız tamsayı dönüşümleri için kaydırma davranışı ve taşma üzerinde imzalı tamsayı dönüşümleri için açık değerleme birleşimi, truncation ile birlikte, çok büyükse çoğu vardiyanın sonuçlarını tahmin edilemez hale getirir.

Bu platformlar, NaN (Not-a-Number) tamsayı türlerine dönüşüm lerini nasıl ele aldıkları konusunda da farklılık gösterir. ARM'da NaN 0x0000000'e dönüşür; x86 ve x64 üzerinde, 0x80000000 dönüştürür.

Kayan nokta dönüştürme, yalnızca değerin dönüştürülmekte olduğu tümsedo türünün aralığında olduğunu biliyorsanız güvenilebilir.

### <a name="shift-operator---behavior"></a>Shift işleci ( >>)\< \< davranışı

ARM mimarisinde, desen tekrarlamaya başlamadan önce bir değer sola veya sağa 255 bit'e kaydırılabilir. x86 ve x64 mimarilerinde desen, desenin kaynağı 64 bitlik bir değişken olmadığı sürece 32'nin her iki katında tekrarlanır; bu durumda, desen x64 üzerinde 64 her katını ve bir yazılım uygulaması istihdam x86, her 256 her kat. Örneğin, 32 pozisyon ile sola kaydırılan 1 değeri olan 32 bitlik bir değişken için ARM'da sonuç 0, x86'da sonuç 1 ve x64'te sonuç da 1'dir. Ancak, değerin kaynağı 64 bitlik bir değişkense, her üç platformdaki sonuç 4294967296'dır ve x64'te 64 veya ARM ve x86'da 256 pozisyon kaydırılana kadar değer "sarma"dır.

Kaynak türündeki bit sayısını aşan bir kaydırma işleminin sonucu tanımlı olmadığından, derleyicinin her durumda tutarlı bir davranışa sahip olması gerekmez. Örneğin, bir değişikliğin her iki operand'ı derleme zamanında biliniyorsa, derleyici, vardiyanın sonucunu önceden hesaplamak ve sonra vardiya işlemi yerine sonucu değiştirmek için bir iç yordam kullanarak programı optimize edebilir. Vardiya miktarı çok büyük veya negatifse, iç yordamın sonucu CPU tarafından yürütülen aynı kaydırma ifadesinin sonucundan farklı olabilir.

### <a name="variable-arguments-varargs-behavior"></a>Değişken bağımsız değişkenler (varargs) davranışı

ARM mimarisinde, yığına geçirilen değişken bağımsız değişkenler listesindeki parametreler hizalamaya tabidir. Örneğin, 64 bit lik bir parametre 64 bit lik bir sınırda hizalanır. x86 ve x64'te, yığına geçirilen bağımsız değişkenler hizalamaya tabi değildir ve sıkıca paketlenir. Bu fark, x86 veya `printf` x64 mimarilerinde bazı değerlerin bir alt kümesi için çalışsa bile, değişken bağımsız değişkenler listesinin beklenen düzeni tam olarak eşleşmiyorsa, ARM'da dolgu olarak tasarlanan bellek adreslerini okumak gibi değişken bir işleve neden olabilir. Bu örneği göz önünde bulundurun:

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will "parse" the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

Bu durumda, hata, bağımsız değişkenin hizalanması nın dikkate alınması için doğru biçim belirtiminin kullanıldığından emin olarak düzeltilebilir. Bu kod doğrudur:

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>Bağımsız değişken değerlendirme sırası

ARM, x86 ve x64 işlemciler çok farklı olduğundan, derleyici uygulamaları için farklı gereksinimler ve optimizasyonlar için farklı fırsatlar sunabilirler. Bu nedenle, çağrı kuralı ve en iyi duruma getirici ayarları gibi diğer etkenlerle birlikte, derleyici işlev bağımsız değişkenlerini farklı mimarilerde veya diğer etkenler değiştiğinde farklı bir sırada değerlendirebilir. Bu, belirli bir değerlendirme emrine dayanan bir uygulamanın davranışının beklenmedik şekilde değişmesine neden olabilir.

Bu tür bir hata, bir işleve yapılan bağımsız değişkenlerin aynı çağrıdaki işlevdeki diğer bağımsız değişkenleri etkileyen yan etkileri olduğunda oluşabilir. Genellikle bu tür bağımlılıklardan kaçınmak kolaydır, ancak bazen ayırt edilmesi zor olan bağımlılıklar veya operatör aşırı yüklemesi tarafından engellenebilir. Bu kod örneğini göz önünde bulundurun:

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

Bu iyi tanımlanmış gibi görünür, `*` ancak aşırı yüklü işleçler varsa, `->` bu kod buna benzeyen bir şeye çevrilir:

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

Ve arasında `operator->(memory_handle)` bir bağımlılık `operator*(p)`varsa, kod, özgün kod olası bir bağımlılık yokmuş gibi görünse de, belirli bir değerlendirme emrine güvenebilir.

### <a name="volatile-keyword-default-behavior"></a>geçici anahtar kelime varsayılan davranışı

MSVC derleyicisi, derleyici `volatile` anahtarlarını kullanarak belirtebileceğiniz depolama niteleyicisinin iki farklı yorumunu destekler. [/volatile:ms](reference/volatile-volatile-keyword-interpretation.md) anahtarı, bu mimariler üzerindeki güçlü bellek modeli nedeniyle x86 ve x64 için geleneksel durumda olduğu gibi, güçlü sıralama garanti Microsoft genişletilmiş uçucu semantik seçer. [/volatile:iso](reference/volatile-volatile-keyword-interpretation.md) anahtarı, güçlü sıralamayı garanti etmez katı C++ standart uçucu semantikleri seçer.

ARM mimarisinde, varsayılan **/volatile:iso** çünkü ARM işlemciler zayıf sıralı bellek modeli var ve ARM yazılımı / uçucu genişletilmiş semantiği güvenerek bir mirasa sahip değildir çünkü **/volatile:ms** ve genellikle yok yazılım ile arayüz. Ancak, hala bazen uygun ya da hatta genişletilmiş semantik kullanmak için bir ARM programı derlemek için gerekli. Örneğin, bir programı ISO C++ semantikini kullanmak üzere bağlantı noktasına getirmek çok maliyetli olabilir veya sürücü yazılımının düzgün çalışması için geleneksel semantiklere uyması gerekebilir. Bu gibi durumlarda , **/volatile:ms** anahtarını kullanabilirsiniz; ancak, ARM hedefleri üzerinde geleneksel uçucu semantik yeniden oluşturmak için, derleyici performans üzerinde `volatile` olumsuz bir etkisi olabilir güçlü sıralama uygulamak için her okuma veya yazma bir değişken in etrafında bellek engelleri eklemek gerekir.

x86 ve x64 mimarilerinde varsayılan **/volatile:ms'dir,** çünkü msvc kullanılarak bu mimariler için zaten oluşturulmuş olan yazılımların çoğu bunlara dayanır. X86 ve x64 programlarını derlediğinizde, geleneksel uçucu semantiklere gereksiz güvenmemek ve taşınabilirliği teşvik etmek için **/volatile:iso** anahtarını belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++’ı ARM işlemciler için yapılandırma](configuring-programs-for-arm-processors-visual-cpp.md)
