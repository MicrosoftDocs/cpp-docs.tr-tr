---
title: En iyi uygulamaları iyileştirme
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
ms.openlocfilehash: 67a071ecd457495510b2015f05466e1aa9bfc989
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477356"
---
# <a name="optimization-best-practices"></a>En iyi uygulamaları iyileştirme

Bu belgede, Visual C++'ta iyileştirme için bazı en iyi uygulamalar açıklanmaktadır.

## <a name="compiler-and-linker-options"></a>Derleyici ve bağlayıcı seçenekleri

### <a name="profile-guided-optimization"></a>Profil temelli iyileştirme

Visual C++ destekler *profil temelli iyileştirme* (PGO). Bu iyileştirme uygulamasının daha sonraki iyileştirme sürücü için profil verileri eğitim yürütmeleri uygulamanın belgelenmiş bir sürümünü kullanır. PGO kullanılarak zaman alıcı olabilir, böylece her geliştiricinin kullanan bir şey olmayabilir, ancak bir ürün için son sürüm yapılandırması PGO kullanmanızı öneririz. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../../build/reference/profile-guided-optimizations.md).

Ayrıca, *tüm Program iyileştirmesi* (bağlama zamanı kod oluşturmayı de bildiği) ve **/O1** ve **/O2** iyileştirmeleri geliştirildi. Genel olarak, aşağıdaki seçeneklerden birini ile derlenen bir uygulamayı aynı uygulamanın daha önceki bir derleyici ile derlenmiş kıyasla daha hızlı olacaktır.

Daha fazla bilgi için [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) ve [/O1, / O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).

### <a name="which-level-of-optimization-to-use"></a>Hangi düzeyde kullanmak için en iyi duruma getirme

Bu tamamen Mümkünse, son yayın derlemeleri profil destekli iyileştirmeler ile derlenmelidir. İzleme eklenmiş çalışan veya senaryolarına erişimi olmaması için yetersiz altyapı olmadığını nedeniyle PGO ile oluşturmak mümkün değilse, ardından tüm Program iyileştirmesi ile yapı öneririz.

**/Gy** anahtar da çok yararlıdır. Başvurulmayan comdat'ları ve COMDAT'ı kaldırmak için söz konusu olduğunda, bağlayıcı daha fazla esneklik sağlayan ayrı COMDAT her işlevin oluşturur Katlama. Tek dezavantajı kullanarak **/Gy** olduğundan bu sorunları hata ayıklarken neden olabilir. Bu nedenle, bu genellikle bunu kullanmak için önerilir. Daha fazla bilgi için [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md).

64-bit ortamlarında bağlamak için kullanılacak önerilir **/OPT: ref, ICF** bağlayıcı seçeneği ve 32-bit ortamlarda **/OPT: ref** önerilir. Daha fazla bilgi için [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md).

En iyi duruma getirilmiş sürüm yapıları olsa da, hata ayıklama sembolleri oluşturmak için de önemle tavsiye edilir. Oluşturulan kodun efekt değil ve çok, uygulamanızın hata ayıklaması daha kolay olması sağlar.

### <a name="floating-point-switches"></a>Kayan nokta anahtarları

**; /OP &** derleyici seçeneği kaldırıldı ve kayan nokta iyileştirmelerini ile ilgili aşağıdaki dört derleyici seçenekleri eklendi:

|||
|-|-|
|**/ FP: precise**|Bu varsayılan öneri ve çoğu durumda kullanılmalıdır.|
|**Fast**|Performans örneğin oyunlarda dayanıklılığı ise önerilir. Bu hızlı performans neden olur.|
|**/ FP: strict**|Önerilen if kesin bir kayan nokta özel durumlarını ve IEEE istenen davranışı. Bu, en yavaş performans neden olur.|
|**/ FP: except [-]**|İle birlikte kullanılabilir **/FP: strict** veya **/FP: precise**, ama **Fast**.|

