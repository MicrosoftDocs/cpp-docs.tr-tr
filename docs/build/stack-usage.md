---
title: x64 yığın kullanımı
ms.date: 12/17/2018
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: b598c33fbdd56630ca3e5ef0da551f38a73baa26
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335539"
---
# <a name="x64-stack-usage"></a>x64 yığın kullanımı

RSP'nin geçerli adresidışındaki tüm bellek geçici olarak kabul edilir: İşletim sistemi veya hata ayıklayıcı, kullanıcı hata ayıklama oturumu sırasında bu belleğin üzerine veya kesme işleyicisi üzerine yazabilir. Bu nedenle, RSP her zaman bir yığın çerçeve değerleri okumaya veya yazmaya çalışmadan önce ayarlanmalıdır.

Bu bölümde yerel değişkenler ve **alloca** içsel için yığın alanı tahsisi anlatılmaktadır.

## <a name="stack-allocation"></a>Yığın ayırma

Bir işlevin prolog yerel değişkenler, kaydedilen kayıtlar, yığın parametreleri ve kayıt parametreleri için yığın alanı ayırmak için sorumludur.

Parametre alanı her zaman yığının en altındadır `alloca` (kullanılsa bile), böylece herhangi bir işlev çağrısı sırasında her zaman iade adresine bitişik olur. En az dört giriş içerir, ancak çağrılabilecek herhangi bir işlevin gerektirdiği tüm parametreleri tutmak için her zaman yeterli alan içerir. Parametrelerin kendileri yığına hiç yer vermese bile, her zaman kayıt parametreleri için alan ayrılacağını unutmayın; bir callee tüm parametreleri için alan tahsis edilmiştir garanti edilir. Çağrılan işlevin bağımsız değişken listesinin (va_list) adresini veya bağımsız bir bağımsız değişkenin adresini alması gerektiğinden, kayıt bağımsız değişkenleri için ev adresleri gereklidir. Bu alan ayrıca thunk yürütme sırasında ve hata ayıklama seçeneği olarak kayıt bağımsız değişkenleri kaydetmek için uygun bir yer sağlar (örneğin, bu sürüm kodu kendi ev adreslerinde depolanır eğer hata ayıklama sırasında bağımsız değişkenleri bulmak kolaylaştırır). Çağrılan işlev4'ten az parametreye sahip olsa bile, bu 4 yığın konumu çağrılan işlevin etkin bir şekilde sahip olduğu ve parametre kayıt değerlerini kaydetmenin yanı sıra başka amaçlar için çağrılan işlev tarafından kullanılabilir.  Bu nedenle arayan, bu yığın bölgesindeki bilgileri işlev çağrısı boyunca kaydedemeyebilir.

Bir işlevde boşluk dinamik`alloca`olarak ayrılmışsa ( ) ise, yığının sabit bölümünün tabanını işaretlemek için geçici olmayan bir kayıt kullanılmalıdır ve bu kayıt prolog'a kaydedilmeli ve başolarak başlatılmalıdır. Kullanıldığında, `alloca` aynı arayandan aynı callee'ye yapılan aramaların kayıt parametreleri için farklı ev adresleri olabileceğini unutmayın.

Yığın, prolog içinde (örneğin, iade adresi itildikten sonra) ve belirli bir çerçeve işlevi sınıfı için [İşlev Türleri'nde](#function-types) belirtilen durumlar dışında, her zaman 16 bayt hizalanmış olarak korunur.

Aşağıda, A işlevinin yaprak sızbir işlev b. İşlev A prologunu çağırdığı yığın düzenine bir örnek verilmiştir. Çağrı, iade adresini iter ve B'nin prolog'u yerel değişkenleri, geçici olmayan kayıtları ve işlevleri çağırması için gereken alan için alan ayırır. B kullanıyorsa, `alloca`alan yerel değişken/geçici olmayan kayıt kaydetme alanı ile parametre yığını alanı arasında ayrılır.

![AMD dönüşüm örneği](../build/media/vcamd_conv_ex_5.png "AMD dönüşüm örneği")

B işlevi başka bir işlevi aradığında, iade adresi RCX'in ev adresinin hemen altına itilir.

## <a name="dynamic-parameter-stack-area-construction"></a>Dinamik parametre yığın alanı yapısı

Bir çerçeve işaretçisi kullanılırsa, parametre yığını alanını dinamik olarak oluşturmak için seçenek vardır. Bu şu anda x64 derleyicisinde yapılmaz.

## <a name="function-types"></a>İşlev türleri

Temelde iki tür işlev vardır. Yığın çerçevesi gerektiren bir işleve *çerçeve işlevi*denir. Yığın çerçevesi gerektirmeyen bir *işleve yaprak işlevi*denir.

Çerçeve işlevi, yığın alanını ayıran, diğer işlevleri çağıran, geçici olmayan kayıtları kaydeden veya özel durum işleme kullanan bir işlevdir. Ayrıca bir işlev tablosu girişi gerektirir. Çerçeve işlevi bir prolog ve bir epilog gerektirir. Çerçeve işlevi yığın alanını dinamik olarak ayırabilir ve bir çerçeve işaretçisi kullanabilir. Bir çerçeve işlevi emrinde bu arama standardının tam özelliklerine sahiptir.

Bir çerçeve işlevi başka bir işlev çağırmıyorsa, yığını hizalamak gerekmez (Bölüm [Yığını Ayırma'da](#stack-allocation)başvurulan).

Yaprak işlevi, işlev tablosu girişi gerektirmeyen bir işlevdir. RSP de dahil olmak üzere geçici olmayan kayıtlarda değişiklik yapamaz, bu da herhangi bir işlevi arayamaması veya yığın alanı tahsis edilemebileceği anlamına gelir. Yürütülürken yığını hizalanmamış olarak bırakmasına izin verilir.

## <a name="malloc-alignment"></a>malloc hizalama

[malloc,](../c-runtime-library/reference/malloc.md) temel bir hizaya sahip olan ve ayrılan bellek miktarına sığabilecek herhangi bir nesneyi depolamak için uygun şekilde hizalanmış belleği döndürecek şekilde garanti edilir. *Temel hizalama,* hizalama belirtimi olmadan uygulama tarafından desteklenen en büyük hizalamadan daha az veya eşit olan bir hizalamadır. (Visual C++'da bu, bir `double`, veya 8 bayt için gerekli olan hizalamadır. 64 bit platformları hedefleyen kodda, 16 bayt.) Örneğin, dört bayt ayırma, herhangi bir dört bayt veya daha küçük nesneyi destekleyen bir sınırda hizalanır.

Visual C++ *genişletilmiş hizalama*türlerine izin verir ( *aşırı hizalanmış* türler olarak da bilinir). Örneğin, [__m128 sse](../cpp/m128.md) türleri `__m256`ve 8'den büyük `__declspec(align( n ))` `n` olduğu yerlerde kullanılarak bildirilen türler genişletilmiş hizalama yada genişletti. Uzatılmış hizalama gerektiren bir nesne için uygun olan sınırdaki bellek `malloc`hizalaması. Aşırı hizalanmış türler için bellek ayırmak için [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) ve ilgili işlevleri kullanın.

## <a name="alloca"></a>alloca

[_alloca](../c-runtime-library/reference/alloca.md) 16 bayt hizalanmış olması ve ayrıca bir çerçeve işaretçisi kullanması gerekir.

Ayrılan yığın, [Yığın Ayırma'da](#stack-allocation)tartışıldığı gibi, daha sonra çağrılan işlevlerin parametreleri için ondan sonra alan içermesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)
