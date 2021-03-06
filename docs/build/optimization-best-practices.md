---
description: 'Daha fazla bilgi edinin: Iyileştirme en iyi uygulamaları'
title: En iyi uygulamaları iyileştirme
ms.date: 05/06/2019
helpviewer_keywords:
- C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
ms.openlocfilehash: 06588225838da3b52216fa0ae3eb51b7538ee58d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179830"
---
# <a name="optimization-best-practices"></a>En iyi uygulamaları iyileştirme

Bu belgede, Visual Studio 'da C++ programlarını iyileştirmek için bazı en iyi yöntemler açıklanmaktadır.

## <a name="compiler-and-linker-options"></a>Derleyici ve bağlayıcı seçenekleri

### <a name="profile-guided-optimization"></a>Profil temelli iyileştirme

Visual Studio *Profil temelli iyileştirme* 'yi (PGO) destekler. Bu iyileştirme, uygulamanın daha sonra en iyi duruma getirilmesini sağlamak için bir uygulamanın belgelenmiş bir sürümünün eğitim yürütmelerinin, profil verilerini kullanır. PGO kullanımı zaman alabilir, bu nedenle her geliştiricinin kullandığı bir şey olmayabilir, ancak ürünün son yayın derlemesi için PGO kullanmanızı öneririz. Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](profile-guided-optimizations.md).

Ayrıca, *tüm program iyileştirmesi* (Ayrıca bağlantı zaman kodu oluşturma olarak da bilir) ve **`/O1`** ve **`/O2`** iyileştirmeleri geliştirildi. Genel olarak, bu seçeneklerden biriyle derlenen bir uygulama, önceki bir derleyici ile derlenen aynı uygulamadan daha hızlı olacaktır.

Daha fazla bilgi için bkz. [ `/GL` (tüm program iyileştirmesi)](reference/gl-whole-program-optimization.md) ve [ `/O1` `/O2` (boyutu en aza indir, hızı Büyüt)](reference/o1-o2-minimize-size-maximize-speed.md).

### <a name="which-level-of-optimization-to-use"></a>Kullanılacak iyileştirme düzeyi

Tüm mümkünse, son yayın derlemeleri profil temelli Iyileştirmeler ile derlenmelidir. PGO ile derleme yapmak mümkün değilse, Araçlı derlemeleri çalıştırmak için yetersiz altyapı veya senaryolara erişim sahibi olmamasından bağımsız olarak, tüm program Iyileştirmesi için oluşturma önerilir.

**`/Gy`** Anahtar da çok yararlı olur. Bu, her bir işlev için ayrı bir COMDAT oluşturur ve bu bağlayıcı, başvurulmayan Comduts ve COMDAT katlamayı kaldırmak için geldiğinde bağlayıcıya daha fazla esneklik sağlar. Kullanmanın tek dezavantajı, **`/Gy`** hata ayıklarken sorun oluşmasına neden olabilir. Bu nedenle, genellikle kullanılması önerilir. Daha fazla bilgi için bkz. [ `/Gy` (Function-Level bağlamayı etkinleştir)](reference/gy-enable-function-level-linking.md).

64 bitlik ortamlarda bağlama için **`/OPT:REF,ICF`** bağlayıcı seçeneğinin kullanılması önerilir ve 32 bit ortamlarda **`/OPT:REF`** önerilir. Daha fazla bilgi için bkz. [/opt (iyileştirmeler)](reference/opt-optimizations.md).

En iyi duruma getirilmiş yayın yapılarla bile hata ayıklama sembolleri oluşturmanız önerilir. Oluşturulan kodu etkilemez ve gerekirse uygulamanızın hatalarını ayıklamanın çok daha kolay olmasını sağlar.

### <a name="floating-point-switches"></a>Kayan nokta anahtarları

**`/Op`** Derleyici seçeneği kaldırılmıştır ve kayan nokta iyileştirmeleriyle ilgili aşağıdaki dört derleyici seçeneği eklenmiştir:

|Seçenek|Açıklama|
|-|-|
|**`/fp:precise`**|Bu, varsayılan öneriden ve çoğu durumda kullanılmalıdır.|
|**`/fp:fast`**|Örneğin, oyunlarda, en önemli öneme sahip olması önerilir. Bu, en yüksek performansa neden olur.|
|**`/fp:strict`**|Kesin kayan nokta özel durumları ve IEEE davranışı isteniyorsa önerilir. Bu, en düşük performansa neden olur.|
|**`/fp:except[-]`**|, Veya ile birlikte kullanılabilir **`/fp:strict`** **`/fp:precise`** **`/fp:fast`** .|

