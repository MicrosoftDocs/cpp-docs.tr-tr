---
title: "Kodunuzu iyileştirme | Microsoft Docs"
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4306f825b9925dbdcdc994d287a2c4287ea7bfc2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="optimizing-your-code"></a>Kodunuzu iyileştirme

Yürütülebilir bir dosya iyileştirerek Hızlı yürütme hızını ve küçük kod boyutu arasında bir denge elde edebilirsiniz. Bu konuda, Visual C++ kodu en iyi hale getirmenize Yardım sağlayan mekanizmaları bazıları açıklanmaktadır.

## <a name="language-features"></a>Dil özellikleri

Aşağıdaki konularda C/C++ dil içindeki en iyi duruma getirme özelliklerinden bazıları açıklanmaktadır.

[Pragmaları ve Anahtar Sözcükleri İyileştirme](../../build/reference/optimization-pragmas-and-keywords.md)  
Anahtar sözcükler ve pragmalar performansını artırmak için kodunuzda kullanabilirsiniz listesi.

[Kategorilere Göre Listelenen Derleyici Seçenekleri](../../build/reference/compiler-options-listed-by-category.md)  
Listesini **/O** özellikle yürütme hızını veya kod boyutunu etkiler derleyici seçenekleri.

[Rvalue Başvuru Bildirimcisi: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
Rvalue başvuru uygulaması Destek *semantiği taşıma*. Şablon kitaplıkları, bu şablonları kullanan uygulamaların performansını uygulamak için kullanılan semantiği taşıma önemli ölçüde iyileştirebilen durumunda.

### <a name="the-optimize-pragma"></a>Optimize pragması

En iyi duruma getirilmiş bir bölüm kod hataları veya yavaşlama neden olursa, kullanabileceğiniz [en iyi duruma getirme](../../preprocessor/optimize.md) iyileştirme Bu bölüm için devre dışı bırakmak üzere pragması.

Aşağıda gösterildiği gibi iki pragmaları arasında kodu alın:

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>Programlama yöntemler

Kodunuzu iyileştirme derlediğinizde ek uyarı iletileri görebilirsiniz. Bazı uyarılar yalnızca en iyi duruma getirilmiş kodla ilişkili olduğundan bu davranış beklenir. Bu uyarılar önemseyin varsa birçok iyileştirme sorunlarını önleyebilirsiniz.

Paradoxically, bir program hızı için en iyi duruma getirme kodun daha yavaş çalışmasına neden olabilir. Bazı iyileştirmeler hızı için kod boyutunu artırın olmasıdır. Örneğin, satır içi kullanım işlevleri işlev çağrılarını yükünü ortadan kaldırır. Ancak, satır içi kullanım programınızı çok fazla kod çok büyük sanal bellek sayfası sayısı arttıkça hataları neden olabilir. Bu nedenle, işlev çağrıları ortadan kazanılan hızı, bellek takası için kaybolmuş olabilir.

Aşağıdaki konular iyi programlama uygulamalarını tartışın.

[Zamana Bağlı Kodu Geliştirme İpuçları](../../build/reference/tips-for-improving-time-critical-code.md)  
Daha iyi teknikleri kodlama daha iyi performans sağlar. Bu konu, kodunuzu zaman açısından kritik bölümlerini başarılı şekilde gerçekleştirdiğinizden emin olun yardımcı olabilecek teknikleri kodlama önerir.

[En İyi Uygulamaları İyileştirme](../../build/reference/optimization-best-practices.md)  
En iyi nasıl uygulamanızı en iyi duruma getirme hakkında genel bilgi sağlar.

## <a name="debugging-optimized-code"></a>İyileştirilmiş kodda hata ayıklama

En iyi duruma getirme derleyici tarafından oluşturulan kodu değişebileceğinden, uygulamanızda hata ayıklama ve kendi performansını ölçmek ve kodunuzu en iyi duruma öneririz.

Aşağıdaki konular, hata ayıklama hakkında temel bilgi sağlar.

- [Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)

- [Yayın Derlemesi Oluşturmadaki Genel Sorunlar](../../build/reference/common-problems-when-creating-a-release-build.md)

Aşağıdaki konular, hata ayıklama hakkında daha gelişmiş bilgi sağlar.

- [Nasıl yapılır: iyileştirilmiş kodda hata ayıklama](/visualstudio/debugger/how-to-debug-optimized-code)

- [Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](../../build/reference/why-floating-point-numbers-may-lose-precision.md)

Aşağıdaki konular, derleme, yükleme ve kodunuzu yürütülürken en iyi duruma getirme hakkında bilgi sağlar.

- [Derleyici Üretimini Geliştirme](../../build/reference/improving-compiler-throughput.md)

- [() Olmadan İşlev Adının Kullanılması Kod Üretmez](../../build/reference/using-function-name-without-parens-produces-no-code.md)

- [Satır İçi Bütünleştirilmiş Kodu En İyi Duruma Getirme](../../assembler/inline/optimizing-inline-assembly.md)

- [ATL Projesinde Derleyici İyileştirmesi Belirtme](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Yükleme yaparken istemci uygulamanın performansını artırmak için hangi iyileştirme tekniklerini kullanmalıyım?](../../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)  
