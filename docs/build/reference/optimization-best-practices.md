---
title: "En iyi uygulamaları iyileştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 74b3ecb413a80fcf0f6de98ee16b75f2d032b123
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="optimization-best-practices"></a>En İyi Uygulamaları İyileştirme
Bu belge Visual C++'ta iyileştirme için bazı en iyi uygulamaları açıklar. Aşağıdaki konular açıklanmaktadır:  
  
-   Derleyici ve bağlayıcı seçenekleri  
  
    -   Profil Temelli İyileştirme  
  
    -   En iyi duruma getirme hangi düzeyde kullanmalıyım?  
  
    -   Kayan nokta anahtarları  
  
-   En iyi duruma getirme Declspecs  
  
-   En iyi duruma getirme pragmaları  
  
-   __restrict ve \__assume  
  
-   İç desteği  
  
-   Özel Durumlar  
  
## <a name="compiler-and-linker-options"></a>Derleyici ve bağlayıcı seçenekleri  
  
### <a name="profile-guided-optimization"></a>Profil Temelli İyileştirme  
 Visual C++ profil temelli iyileştirme (PGO) destekler. Bu iyileştirme belgelenmiş bir uygulama sürümünün son yürütmeleri profil verileri sürücü uygulamasının daha sonraki iyileştirmesi için kullanır. Her geliştiricinin kullanan bir şey olmayabilir şekilde PGO kullanarak zaman alıcı olabilir, ancak bir ürün son yayın derlemesi için PGO kullanmanızı öneririz. Daha fazla bilgi için bkz: [Profile-Guided en iyi duruma getirme](../../build/reference/profile-guided-optimizations.md).  
  
 Ayrıca, bütün Program iyileştirmesi (bağlantı zamanı kodu oluşturma da bilir) ve **/O1** ve **O2** en iyi duruma getirme geliştirilmiştir. Genel olarak, aşağıdaki seçeneklerden birini derlenmiş bir uygulamanın bir önceki derleyicisi ile derlenmiş aynı uygulamanın daha hızlı olacaktır.  
  
 Daha fazla bilgi için bkz: [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) ve [/O1, O2 (boyutu en aza indirmek, hızı en üst düzeye)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
### <a name="which-level-of-optimization-should-i-use"></a>En iyi duruma getirme hangi düzeyde kullanmalıyım?  
 Mümkünse, son sürüm derlemeleri profil temeli iyileştirmeler ile derlenmesi gerekir. Bu izleme eklenmiş derlemeleri çalıştırmak veya senaryoları için erişim olmaması için yetersiz altyapı olup olmadığını nedeniyle PGO ile oluşturmak mümkün değilse, ardından bütün Program iyileştirmesi binada öneririz.  
  
 **/Gy** anahtar da çok yararlıdır. Başvurulmayan COMDATs ve comdat'ı kaldırmak için geldiğinde bağlayıcı daha fazla esneklik sağlayan bir ayrı comdat'ı her işlevin oluşturur Katlama. Kullanarak yalnızca dezavantajı **/Gy** derleme zamanında küçük bir etkisi olabilir. Bu nedenle, bu genellikle kullanmak için önerilir. Daha fazla bilgi için bkz: [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md).  
  
 64-bit ortamlarda bağlama için kullanmak için önerilir **/OPT:REF, ICF** bağlayıcı seçeneği ve 32-bit ortamlarda **/OPT:REF** önerilir. Daha fazla bilgi için bkz: [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md).  
  
 Hata ayıklama sembolleriyle, hatta en iyi duruma getirilmiş sürüm yapıları oluşturmak için de önemle tavsiye edilir. Oluşturulan kod efekt değil ve, varsa, uygulamanızın hatalarını ayıklamak daha kolay çok olması gerekir yapar.  
  
### <a name="floating-point-switches"></a>Kayan nokta anahtarları  
 **/Op** derleyici seçeneği kaldırılmıştır ve noktası iyileştirmeler kayan ile ilgili aşağıdaki dört derleyici seçenekleri eklenmiştir:  
  
|||  
|-|-|  
|**/FP: kesin**|Bu varsayılan öneri ve çoğu durumda kullanılmalıdır.|  
|**/FP:Fast**|Performans örneğin oyunlarda utmost öneme sahip olup olmadığını önerilir. Bu hızlı performans neden olacaktır.|  
|**/FP: katı**|Önerilen IF kesin kayan nokta özel durumlar ve IEEE davranışı istenen. Bu, yavaş performans neden olacaktır.|  
|**/FP: dışındaki [-]**|İle birlikte kullanılan **/fp: katı** veya **/fp: kesin**, ama **/fp:fast**.|  
  
 Daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
## <a name="optimization-declspecs"></a>En iyi duruma getirme Declspecs  
 Bu bölümde biz programlarda performans yardımcı olmak için kullanılan iki declspecs arar: `__declspec(restrict)` ve `__declspec(noalias)`.  
  
 `restrict` Declspec yalnızca bir işaretçi gibi döndüren işlev bildirimlerine uygulanabilir`__declspec(restrict) void *malloc(size_t size);`  
  
 `restrict` Declspec unaliased işaretçiler döndüren işlevlerini kullanılır. Bu anahtar sözcük C çalışma zamanı kitaplığı uygulanması için kullanılan `malloc` bu yana hiçbir zaman (, belleği serbest bırakılmış sonra kullanma gibi geçersiz bir şey yapmakta olduğunuz sürece), geçerli program kullanımda olan bir işaretçi değeri döndürür.  
  
 `restrict` Declspec derleyici derleyici iyileştirmelerini gerçekleştirmeye yönelik daha fazla bilgi sağlar. En zor şeylerden belirlemek bir derleyici için biri hangi işaretçileri diğer diğer işaretçiler ve bu bilgileri büyük ölçüde kullanarak derleyici yardımcı olur.  
  
 Bu işaret eden değerinde bu promise derleyici derleyici doğrular şey değil olmasıdır. Programınızı bu kullanıyorsa `restrict` declspec açamayacağı, programınızı yanlış davranışa sahip olabilir.  
  
 Daha fazla bilgi için bkz: [kısıtlamak](../../cpp/restrict.md).  
  
 `noalias` Declspec yalnızca işlevleri için de geçerli ve işlev yarı saf bir işlevi olduğunu gösterir. Yarı saf işlevi, yalnızca yerel öğeler, bağımsız değişkenleri ve birinci düzey indirections bağımsız değişkenleri değiştirir veya başvuruyor biridir. Promise derleyici bu declspec olduğu ve globals işlevi başvuruyor veya ikinci düzey indirections işaretçi bağımsız değişkenlerini daha sonra derleyici kod oluşturabilirsiniz, uygulama keser.  
  
 Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md).  
  
