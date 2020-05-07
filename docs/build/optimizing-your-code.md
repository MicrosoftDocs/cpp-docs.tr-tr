---
title: Kodunuzu İyileştirme
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: 00356cf50ca8e50c80e8a1142adf654816490c9b
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078500"
---
# <a name="optimizing-your-code"></a>Kodunuzu iyileştirme

Bir yürütülebiliri iyileştirerek, Hızlı yürütme hızı ve küçük kod boyutu arasında bir denge elde edebilirsiniz. Bu konuda, kodu iyileştirmenize yardımcı olmak için Visual Studio 'nun sağladığı mekanizmalardan bazıları ele alınmaktadır.

## <a name="language-features"></a>Dil özellikleri

Aşağıdaki konularda, C/C++ dilinde en iyi duruma getirme özellikleri açıklanır.

[Optimizasyon pragmaları ve anahtar sözcükleri](optimization-pragmas-and-keywords.md) \
Kodunuzun performansını artırmak için kodunuzda kullanabileceğiniz anahtar sözcüklerin ve pragmaların bir listesi.

[Kategoriye göre listelenen derleyici seçenekleri](reference/compiler-options-listed-by-category.md) \
Özellikle yürütme hızını veya kod boyutunu etkileyen **/o** derleyici seçeneklerinin bir listesi.

[Rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md) \
Rvalue başvuruları, *taşıma semantiğinin*uygulanmasını destekler. Taşıma semantiği şablon kitaplıklarını uygulamak için kullanılırsa, bu şablonları kullanan uygulamaların performansı önemli ölçüde iyileştirebilirler.

### <a name="the-optimize-pragma"></a>Optimize pragma

İyileştirilmiş bir kod bölümü hatalara veya yavaşlama hatasına neden oluyorsa, bu bölüm için iyileştirmeyi devre dışı bırakmak için [optimize](../preprocessor/optimize.md) pragma 'ı kullanabilirsiniz.

Kodu, burada gösterildiği gibi iki pragma arasına koyun:

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>Programlama uygulamaları

Kodunuzu iyileştirme ile derlerken ek uyarı iletileri görebilirsiniz. Bu davranış, bazı uyarılar yalnızca iyileştirilmiş kodla ilişkilendirildiğinden beklenmektedir. Bu uyarıları önemseen iyileştirme sorunlarından kaçınabilirsiniz.

Paradoxically, bir programı hız için iyileştirmek kodun daha yavaş çalışmasına neden olabilir. Bunun nedeni hız için bazı iyileştirmelerin kod boyutunu artırması nedeniyle oluşur. Örneğin, satır içi işlevler işlev çağrılarının ek yükünü ortadan kaldırır. Ancak, çok fazla kod, programınızı, sanal bellek sayfa hatalarının sayısının arttığı kadar büyük hale getirir. Bu nedenle, işlev çağrılarını ortadan kaldırarak elde edilen hız bellek takası için kaybolabilir.

Aşağıdaki konular iyi programlama uygulamalarını tartışır.

[Zaman açısından kritik kodu Iyileştirmeye yönelik ipuçları](tips-for-improving-time-critical-code.md) \
Daha iyi kodlama teknikleri daha iyi performans sağlayabilir. Bu konuda, kodunuzun zaman kritik bölümlerinin önemli olduğundan emin olmanıza yardımcı olabilecek kodlama teknikleri önerilir.

[En Iyi duruma getirme uygulamaları](optimization-best-practices.md) \
Uygulamanızın en iyi şekilde iyileştirilmesi hakkında genel yönergeler sağlar.

## <a name="debugging-optimized-code"></a>İyileştirilmiş kodda hata ayıklama

İyileştirme derleyici tarafından oluşturulan kodu değiştirebileceğinden, uygulamanızda hata ayıklamanızı ve performansını ölçmenizi ve ardından kodunuzu en iyi duruma getirmeyi öneririz.

Aşağıdaki konularda, sürüm Derlemeleriyle ilgili hata ayıklama hakkında bilgi sağlanmaktadır.

- [Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)

- [Nasıl Yapılır: İyileştirilmiş Kodda Hata Ayıklama](/visualstudio/debugger/how-to-debug-optimized-code)

- [Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](why-floating-point-numbers-may-lose-precision.md)

Aşağıdaki konularda, kodunuzun oluşturulması, yüklenmesi ve yürütülmesi nasıl iyileştirileceği hakkında bilgi sağlanmaktadır.

- [Derleyici verimini geliştirme](improving-compiler-throughput.md)

- [() Olmadan İşlev Adının Kullanılması Kod Üretmez](using-function-name-without-parens-produces-no-code.md)

- [Satır İçi Bütünleştirilmiş Kodu En İyi Duruma Getirme](../assembler/inline/optimizing-inline-assembly.md)

- [ATL Projesinde Derleyici İyileştirmesi Belirtme](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Yükleme sırasında istemci uygulamasının performansını iyileştirmek için hangi iyileştirme tekniklerini kullanmalıyım?](../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="in-this-section"></a>Bu bölümde

[Optimizasyon pragmaları ve anahtar sözcükleri](optimization-pragmas-and-keywords.md) \
[Derleyici verimini geliştirme](improving-compiler-throughput.md) \
[Kayan noktalı sayıların neden duyarlık Kaybedemeyebilir](why-floating-point-numbers-may-lose-precision.md) \
[IEEE kayan nokta temsili](ieee-floating-point-representation.md) \
[Zaman açısından kritik kodu Iyileştirmeye yönelik ipuçları](tips-for-improving-time-critical-code.md) \
[() Olmadan Işlev adının kullanılması kod üretmez](using-function-name-without-parens-produces-no-code.md) \
[En Iyi duruma getirme uygulamaları](optimization-best-practices.md) \
[Profil temelli Iyileştirmeler](profile-guided-optimizations.md) \
[Profil temelli Iyileştirmeler için ortam değişkenleri](environment-variables-for-profile-guided-optimizations.md) \
[Pgooto süpürme](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[Nasıl Yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](reference/c-cpp-building-reference.md)