Daha fazla bilgi için [FP (Floating-Point davranışını belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).

## <a name="optimization-declspecs"></a>En iyi duruma getirme declspecs

Bu bölümde biz programlarında performans yardımcı olmak için kullanılabilecek iki declspecs sırasında görünür: `__declspec(restrict)` ve `__declspec(noalias)`.

`restrict` Declspec yalnızca gibi bir işaretçi döndüren işlev bildirimlerine uygulanabilir `__declspec(restrict) void *malloc(size_t size);`

`restrict` Declspec unaliased işaretçileri döndüren işlevler kullanılır. Bu anahtar sözcük C çalışma zamanı kitaplığı uygulaması için kullanılan `malloc` bu yana hiçbir zaman (belleği serbest bırakılmış sonra kullanma gibi geçersiz bir şey yapmakta olduğunuz sürece) zaten kullanılmakta olan geçerli programda bir işaretçi değeri döndürür.

`restrict` Declspec derleyici derleyici iyileştirmelerini gerçekleştirmeye yönelik daha fazla bilgi sağlar. Sığdırıp belirlemek bir derleme için bir diğer işaretçilerin hangi işaretçileri diğer adıdır ve büyük ölçüde bu bilgileri kullanarak derleyici yardımcı olur.

Bunu belirtmemiz Bu derleyici derleyici doğrular sorun değil promise olmasıdır. Programınızı kullanıyorsa `restrict` declspec uygunsuz bir şekilde, programınız yanlış davranışa sahip olabilir.

Daha fazla bilgi için [kısıtlama](../../cpp/restrict.md).

`noalias` Declspec de yalnızca işlevlere uygulanır ve işlev yarı saf işlev olduğunu gösterir. Yarı saf işlev başvuruyor veya yalnızca yerel öğeler, bağımsız değişkenler ve bağımsız değişkenlerin birinci düzey yöneltmeye değiştirir biridir. Bu declspec derleyici için bir vaattir ve işlev globals başvurur veya işaretçi bağımsız değişkenler ardından derleyici ikinci düzey yöneltmeye kod oluşturmak için kullanabileceğiniz, uygulamanın keser.

Daha fazla bilgi için [noalias](../../cpp/noalias.md).

## <a name="optimization-pragmas"></a>En iyi duruma getirme pragmaları

Kodu En İyileştir yardımcı olmak için birkaç faydalı pragmaları vardır. Ele ilki `#pragma optimize`:

```cpp
#pragma optimize("{opt-list}", on | off)
```

Bu pragma işlev tarafından işlevi olarak verilen iyileştirme düzeyini ayarlamanıza olanak tanır. Bu kullanarak için belirli bir işlevi iyileştirme ile derlendiğinde, uygulamanızın nerede kilitleniyor idealdir. Bu, tek bir işlev için iyileştirmeler devre dışı bırakmak için kullanabilirsiniz:

```cpp
#pragma optimize("", off)
int myFunc() {...}
#pragma optimize("", on)
```

Daha fazla bilgi için [en iyi duruma getirme](../../preprocessor/optimize.md).

Satır içi derleyici gerçekleştiren ve burada size bu davranışı değiştirmek yardımcı pragmaları birkaç hakkında konuşmak en önemli iyileştirmeler biridir.

`#pragma inline_recursion` Satır içi Özyinelenen çağrı için uygulama isteyip istemediğinizi belirtmek için kullanışlıdır. Varsayılan olarak kapalı. Küçük işlevlerin yüzeysel özyineleme için bunu etkinleştirin olabilir. Daha fazla bilgi için [inline_recursion](../../preprocessor/inline-recursion.md).

Derinliğini sınırlamak için başka bir kullanışlı pragma yapılmış olan `#pragma inline_depth`. Bu genellikle bir programı veya işlev boyutunu sınırlamak için burada çalıştığınız durumlarda yararlı olur. Daha fazla bilgi için [inline_depth](../../preprocessor/inline-depth.md).

## <a name="restrict-and-assume"></a>__restrict ve \__assume

Birkaç performans yardımcı olabilecek Visual c++ anahtar sözcükleri: [__restrict](../../cpp/extension-restrict.md) ve [__assume](../../intrinsics/assume.md).

İlk olarak, unutulmamalıdır, `__restrict` ve `__declspec(restrict)` iki farklı şey vardır. Biraz ilgili olsa da, semantiği farklıdır. `__restrict` gibi bir tür niteleyicisi olan `const` veya `volatile`, ancak yalnızca işaretçi türleri için.

Değiştirilen bir işaretçi `__restrict` şeklinde adlandırılan bir *işaretçi __restrict*. __Restrict işaretçisi aracılığıyla yalnızca erişilebilir bir işaretçidir \__restrict işaretçi. Diğer bir deyişle, başka bir işaretçi tarafından işaret verilere erişmek için kullanılamaz \__restrict işaretçi.

`__restrict` Visual C++ iyileştirici yönelik güçlü bir araç olması, ancak çok dikkatli kullanın. İyileştirici, düzensiz kullandıysanız, uygulamanızın çalışmamasına neden bir iyileştirme gerçekleştirebilir.

`__restrict` Anahtar sözcüğü değiştirir **/Oa** önceki sürümlerden geçiş yapın.

İle `__assume`, bir geliştirici bazı değişkeninin değeri hakkında varsayımlar yapmak için derleyici söyleyebilirsiniz.

Örneğin `__assume(a < 5);` iyileştirici, bu değişkeni kod satırında söyler `a` değerinden 5'tir. Yeniden derleyici promise budur. Varsa `a` gerçekten 6 Bu noktada programdaki sonra derleyici optimize sahip sonra programın davranışını beklediğiniz olmayabilir. `__assume` Switch deyimleri ve/veya koşullu ifadeler önce en yararlı olur.

Bazı sınırlamalar vardır `__assume`. İlk olarak, ister `__restrict`, yalnızca bir öneri, derleyici, bu nedenle, bunu yoksaymak için ücretsiz. Ayrıca, `__assume` şu anda yalnızca değişken inequalities sabitleri karşı çalışır. Sembolik inequalities, örneğin, dağıtılmaz assume(a < b).

## <a name="intrinsic-support"></a>İç desteği

Yapı içleri olan işlevi burada derleyici iç bilgileri çağrı sahip ve bir kitaplıkta bir işlevi çağırmak yerine, söz konusu işlevin kodu yayan çağırır. Üst bilgi dosyası \<intrin.h > her desteklenen donanım platformları için tüm kullanılabilir yapı içlerini içerir.

Yapı içleri Programcı bütünleştirilmiş kod kullanmak zorunda kalmadan derin koda gitme olanağı sunar. Kullanarak yapı içleri çeşitli avantajları vardır:

- Kodunuzun daha taşınabilir olduğundan. Birkaç yapı içlerini birden çok CPU mimarileri üzerinde kullanılabilir.

- Kodunuzu kod hala C/C++'da yazılmış bu yana okumak kolaydır.

- Kodunuz, derleyici iyileştirmeleri avantajı alır. Derleyici, daha iyi ettiği kod oluşturma için yapı içlerini artırır.

Daha fazla bilgi için [derleyici iç bilgileri](../../intrinsics/compiler-intrinsics.md).

## <a name="exceptions"></a>Özel Durumlar

Bir performansın isabet özel durumlar kullanma ile ilişkili. Bazı kısıtlamalar, derleyici belirli iyileştirmelerde gerçekleştirmesini engelle try blokları kullanırken sunulmuştur. Üzerinde x86 blokları, kod yürütme sırasında oluşturulan ek durum bilgilerini nedeniyle ek performansta azalmaya karşı yoktur platformları deneyin. 64-bit platformlarda deneyin bloklar çok performansı düşürebilir değil, ancak bir özel durum sonra işleyici bulma ve yığın geriye doğru izleme işlemini pahalı olabilir.

Bu nedenle, gerçekten olarak gerekmeyen koda try/catch blokları önlemek için önerilir. Zaman uyumlu özel durumları, özel durumlar kullanmanız gerekiyorsa, mümkünse kullanın. Daha fazla bilgi için [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).

Son olarak, yalnızca olağanüstü durumlar için özel durumlar. Özel durumlar için genel denetim akışı kullanarak, performans düşebilir büyük olasılıkla bir hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu İyileştirme](../../build/reference/optimizing-your-code.md)
