---
title: Kodunuzu İyileştirme
ms.date: 12/10/2018
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: ae60070959c683a6365992e7b6cc510fd4111b36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295225"
---
# <a name="optimizing-your-code"></a>Kodunuzu iyileştirme

Yürütülebilir hale getirerek, Hızlı yürütme hızını ve küçük kod boyutu arasında bir denge elde edebilirsiniz. Bu konu, bazı Visual C++ kod iyileştirmenize yardımcı sağlayan mekanizmalarını açıklar.

## <a name="language-features"></a>Dil özellikleri

Aşağıdaki konularda C/C++ dilinde iyileştirme özelliklerinden bazıları açıklanmaktadır.

[Pragmaları ve Anahtar Sözcükleri İyileştirme](optimization-pragmas-and-keywords.md)<br/>
Anahtar sözcükler ve pragmalar performansını artırmak için kodunuzda kullanabileceğiniz listesi.

[Kategorilere Göre Listelenen Derleyici Seçenekleri](reference/compiler-options-listed-by-category.md)<br/>
Listesini **/O** derleyici seçenekleri, özellikle yürütme hızını veya kod boyutunu etkiler.

[Rvalue Başvuru Bildirimcisi: &&](../cpp/rvalue-reference-declarator-amp-amp.md)<br/>
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

[Zamana Bağlı Kodu Geliştirme İpuçları](tips-for-improving-time-critical-code.md)<br/>
Teknikleri daha iyi kodlama daha iyi performans sağlayabilir. Bu konuda, zaman açısından kritik kod bölümlerini tatmin edici bir şekilde gerçekleştirdiğinizden emin olun yardımcı olabilecek teknikleri kodlama önerir.

[En İyi Uygulamaları İyileştirme](optimization-best-practices.md)<br/>
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

[Pragmaları ve Anahtar Sözcükleri İyileştirme](optimization-pragmas-and-keywords.md)<br/>
[Derleyici Üretimini Geliştirme](improving-compiler-throughput.md)<br/>
[Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](why-floating-point-numbers-may-lose-precision.md)<br/>
[IEEE Kayan Noktası Temsili](ieee-floating-point-representation.md)<br/>
[Zamana Bağlı Kodu Geliştirme İpuçları](tips-for-improving-time-critical-code.md)<br/>
[() Olmadan İşlev Adının Kullanılması Kod Üretmez](using-function-name-without-parens-produces-no-code.md)<br/>
[En İyi Uygulamaları İyileştirme](optimization-best-practices.md)<br/>
[Profil Temelli İyileştirmeler](profile-guided-optimizations.md)<br/>
[Profil Temelli İyileştirmeler için Ortam Değişkenleri](environment-variables-for-profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgomgr](pgomgr.md)<br/>
[pgosweep](pgosweep.md)<br/>
[Nasıl yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
[Performans ve Tanılama Hub’ında Visual Studio 2013 PGO Eklentisi](profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](reference/c-cpp-building-reference.md)
