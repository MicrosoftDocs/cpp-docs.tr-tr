---
title: x64 yığın kullanımı
ms.date: 12/17/2018
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: 3318a3512f83e242496454ffa2dc4aa8d26e1fc3
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627325"
---
# <a name="x64-stack-usage"></a>x64 yığın kullanımı

Tüm geçerli adresi RSP bellekten geçici olarak kabul edilir: İşletim sistemi veya bir hata ayıklayıcı bu bellek kullanıcı hata ayıklama oturumu veya kesinti işleyicisinin sırasında üzerine yazabilir. Bu nedenle, RSP her zaman bir yığın çerçevesine değerleri okunamıyor veya yazılamıyor denemeden önce ayarlanmalıdır.

Bu bölümde, yerel değişkenler için yığın alanı ayırma anlatılmaktadır ve **alloca** iç.

## <a name="stack-allocation"></a>Yığın ayırma

Bir işlevin giriş yığın alanı yerel değişkenler için sorumlu olan, kaydedilmiş yazmaçlar, parametreleri yığın ve parametreleri kaydedin.

Parametre alanı her zaman yığının en altında olduğu (bile `alloca` kullanılır), böylece bu her zaman herhangi bir işlev çağrısı sırasında dönüş adresi için bitişik olacaktır. En az dört girişler içeriyor, ancak tüm parametreleri tutmak için yeterli alan çağrılabilir hiçbir işlev tarafından her zaman gerekli. Parametreleri yığına hiçbir zaman barındırılan olsa bile alan kayıt parametreleri için her zaman ayrılır dikkat edin. bir çağrılan alanı tüm parametreleri için ayrıldı garanti edilir. Bağımsız değişken listesi (va_list) ya da tek bir bağımsız değişken adresini almak çağrılan işlev ihtiyacı ardışık bir alanı kullanılabilir olması, ev adresleri yazmaç bağımsız değişkenleri gereklidir. Bu alan ayrıca kayıt bağımsız değişkenleri dönüştürücü yürütme sırasında ve hata ayıklama seçeneği olarak kaydetmek için uygun bir yer sağlar (örneğin, bağımsız değişkenler ev adreslerini giriş kodu içinde depolanıyorsa hata ayıklama sırasında bulmayı kolaylaştırır). Çağrılan işlev en az 4 parametreleri olsa bile, bu 4 yığın konumlarının etkili bir şekilde çağrılan işlev tarafından sahip olunan ve parametre kayıt değerlerini kaydetme yanı sıra diğer amaçlar için çağrılan işlev tarafından kullanılıyor olabilir.  Bu nedenle arayan bilgileri yığınının bu bölgede bir işlev çağrısı kaydedemeyebilir.

Alan dinamik olarak ayırdığınızda (`alloca`) bir işlevde sonra bir kayıt çerçeve işaretçisi olarak tabanı yığın sabit bir parçası olarak işaretlemek için kullanılmalıdır ve kayıt kaydedildi ve giriş bölümünde başlatıldı. Dikkat edin `alloca` olan kullanıldığında, aynı çağrılan çağrıları aynı kayıt parametreleri için farklı ev adresleri olabilir.