## <a name="optimization-pragmas"></a>En iyi duruma getirme pragmaları  
 Kodu en iyi duruma yardımcı olmak için birkaç faydalı pragmaları vardır. Aşağıdakiler ele ilk sağlayıcıdır `#pragma optimize`:  
  
```  
#pragma optimize("{opt-list}", on | off)  
```  
  
 Bu pragma bir işlev tarafından işlevi temelinde verilen iyileştirme düzeyini ayarlamanıza olanak sağlar. Bu bu nadir durumlarda için verilen işlevi iyileştirme ile derlendiğinde, uygulamanızın nerede çöküyor idealdir. Bu iyileştirmeler tek bir işlev için devre dışı bırakmak için kullanabilirsiniz:  
  
```  
#pragma optimize("", off)  
int myFunc() {...}  
#pragma optimize("", on)  
```  
  
 Daha fazla bilgi için bkz: [en iyi duruma getirme](../../preprocessor/optimize.md).  
  
 Satır içi kullanım derleyici gerçekleştiren ve burada Biz bu davranışı değiştirmek Yardım pragmaları birkaç hakkında konuşun en önemli iyileştirmeler biridir.  
  
 `#pragma inline_recursion`Satır içi bir özyinelemeli çağrı kullanabilmek için uygulamayı isteyip istemediğinizi belirtmek için kullanışlıdır. Varsayılan olarak, kapalıdır. Kısa işlevleri yüzeysel özyineleme için bunu açmanızı olabilir. Daha fazla bilgi için bkz: [inline_recursion](../../preprocessor/inline-recursion.md).  
  
 Derinliğini sınırlamak için başka bir yararlı pragma satır içi kullanım olduğu `#pragma inline_depth`. Bu genellikle, bir program veya işlevi boyutunu sınırlamak için burada çalıştığınız durumlarda yararlıdır. Daha fazla bilgi için bkz: [inline_depth](../../preprocessor/inline-depth.md).  
  
