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

Geçerli RSP adresinin ötesinde tüm bellek geçici olarak değerlendirilir: işletim sistemi veya hata ayıklayıcı, Kullanıcı hata ayıklama oturumu sırasında bu belleğin üzerine yazabilir veya bir kesme işleyicisi olabilir. Bu nedenle, bir yığın çerçevesinin değerlerini okumaya veya yazmaya çalışmadan önce RSP her zaman ayarlanmalıdır.

Bu bölümde yerel değişkenler için yığın alanının ayrılması ve **alloca** iç sürümü ele alınmaktadır.

## <a name="stack-allocation"></a>Yığın ayırma

Bir işlevin girişi, yerel değişkenler, kayıtlı Yazmaçları, yığın parametreleri ve kayıt parametreleri için yığın alanı ayırmaktan sorumludur.

Parametre alanı her zaman yığının en altında (kullanılsa bile `alloca` ), her zaman herhangi bir işlev çağrısı sırasında dönüş adresine bitişik olacak. En az dört giriş içerir, ancak çağrılabilir herhangi bir işlev için gereken tüm parametreleri tutmak için yeterli alan yok. Parametrelerin kendileri hiçbir zaman yığına bağlı olmasa bile, kayıt parametreleri için alanın her zaman ayrıldığını unutmayın; çağrılan, alanın tüm parametreleri için ayrıldığı garantisi verir. Kayıt bağımsız değişkenleri için giriş adresleri gereklidir, böylece çağrılan işlevin bağımsız değişken listesinin adresini (va_list) veya bağımsız bir bağımsız değişkeni alması gerektiğinde bitişik bir alanın kullanılabilir olması gerekir. Bu alan Ayrıca, dönüştürücü yürütme sırasında kayıt bağımsız değişkenlerini kaydetmek için uygun bir yer sağlar ve bir hata ayıklama seçeneği olarak (örneğin, giriş kodundaki ana adreslerinde depolandıklarında, hata ayıklama sırasında bağımsız değişkenleri bulmayı kolaylaştırır). Çağrılan işlev 4 ' ten az parametreye sahip olsa da, bu 4 yığın konumları çağrılan işleve etkin bir şekilde sahip olur ve parametre kayıt değerlerini kaydetme yanı sıra çağrılan işlev tarafından başka amaçlar için de kullanılabilir.  Bu nedenle, çağıran bir işlev çağrısında bu yığın bölgesinde bilgi kaydedemez.

Bir işlevde bir boşluk dinamik olarak`alloca`ayrılmışsa (), yığın bölümünün temelini işaretlemek için bir çerçeve işaretçisi olarak kalıcı kayıt kullanılmalıdır ve bu kayıt giriş bölümünde kaydedilip başlatılmalıdır. `alloca` Kullanıldığında, aynı çağırandan aynı çağrılan çağrıların, kayıt parametreleri için farklı giriş adreslerine sahip olabileceğini unutmayın.

Yığın, giriş (örneğin, dönüş adresi gönderildikten sonra) ve belirli bir çerçeve işlevleri sınıfı için [Işlev türlerinde](#function-types) belirtilen durumlar dışında, her zaman 16 baytlık hizalanmış bir şekilde korunur.

Aşağıda, işlev A 'nın yaprak olmayan bir işlevi çağırdığı bir yığın düzenine örnek verilmiştir. Işlev A 'nın girişi, yığının en altında B için gereken tüm yazmaç ve yığın parametreleri için zaten alan ayırmıştır. Çağrı, dönüş adresini ve B 'nin giriş alanını, yerel değişkenleri, kalıcı yazmaçları ve işlevleri çağırmak için gereken alanı ayırır. B kullanılıyorsa `alloca`, yerel değişken/kalıcı kayıt kaydetme alanı ve parametre yığın alanı arasında alan ayrılır.

![AMD dönüştürme örneği](../build/media/vcamd_conv_ex_5.png "AMD dönüştürme örneği")

B işlevi başka bir işlevi çağırdığında, dönüş adresi RCX giriş adresinin hemen altına gönderilir.

## <a name="dynamic-parameter-stack-area-construction"></a>Dinamik parametre yığın alanı oluşturma

Bir çerçeve işaretçisi kullanılıyorsa, parametre yığın alanını dinamik olarak oluşturmak için seçeneği vardır. Bu, şu anda x64 derleyicisinde yapılmamaktadır.

## <a name="function-types"></a>İşlev türleri

Temel olarak iki tür işlev vardır. Yığın çerçevesini gerektiren bir işleve *çerçeve işlevi*denir. Yığın çerçevesi gerektirmeyen bir işleve *yaprak işlevi*denir.

Çerçeve işlevi, yığın alanı ayıran, diğer işlevleri çağıran, kalıcı kayıtları kaydeden veya özel durum işlemeyi kullanan bir işlevdir. Ayrıca bir işlev tablosu girişi gerektirir. Çerçeve işlevi, giriş ve bitiş gerektirir. Çerçeve işlevi, yığın alanı dinamik olarak ayırabilir ve bir çerçeve işaretçisi kullanabilir. Çerçeve işlevi, bu çağrıyı yapan standart 'nin elden çıkarılmasında tam yeteneklere sahiptir.

Bir çerçeve işlevi başka bir işlevi çağırmıyorsa, yığını hizalamak gerekmez (bölüm [yığını ayırmada](#stack-allocation)başvurulur).

Yaprak işlev, işlev tablosu girişi gerektirmeyen bir işlevdir. RSP de dahil olmak üzere herhangi bir kalıcı kayıt üzerinde değişiklik yapamaz, bu da hiçbir işlevi çağıramayacağı veya yığın alanı ayıramayacağı anlamına gelir. Yürütülürken yığının hizalanmamış olmasına izin verilir.

## <a name="malloc-alignment"></a>malloc hizalaması

[malloc](../c-runtime-library/reference/malloc.md) , temel hizalaması olan ve ayrılan bellek miktarına uyalabilen herhangi bir nesneyi depolamak için uygun şekilde hizalı belleği döndürecek şekilde garanti edilir. *Temel hizalama* , bir hizalama belirtimi olmadan uygulamanın desteklediği en büyük hizalamadan küçük veya ona eşit olan hizalamadır. (Visual C++, bu, veya 8 bayt için `double`gerekli olan hizalamadır. 64 bitlik platformları hedefleyen kodda 16 bayttır.) Örneğin, dört baytlık bir ayırma dört baytlık veya daha küçük bir nesneyi destekleyen bir sınır üzerinde hizalanabilir.

Visual C++, daha *fazla hizalanmış* türler olarak da bilinen, *genişletilmiş hizalaması*olan türlere izin verir. Örneğin, SSE türü [__m128](../cpp/m128.md) ve `__m256`ve `__declspec(align( n ))` ' `n` nin 8 ' den büyük olduğu, genişletilmiş hizalamadır. Genişletilmiş hizalama gerektiren bir nesne için uygun olan bir sınır üzerindeki bellek hizalaması tarafından `malloc`garanti edilmez. Fazla hizalanmış türler için bellek ayırmak üzere [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) ve ilgili işlevleri kullanın.

## <a name="alloca"></a>alloca

[_alloca](../c-runtime-library/reference/alloca.md) , 16 baytlık hizalanmış ve ek olarak bir çerçeve işaretçisi kullanmak için gereklidir.

Ayrılan yığının, [yığın ayırma](#stack-allocation)bölümünde anlatıldığı gibi, daha sonra çağrılan işlevlerin parametreleri için öğesinden sonra boşluk eklemesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)