Yığın her zaman 16 baytlık korunur hizalanmış, giriş (örneğin, sonra dönüş adresi gönderilir) ve belirtilen belirtilmediği [işlev türleri](#function-types) çerçeve işlevlerinin belirli bir sınıf için.

Burada A'dan B'ye işlevi giriş yaprak olmayan bir işlev çağrıları işlev yığın düzeni örneği zaten yığının sonuna B için gerekli tüm kayıt ve yığın parametreler için alanı ayırdığı verilmiştir. Çağrının dönüş adresi gönderir ve yerel değişkenleri ve kalıcı kayıtlar işlevleri çağırmak için ihtiyaç duyulan alanı B kullanıcısının giriş alanı ayırır. B kullanıyorsa `alloca`, yerel değişken/kalıcı kayıt kaydetme alanı ve parametre yığın alanı arasında ayrılmış alanı.

![AMD dönüştürme örnek](../build/media/vcamd_conv_ex_5.png "AMD dönüştürme örneği")

Dönüş adresi B işlevi başka bir işlevi çağırdığında, yalnızca aşağıdaki ev adresi RCX için gönderilir.

## <a name="dynamic-parameter-stack-area-construction"></a>Dinamik parametre yığın alanı yapımı

Çerçeve işaretçisini kullandıysanız, dinamik parametre yığın alanı oluşturmak için seçeneği bulunmaktadır. Bu şu anda içinde x64 yapılmadığı derleyici.

## <a name="function-types"></a>İşlev türleri

Temel işlevleri iki tür vardır. Bir yığın çerçevesini gerektiren bir işlev çağrılır bir *çerçeve işlevi*. Bir yığın çerçevesini gerektirmeyen bir işlevi çağrıldığında bir *yaprak işlevi*.

Yığın alanı ayırır, diğer işlevleri çağırır, kalıcı Yazmaçları kaydeder veya özel durum işleme kullanan bir işlev bir çerçeve işlevidir. Ayrıca, bir işlevin tablo girişi gerektirir. Çerçeve işlevi, bir giriş ve bitiş gerektirir. Çerçeve işlevi yığın alanı dinamik olarak ayırabilir ve bir çerçeve işaretçisi tercih edebilirsiniz. Çerçeve işlevi tüm özelliklerini, atma standart çağırma vardır.

Çerçeve işlevi başka bir işlevi çağırmadığı sonra yığın hizalamak için gerekli değildir (bölümünde başvurulan [yığın ayırma](#stack-allocation)).

Bir yaprak işlev bir tablo girişi gerektirmeyen bir işlevdir. Bu, onun tüm işlevler veya yığın alanı ayırmak, yani RSP dahil olmak üzere tüm kalıcı Yazmaçları değişiklik yapamazsınız. Yığın yürütürken hizalanmamış bırakın izin verilir.

## <a name="malloc-alignment"></a>malloc hizalaması

[malloc](../c-runtime-library/reference/malloc.md) temel hizalama ve, olan herhangi bir nesneyi depolamak için ayrılan bellek miktarına uygun olabilecek için uygun şekilde hizalanmış belleğe dönmesi garanti edilir. A *temel hizalama* hizalama belirtimleri olmaksızın uygulamayla desteklenen en geniş hizalamadan küçük veya ona eşit olan hizalamadır. (Visual C++'da, bunun için gerekli olan hizalamadır bir `double`, veya 8 bayt. 64-bit platformları hedefleyen kodda, 16 bayttır.) Örneğin, dört baytlık bir atama dört bayt veya daha küçük bir nesne destekleyen bir sınır üzerinde hizalanabilir.

Visual C++ verir sahip türleri *genişletilmiş hizaya*, olarak da bilinen olduğu *aşırı hizalanmış* türleri. Örneğin SSE türleri [__m128](../cpp/m128.md) ve `__m256`ve kullanılarak bildirilen türler `__declspec(align( n ))` burada `n` 8'den büyükse, genişletilmiş hizaya sahiptir. Genişletilmiş hizalama gerektiren bir nesne için uygun olan bir sınır üzerinde bellek hizalama tarafından garanti edilmez `malloc`. Aşırı hizalanmış türlere bellek ayırmak için kullanmak [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) ve ilgili işlevleri.

## <a name="alloca"></a>alloca

[_alloca](../c-runtime-library/reference/alloca.md) 16 bayt olacak şekilde hizalanmış ve ayrıca bir çerçeve işaretçisi kullanmak için gereklidir.

Ayrılmış yığın alanı sonra daha sonra çağrılan işlevlerin parametreleri için açıklandığı gibi eklemis [yığın ayırma](#stack-allocation).

## <a name="see-also"></a>Ayrıca Bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)