## <a name="restrict-and-assume"></a>__restrict ve \__assume  
 Birkaç performans yardımcı olabilecek Visual c++ anahtar sözcükleri vardır: [__restrict](../../cpp/extension-restrict.md) ve [__assume](../../intrinsics/assume.md).  
  
 İlk olarak, unutulmamalıdır, `__restrict` ve `__declspec(restrict)` iki farklı noktalardır. Biraz ilgili karşın, bunların semantiği farklıdır. `__restrict`tür niteleyicisi gibi olan `const` veya `volatile`, ancak işaretçi türleri için özel olarak.  
  
 İle değiştiren bir işaretçi `__restrict` olarak adlandırılır bir *işaretçi __restrict*. Yalnızca aracılığıyla erişilebilir bir işaretçi bir __restrict işaretçidir \__kuruluşuma işaretçi. Diğer bir deyişle, başka bir işaretçi işaret verilere erişmek için kullanılamaz \__kuruluşuma işaretçi.  
  
 `__restrict`Visual C++ iyileştirici için güçlü bir araç olabilir, ancak çok dikkatli kullanın. Yanlış kullandıysanız, en iyi hale getirme, uygulamanızın çalışmamasına neden bir iyileştirme gerçekleştirebilir.  
  
 `__restrict` Anahtar sözcüğü değiştirir **/Oa** önceki sürümlerden geçiş yapın.  
  
 İle `__assume`, geliştirici bazı değişkeninin değeri hakkında varsayımlarda derleyici anlayabilirsiniz.  
  
 Örneğin `__assume(a < 5);` bu kodu değişkeni satırında söyler iyileştirici `a` değerinden 5'tir. Yeniden promise derleyici budur. Varsa `a` gerçekten 6 Bu noktada programda sonra derleyici optimize sahip sonra programın davranışını ne beklediğiniz olmayabilir. `__assume`Switch deyimleri ve/veya koşullu ifadeler önce en yararlı olur.  
  
 Bazı sınırlamalar vardır `__assume`. İlk olarak, ister `__restrict`, yalnızca bir öneri, yoksaymayı derleyici şekilde boş. Ayrıca, `__assume` şu anda yalnızca değişken inequalities sabitleri karşı çalışır. Simgesel inequalities, örneğin, dağıtılmaz assume(a < b).  
  
## <a name="intrinsic-support"></a>İç desteği  
 İç bilgiler işlevi olan burada derleyici iç Bilgi Bankası araması hakkında sahip ve bir kitaplıkta bir işlevi çağırmak yerine, bu işlevin kodunun yayar çağırır. < Installation_Directory > \VC\include\intrin.h bulunan üstbilgi dosyası intrin.h her üç desteklenen platformlar (x 86, x64 ve ARM) için tüm kullanılabilir iç bilgileri içerir.  
  
 İç bilgiler Programcı derleme kullanmak zorunda kalmadan derin koda gitme olanağı verir. İç bilgiler kullanmanın bazı avantajları şunlardır:  
  
1.  Kodunuzu daha taşınabilir. İç bilgiler çeşitli birden fazla CPU mimari üzerinde kullanılabilir.  
  
2.  Kodunuzu kodu hala C/C++'da yazılmış bu yana okumak daha kolay olur.  
  
3.  Kodunuzu derleyici iyileştirmelerini yararı alır. Derleyici daha iyi alır gibi iç bilgileri için kod oluşturmanın artırır.  
  
 Daha fazla bilgi için bkz: [derleyici iç bilgileri](../../intrinsics/compiler-intrinsics.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 Bir performans yoktur isabet özel durumlar kullanma ile ilişkilendirilmiş. Bazı kısıtlamalar belirli iyileştirmelerini gerçekleştirmeye derleyici engelle try blokları kullanırken sunulur. Üzerinde x86 gelen ek performans düşüşünü yoktur platformları kodu yürütme sırasında oluşturulan ek durum bilgileri nedeniyle blokları deneyin. 64 bit platformlarda deneyin blokları olabildiğince fazla performans düşebilir değil, ancak bir özel durum oluşturulduktan sonra işleyici bulma ve yığını geriye doğru izleme işlemi pahalı olabilir.  
  
 Bu nedenle, gerçekten ihtiyacınız olmayan koda try/catch blokları önlemek için önerilir. Özel durumlar kullanmanız gerekiyorsa, zaman uyumlu özel durumlar mümkünse kullanın. Daha fazla bilgi için bkz: [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).  
  
 Son olarak, yalnızca olağanüstü durumlar için özel durumlar oluşturma. Genel denetim akışı için özel durumlar kullanma, performans düşebilir büyük olasılıkla bir hale getirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu iyileştirme](../../build/reference/optimizing-your-code.md)