Daha fazla bilgi için bkz. [ `/fp` (Floating-Point davranışını belirtin)](reference/fp-specify-floating-point-behavior.md).

## <a name="optimization-declspecs"></a>İyileştirme declspecs

Bu bölümde, performansa yardımcı olmak için programlarda kullanılabilecek iki declspecs bakacağız: `__declspec(restrict)` ve `__declspec(noalias)` .

`restrict`Declspec, yalnızca bir işaretçi döndüren işlev bildirimlerine uygulanabilir, örneğin`__declspec(restrict) void *malloc(size_t size);`

`restrict`Declspec, diğer adı olmayan işaretçiler döndüren işlevlerde kullanılır. Bu anahtar sözcük, `malloc` ' nin geçerli programda zaten kullanımda olan bir işaretçi değeri döndürmeyeceğinden (örneğin, serbest bırakıldıktan sonra belleği kullanmak gibi), ' ın C çalışma zamanı kitaplığı uygulamasında kullanılır.

`restrict`Declspec derleyici iyileştirmeleri gerçekleştirmek için derleyiciye daha fazla bilgi verir. Bir derleyicinin belirlemek için en zor işlemlerden biri, diğer diğer işaretçiler diğer işaretçilerdir ve bu bilgilerin kullanılması derleyiciye büyük ölçüde yardımcı olur.

Derleyicinin doğrulayabileceği bir şey değil, derleyicinin Promise olduğunu işaret eder. Programınız bu `restrict` declspec uygun şekilde kullanıyorsa, programınızın davranışı yanlış olabilir.

Daha fazla bilgi için bkz. [`restrict`](../cpp/restrict.md).

`noalias`Declspec, yalnızca işlevlerine de uygulanır ve işlevin yarı saf bir işlev olduğunu gösterir. Yarı saf bir işlev, yalnızca Yereller, bağımsız değişkenler ve bağımsız değişkenlerin ilk düzey inyönlerine başvuran veya değiştiren bir işlevdir. Bu declspec, derleyiciye bir taahhüdidir ve işlev, işaretçi bağımsız değişkenlerinin genel veya ikinci düzey yönlerine başvuruyorsa, derleyici uygulamayı kesen bir kod oluşturabilir.

Daha fazla bilgi için bkz. [`noalias`](../cpp/noalias.md).

## <a name="optimization-pragmas"></a>İyileştirme pragmaları

Kodun iyileştirmesine yardımcı olmak için çeşitli yararlı pragmalar da vardır. Tartıştığımız ilk bir ad `#pragma optimize` :

```cpp
#pragma optimize("{opt-list}", on | off)
```

Bu pragma, belirli bir optimizasyon düzeyini işlev işlevi temelinde ayarlamanıza olanak sağlar. Bu, belirli bir işlev iyileştirme ile derlendikten sonra uygulamanızın çöktüğü görülen nadir günler için idealdir. Bu işlemi, tek bir işlev için iyileştirmeleri devre dışı bırakmak için kullanabilirsiniz:

```cpp
#pragma optimize("", off)
int myFunc() {...}
#pragma optimize("", on)
```

Daha fazla bilgi için bkz. [`optimize`](../preprocessor/optimize.md).

Satır içi, derleyicinin gerçekleştirdiği en önemli iyileştirmelerin yanı sıra bu davranışı değiştirmeye yardımcı olan pragmaların her biri hakkında konuşur.

`#pragma inline_recursion` uygulamanın bir özyinelemeli çağrıyı satır içine almak isteyip istemediğinizi belirtmek için yararlıdır. Varsayılan olarak kapalıdır. Küçük işlevlerin basit özyineleme için bunu açabilirsiniz. Daha fazla bilgi için bkz. [`inline_recursion`](../preprocessor/inline-recursion.md).

Intıl derinliğini kısıtlamak için başka bir faydalı pragma `#pragma inline_depth` . Bu, genellikle bir program veya işlevin boyutunu sınırlandırmaya çalıştığınız durumlarda faydalıdır. Daha fazla bilgi için bkz. [`inline_depth`](../preprocessor/inline-depth.md).

## <a name="__restrict-and-__assume"></a>`__restrict` ve `__assume`

Visual Studio 'da performansa yardımcı olabilecek birkaç anahtar sözcük vardır: [__restrict](../cpp/extension-restrict.md) ve [__assume](../intrinsics/assume.md).

