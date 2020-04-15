---
title: En iyi uygulamaları iyileştirme
ms.date: 05/06/2019
helpviewer_keywords:
- C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
ms.openlocfilehash: 541114b4cbf7d3d063e48b50ab265b4c95c6237c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328447"
---
# <a name="optimization-best-practices"></a>En iyi uygulamaları iyileştirme

Bu belge, Visual Studio'da C++ programlarını optimize etmek için en iyi bazı uygulamaları açıklar.

## <a name="compiler-and-linker-options"></a>Derleyici ve Bağlayıcı Seçenekleri

### <a name="profile-guided-optimization"></a>Profil güdümlü optimizasyon

Visual Studio *profil güdümlü optimizasyonu* (PGO) destekler. Bu optimizasyon, uygulamanın daha sonra optimizasyonunu sağlamak için bir uygulamanın araçlı sürümünün eğitim yürütmelerinden elde edilen profil verilerini kullanır. PGO kullanmak zaman alıcı olabilir, bu nedenle her geliştiricinin kullandığı bir şey olmayabilir, ancak bir ürünün son sürüm yapısı için PGO kullanmanızı öneririz. Daha fazla bilgi için [Profil Destekli Optimizasyonlar'a](profile-guided-optimizations.md)bakın.

Buna ek olarak, *Tüm Program Optimizasyonu* (Bağlantı Zaman Kodu Oluşturma olarak da bilir) ve **/ O1** ve **/ O2** optimizasyonları geliştirilmiştir. Genel olarak, bu seçeneklerden biriyle derlenen bir uygulama, önceki bir derleyiciyle derlenen aynı uygulamadan daha hızlı olacaktır.

Daha fazla bilgi için bkz: [/GL (Tüm Program Optimizasyonu)](reference/gl-whole-program-optimization.md) ve [/O1, /O2 (Boyutu En Aza Indirin, Hızı En Üst Düzeye Çıkarın)](reference/o1-o2-minimize-size-maximize-speed.md).

### <a name="which-level-of-optimization-to-use"></a>Hangi optimizasyon düzeyi kullanılacak

Mümkünse, son sürüm oluşturmaları Profil Destekli Optimizasyonlar ile derlenmelidir. PGO ile inşa etmek mümkün değilse, ister enstrümantize yapılar çalıştırmak için yetersiz altyapı nedeniyle olsun veya senaryolara erişimi olmayan, o zaman tüm program optimizasyonu ile bina öneririz.

**/Gy** anahtarı da çok yararlıdır. Her işlev için ayrı bir COMDAT oluşturur ve referanssız COMDAT'ları ve COMDAT katlamalarını kaldırma konusunda bağlayıcıya daha fazla esneklik sağlar. **/Gy** kullanmanın tek dezavantajı hata ayıklama yaparken sorunlara neden olmasıdır. Bu nedenle, genellikle kullanılması tavsiye edilir. Daha fazla bilgi için bkz: [/Gy (İşlev Düzeyi Bağlamayı Etkinleştir)](reference/gy-enable-function-level-linking.md).

64 bit ortamlarda bağlantı için **/OPT:REF,ICF** bağlayıcı seçeneğinin kullanılması ve 32 bit ortamlarda **/OPT:REF** önerilir. Daha fazla bilgi için bkz: [/OPT (Optimizasyonlar)](reference/opt-optimizations.md).

Ayrıca, en iyi duruma getirilmiş sürüm yapılarında bile hata ayıklama sembolleri oluşturulması önerilir. Oluşturulan kodu etkilemez ve gerekirse uygulamanızı hata ayıklamayı çok daha kolay hale getirir.

### <a name="floating-point-switches"></a>Kayan nokta anahtarları

**/Op** derleyici seçeneği kaldırıldı ve kayan nokta optimizasyonlarıyla ilgili aşağıdaki dört derleyici seçeneği eklendi:

|||
|-|-|
|**/fp:hassas**|Bu varsayılan öneridir ve çoğu durumda kullanılmalıdır.|
|**/fp:hızlı**|Örneğin oyunlarda performans son derece önemliyse önerilir. Bu en hızlı performans ile sonuçlanır.|
|**/fp:sıkı**|Hassas kayan nokta özel durumları ve IEEE davranışı isteniyorsa önerilir. Bu, en yavaş performansla sonuçlanır.|
|**/fp:hariç[-]**|**/fp: strict** veya **/fp:precise**ile birlikte kullanılabilir, ama **/fp:fast**değil .|

Daha fazla bilgi için bkz: [/fp (Kayan Nokta Davranışı Belirt)](reference/fp-specify-floating-point-behavior.md).

## <a name="optimization-declspecs"></a>Optimizasyon declspecs

Bu bölümde performansa yardımcı olmak için programlarda kullanılabilecek iki declspecs bakacağız: `__declspec(restrict)` ve `__declspec(noalias)`.

`restrict` Declspec yalnızca bir işaretçi döndüren işlev bildirimlerine uygulanabilir, örneğin`__declspec(restrict) void *malloc(size_t size);`

`restrict` Declspec, başka bir işaretçi döndüren işlevlerde kullanılır. Bu anahtar kelime, geçerli programda zaten `malloc` kullanılmakta olan bir işaretçi değerini asla döndürmeyeceği için (serbest bırakıldıktan sonra bellek kullanmak gibi yasadışı bir şey yapmıyorsanız) C-Runtime Kitaplığı uygulaması için kullanılır.

`restrict` Declspec derleyici optimizasyonları gerçekleştirmek için daha fazla bilgi verir. Bir derleyicinin belirleyebilmek için en zor şeylerden biri, diğer işaretçilerin diğer işaretçiler olarak diğer işaretçilerolarak hangilerini işaretçiye yardımcı olduğudur ve bu bilgileri kullanmak derleyiciye büyük ölçüde yardımcı olur.

Bu derleyici için bir söz değil, derleyici doğrulayacak bir şey olduğunu işaret değer. Programınız bu `restrict` declspec'i uygunsuz şekilde kullanıyorsa, programınız yanlış davranışa sahip olabilir.

Daha fazla bilgi için [bkz.](../cpp/restrict.md)

`noalias` Declspec da yalnızca işlevlere uygulanır ve işlevin yarı saf bir işlev olduğunu gösterir. Yarı saf işlev, yalnızca yerel halkalar, bağımsız değişkenler ve bağımsız değişkenlerin birinci düzey yönlendirmelerine başvuruyapan veya değiştiren işlevdir. Bu declspec derleyici için bir sözdür ve işlev globals veya işaretçi bağımsız değişkenlerinin ikinci düzey yönler başvurur, derleyici uygulamayı tatili kodu oluşturabilir.

Daha fazla bilgi için [noalias'a](../cpp/noalias.md)bakın.

## <a name="optimization-pragmas"></a>Optimizasyon pragmas

Kodu optimize etmeye yardımcı olmak için birkaç yararlı pragma da vardır. İlk `#pragma optimize`tartışacağız:

```cpp
#pragma optimize("{opt-list}", on | off)
```

Bu pragma, belirli bir optimizasyon düzeyini işlev bazında ayarlamanızı sağlar. Bu, belirli bir işlev optimizasyonuyla derlendiğinde uygulamanızın çöktüğü nadir durumlar için idealdir. Bunu, tek bir işlev için optimizasyonları kapatmak için kullanabilirsiniz:

```cpp
#pragma optimize("", off)
int myFunc() {...}
#pragma optimize("", on)
```

Daha fazla bilgi için [en iyi duruma getirme](../preprocessor/optimize.md)bilgisine bakın.

Inlining derleyici gerçekleştirir ve burada bu davranışı değiştirmek yardımcı pragmlar bir çift hakkında konuşmak en önemli optimizasyonlar biridir.

`#pragma inline_recursion`uygulamanın özyinelemeli bir çağrıyı satır labilmesini isteyip istemediğinibelirtmek için yararlıdır. Varsayılan olarak kapalıdır. Küçük işlevlerin sığ özyinelemesi için bunu açabilirsiniz. Daha fazla bilgi için [inline_recursion](../preprocessor/inline-recursion.md)bakın.

Inlining derinliğini sınırlamak için başka bir `#pragma inline_depth`yararlı pragma olduğunu . Bu genellikle bir programın veya işlevin boyutunu sınırlamaya çalıştığınız durumlarda yararlıdır. Daha fazla bilgi için [inline_depth.](../preprocessor/inline-depth.md)

## <a name="__restrict-and-__assume"></a>__restrict \_ve _assume

Visual Studio'da performansa yardımcı olabilecek birkaç anahtar kelime vardır: [__restrict](../cpp/extension-restrict.md) ve [__assume.](../intrinsics/assume.md)

İlk olarak, bu `__restrict` unutulmamalıdır ve `__declspec(restrict)` iki farklı şeylerdir. Onlar biraz ilgili olsa da, onların semantik farklıdır. `__restrict`gibi `const` bir `volatile`tür niteleyici, ancak işaretçi türleri için özel.

Değiştirilen `__restrict` bir *işaretçiye __restrict işaretçisi*denir. __restrict işaretçisi, yalnızca _restrict işaretçisi \_aracılığıyla erişilebilen bir işaretçidir. Başka bir deyişle, \_başka bir işaretçi _restrict işaretçi tarafından işaret edilen verilere erişmek için kullanılamaz.

`__restrict`Microsoft C++ optimize edicisi için güçlü bir araç olabilir, ancak büyük bir özenle kullanın. Yanlış kullanılırsa, en iyi duruma getirici uygulamanızı bozacak bir optimizasyon gerçekleştirebilir.

Anahtar `__restrict` kelime önceki sürümlerden **/Oa** anahtarının yerini alır.

Bununla `__assume`birlikte, bir geliştirici derleyiciye bazı değişkenin değeri hakkında varsayımlarda bulunmasını söyleyebilir.

Örneğin, `__assume(a < 5);` en iyi duruma getiriciye bu `a` kod satırında değişkenin 5'ten küçük olduğunu söyler. Yine bu derleyici için bir sözdür. Programda bu noktada aslında 6 ise, `a` derleyici en iyi duruma getirildikten sonra programın davranışı beklediğiniz gibi olmayabilir. `__assume`ifadeleri ve/veya koşullu ifadeleri değiştirmeden önce en yararlı olandır.

Bazı sınırlamalar `__assume`vardır . İlk olarak, gibi `__restrict`, sadece bir öneri, bu nedenle derleyici bunu göz ardı etmek ücretsizdir. Ayrıca, `__assume` şu anda sabitlere karşı değişken eşitsizlikler sadece çalışır. Sembolik eşitsizlikleri yaymaz, örneğin, varsaymak (a < b).

## <a name="intrinsic-support"></a>Intrinsic destek

İçsel bilgiler, derleyicinin çağrı hakkında içsel bilgiye sahip olduğu işlev çağrılarıdır ve kitaplıktaki bir işlevi çağırmak yerine, bu işlev için kod yayır. Üstbilgi dosyası \<intrin.h> desteklenen donanım platformlarının her biri için kullanılabilir tüm içsellikleri içerir.

İçsel olarak programcıya derleme kullanmak zorunda kalmadan kodun derinliklerine inme olanağı verir. Içsel kullanmanın çeşitli faydaları vardır:

- Kodunuz daha taşınabilir. Birçok içsel lik birden çok CPU mimarisinde kullanılabilir.

- Kod hala C/C++'da yazıldığından, kodunuzu okumak daha kolaydır.

- Kodunuz derleyici optimizasyonlarından yararlanır. Derleyici iyileştikçe, içselkod oluşturma geliştirir.

Daha fazla bilgi için [Derleyici Intrinsics'e](../intrinsics/compiler-intrinsics.md)bakın.

## <a name="exceptions"></a>Özel durumlar

Özel durumlar kullanılarak ilişkili bir performans isabeti vardır. Derleyicinin belirli optimizasyonları gerçekleştirmesini engelleyen try blokları kullanılarak bazı kısıtlamalar getirilir. x86 platformlarında, kod yürütme sırasında oluşturulması gereken ek durum bilgileri nedeniyle try bloklarından ek performans bozulması vardır. 64 bit platformlarda, try blokları performansı çok düşürmez, ancak bir özel durum atıldığında, işleyiciyi bulma ve yığını gevşetme işlemi pahalı olabilir.

Bu nedenle, gerçekten gerekmeyen kodiçine try/catch blokları nın getirilmesini önlemesi önerilir. Özel durumlar kullanmanız gerekiyorsa, mümkünse senkron özel durumlar kullanın. Daha fazla bilgi için bkz: [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md).

Son olarak, yalnızca istisnai durumlar için özel durumlar atın. Genel denetim akışı için özel durumlar kullanmak büyük olasılıkla performansın zarar alacaktır.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu İyileştirme](optimizing-your-code.md)
