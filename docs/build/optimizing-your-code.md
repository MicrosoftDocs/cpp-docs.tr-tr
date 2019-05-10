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
ms.openlocfilehash: f44fb734c8441e10b656c5326c8df4bf6879499a
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220181"
---
# <a name="optimizing-your-code"></a>Kodunuzu iyileştirme

Yürütülebilir hale getirerek, Hızlı yürütme hızını ve küçük kod boyutu arasında bir denge elde edebilirsiniz. Bu konu, bazı Visual Studio kod iyileştirmenize yardımcı sağlayan mekanizmalarını açıklar.

## <a name="language-features"></a>Dil özellikleri

Aşağıdaki konularda C/C++ dilinde iyileştirme özelliklerinden bazıları açıklanmaktadır.

[En iyi duruma getirme pragmaları ve anahtar sözcükleri](optimization-pragmas-and-keywords.md) \
Anahtar sözcükler ve pragmalar performansını artırmak için kodunuzda kullanabileceğiniz listesi.

[Kategorilere göre listelenen derleyici seçenekleri](reference/compiler-options-listed-by-category.md) \
Listesini **/O** derleyici seçenekleri, özellikle yürütme hızını veya kod boyutunu etkiler.

[Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md) \
Rvalue başvuruları uygulamasını destekler *taşıma semantiği*. Taşıma semantiği Şablon Kütüphanesi, bu şablonları kullanan uygulamaların performansını uygulamak için kullanılan önemli ölçüde artırabilir.

### <a name="the-optimize-pragma"></a>Optimize pragması

Kodun en iyi duruma getirilmiş bir bölümünü, hatalar veya yavaşlama neden olursa, kullanabileceğiniz [en iyi duruma getirme](../preprocessor/optimize.md) pragması, bu bölümü için iyileştirme devre dışı bırakmak için.

İki pragmaları arasında kod, aşağıda gösterildiği gibi alın:

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>Programlama yöntemler

Kodunuzu iyileştirme ile derleme yaparken ek uyarı iletileri görebilirsiniz. Bazı uyarılar için yalnızca en iyi duruma getirilmiş kod arasında bir ilişki olduğundan, bu davranış beklenmektedir. Bu uyarılar önemseyin, birçok iyileştirme sorunlarını önleyebilirsiniz.

Paradoxically, bir program hızını en iyi duruma getirme, kodun daha yavaş çalışmasına neden olabilir. Bazı iyileştirmeler hızı için kod boyutunu artırın olmasıdır. Örneğin, satır içi işlevler işlev çağrılarının ek yükü ortadan kaldırır. Ancak, yapılmış programınızı çok fazla kod çok büyük sanal bellek sayfası sayısı arttıkça hataları neden olabilir. Bu nedenle, işlev çağrıları ortadan öğesinden elde edilen hızı, bellek takas için kaybolmuş olabilir.

Aşağıdaki konular, iyi bir programlama uygulamalarını tartışın.

[Zamana bağlı kodu geliştirme ipuçları](tips-for-improving-time-critical-code.md) \
Teknikleri daha iyi kodlama daha iyi performans sağlayabilir. Bu konuda, zaman açısından kritik kod bölümlerini tatmin edici bir şekilde gerçekleştirdiğinizden emin olun yardımcı olabilecek teknikleri kodlama önerir.

[En iyi uygulamaları iyileştirme](optimization-best-practices.md) \
Uygulamanızı en iyi duruma getirmek en iyi nasıl hakkında genel yönergeler sağlar.

## <a name="debugging-optimized-code"></a>En iyi duruma getirilmiş kodda hata ayıklama

İyileştirme derleyici tarafından oluşturulan kodu değişebileceğinden, uygulamanızda hata ayıklamak ve performansını ölçmek ve kodunuzu en iyi duruma öneririz.

Aşağıdaki konular, derlemeler sürüm hata ayıklama hakkında bilgi sağlar.

- [Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)

- [Nasıl yapılır: İyileştirilmiş Kodda Hata Ayıklama](/visualstudio/debugger/how-to-debug-optimized-code)

- [Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](why-floating-point-numbers-may-lose-precision.md)


Aşağıdaki konular, derleme, yükleme ve kodunuzun yürütme en iyi duruma getirme hakkında bilgi sağlar.

- [Derleyici Üretimini Geliştirme](improving-compiler-throughput.md)

- [() Olmadan İşlev Adının Kullanılması Kod Üretmez](using-function-name-without-parens-produces-no-code.md)

- [Satır İçi Bütünleştirilmiş Kodu En İyi Duruma Getirme](../assembler/inline/optimizing-inline-assembly.md)

- [ATL Projesinde Derleyici İyileştirmesi Belirtme](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Yüklenirken istemci uygulamanın performansını artırmak için hangi iyileştirme tekniklerini kullanmalıyım?](../build/dll-frequently-asked-questions.md#mfc_optimization)


## <a name="in-this-section"></a>Bu bölümde

[En iyi duruma getirme pragmaları ve anahtar sözcükleri](optimization-pragmas-and-keywords.md) \
[Derleyici üretimini geliştirme](improving-compiler-throughput.md) \
[Kayan noktalı sayıların neden duyarlık kaybedebileceği](why-floating-point-numbers-may-lose-precision.md) \
[IEEE kayan Noktası temsili](ieee-floating-point-representation.md) \
[Zamana bağlı kodu geliştirme ipuçları](tips-for-improving-time-critical-code.md) \
[() Olmadan işlev adının kullanılması kod üretmez](using-function-name-without-parens-produces-no-code.md) \
[En iyi uygulamaları iyileştirme](optimization-best-practices.md) \
[Profil temelli iyileştirmeler](profile-guided-optimizations.md) \
[Profil temelli iyileştirmeler için ortam değişkenleri](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[Nasıl yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](reference/c-cpp-building-reference.md)
