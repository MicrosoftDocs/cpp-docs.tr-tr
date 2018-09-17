---
title: Kodunuzu iyileştirme | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 180586f55ea57100286c3c598ac62eb83107d7c9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714382"
---
# <a name="optimizing-your-code"></a>Kodunuzu iyileştirme

Yürütülebilir hale getirerek, Hızlı yürütme hızını ve küçük kod boyutu arasında bir denge elde edebilirsiniz. Bu konu, bazı Visual C++ kod iyileştirmenize yardımcı sağlayan mekanizmalarını açıklar.

## <a name="language-features"></a>Dil özellikleri

Aşağıdaki konularda C/C++ dilinde iyileştirme özelliklerinden bazıları açıklanmaktadır.

[En iyi duruma getirme pragmaları ve anahtar sözcükleri](../../build/reference/optimization-pragmas-and-keywords.md) anahtar sözcükler ve pragmalar performansını artırmak için kodunuzda kullanabileceğiniz bir listesi.

[Kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md) listesini **/O** derleyici seçenekleri, özellikle yürütme hızını veya kod boyutunu etkiler.

[Rvalue başvuru Bildirimcisi: & &](../../cpp/rvalue-reference-declarator-amp-amp.md) uygulamasını Rvalue başvurularını destekler *taşıma semantiği*. Taşıma semantiği Şablon Kütüphanesi, bu şablonları kullanan uygulamaların performansını uygulamak için kullanılan önemli ölçüde artırabilir.

### <a name="the-optimize-pragma"></a>Optimize pragması

Kodun en iyi duruma getirilmiş bir bölümünü, hatalar veya yavaşlama neden olursa, kullanabileceğiniz [en iyi duruma getirme](../../preprocessor/optimize.md) pragması, bu bölümü için iyileştirme devre dışı bırakmak için.

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

[Zamana bağlı kodu geliştirme ipuçları](../../build/reference/tips-for-improving-time-critical-code.md) teknikleri daha iyi kodlama daha iyi performans yield. Bu konuda, zaman açısından kritik kod bölümlerini tatmin edici bir şekilde gerçekleştirdiğinizden emin olun yardımcı olabilecek teknikleri kodlama önerir.

[En iyi uygulamaları iyileştirme](../../build/reference/optimization-best-practices.md) uygulamanızı en iyi duruma getirmek en iyi nasıl hakkında genel yönergeler sağlar.

## <a name="debugging-optimized-code"></a>En iyi duruma getirilmiş kodda hata ayıklama

İyileştirme derleyici tarafından oluşturulan kodu değişebileceğinden, uygulamanızda hata ayıklamak ve performansını ölçmek ve kodunuzu en iyi duruma öneririz.

Aşağıdaki konular hatalarını nasıl ayıklayacağınız hakkında temel bilgiler sağlar.

- [Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)

- [Yayın Derlemesi Oluşturmadaki Genel Sorunlar](../../build/reference/common-problems-when-creating-a-release-build.md)

Aşağıdaki konular, hata ayıklama hakkında daha fazla Gelişmiş bilgi sağlar.

- [Nasıl Yapılır: İyileştirilmiş Kodda Hata Ayıklama](/visualstudio/debugger/how-to-debug-optimized-code)

- [Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](../../build/reference/why-floating-point-numbers-may-lose-precision.md)

Aşağıdaki konular, derleme, yükleme ve kodunuzun yürütme en iyi duruma getirme hakkında bilgi sağlar.

- [Derleyici Üretimini Geliştirme](../../build/reference/improving-compiler-throughput.md)

- [() Olmadan İşlev Adının Kullanılması Kod Üretmez](../../build/reference/using-function-name-without-parens-produces-no-code.md)

- [Satır İçi Bütünleştirilmiş Kodu En İyi Duruma Getirme](../../assembler/inline/optimizing-inline-assembly.md)

- [ATL Projesinde Derleyici İyileştirmesi Belirtme](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Yüklenirken istemci uygulamanın performansını artırmak için hangi iyileştirme tekniklerini kullanmalıyım?](../../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)