İlk olarak, bunun aksi belirtilmedikçe **`__restrict`** `__declspec(restrict)` iki farklı işlem olmalıdır. Bunlar biraz ilişkili olsa da, anlamları farklıdır. **`__restrict`** , veya gibi bir tür niteleyicisi **`const`** , **`volatile`** ancak yalnızca işaretçi türleri için.

İle değiştirilen bir işaretçi **`__restrict`** *__restrict işaretçisi* olarak adlandırılır. __Restrict işaretçi yalnızca _restrict işaretçisi üzerinden erişilebilen bir işaretçisidir \_ . Diğer bir deyişle, _restrict işaretçisi tarafından işaret edilen verilere erişmek için başka bir işaretçi kullanılamaz \_ .

**`__restrict`** , Microsoft C++ iyileştirici için güçlü bir araç olabilir, ancak bunu harika bir şekilde kullanabilirsiniz. Yanlış kullanılırsa, iyileştirici uygulamanızı kesen bir iyileştirme gerçekleştirebilir.

**`__restrict`** Anahtar sözcüğü, **/OA** anahtarının önceki sürümlerden yerini alır.

İle **`__assume`** bir geliştirici, derleyiciye bazı değişkenlerin değeri hakkında varsayımlar yapma konusunda bilgi verebilir.

Örneğin, `__assume(a < 5);` Bu kod satırının değişkenin 5 ' ten küçük olduğunu belirten iyileştiriciye söyler `a` . Bu, derleyicinin taahhüdüne bir değer. `a`Artık programın bu noktasında 6 ' dır, derleyici iyileştirildikten sonra programın davranışı beklemiş olabilir. **`__assume`** , Switch deyimleri ve/veya Koşullu ifadeler öncesinde en yararlı seçenektir.

İçin bazı sınırlamalar vardır **`__assume`** . İlk olarak, gibi **`__restrict`** yalnızca bir öneridir, bu nedenle derleyicinin yok saymaya ücretsizdir. Ayrıca, **`__assume`** Şu anda yalnızca sabitlere göre değişken nitelikleri olan değişkenlerle birlikte çalışıyor. Sembolik nitelikleri (örneğin, bir < b) yaymaz.

## <a name="intrinsic-support"></a>İç destek

İç bilgiler, derleyicinin çağrı hakkında iç bilgi sahibi olduğu ve bir kitaplıktaki bir işlevi çağırmak yerine bu işlev için kod yayar. Üst bilgi dosyası, \<intrin.h> desteklenen her donanım platformlarının her biri için kullanılabilir tüm iç bilgileri içerir.

İç bilgiler, programcıya derlemeyi kullanmak zorunda kalmadan koda derin bir şekilde gidebilme olanağı sağlar. İç bilgileri kullanmanın çeşitli avantajları vardır:

- Kodunuz daha taşınabilir. Birden çok CPU mimarilerinde birçok iç yapı mevcuttur.

- Kod hala C/C++ dilinde yazıldığı için kodunuzun okunması daha kolaydır.

- Kodunuz, derleyici iyileştirmelerinin avantajını alır. Derleyici daha iyi aldığından, iç yapı için kod oluşturma artar.

Daha fazla bilgi için bkz. [derleyici iç](../intrinsics/compiler-intrinsics.md)bilgileri.

## <a name="exceptions"></a>Özel durumlar

Özel durumları kullanmayla ilişkili bir performans okuması vardır. Derleyicinin belirli iyileştirmeleri gerçekleştirmesini önleyen TRY blokları kullanılırken bazı kısıtlamalar ortaya çıkartılır. X86 platformlarında, kod yürütme sırasında oluşturulması gereken ek durum bilgileri nedeniyle TRY bloklarında ek performans düşüşü vardır. 64-bit platformlarda, blokları performansı çok fazla azalmayın, ancak bir özel durum oluşturulduktan sonra, işleyiciyi bulma ve yığını geri sarma süreci pahalı olabilir.

Bu nedenle, try/catch bloklarını gerçekten gerekmeyen koda ulaşmaktan kaçınmak önerilir. Özel durumları kullanmanız gerekiyorsa, mümkünse zaman uyumlu özel durumlar kullanın. Daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md).

Son olarak, yalnızca olağanüstü durumlar için özel durumlar oluşturun. Genel denetim akışı için özel durumların kullanılması büyük olasılıkla performansı etkilemeyecektir.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu iyileştirme](optimizing-your-code.md)
