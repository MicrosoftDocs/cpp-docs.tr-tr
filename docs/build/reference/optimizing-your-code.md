---
title: "Kodunuzu iyileştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
ms.assetid: 4f33e6c7-9870-43b3-9c2f-d7e44f764971
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3da29e9a0269c4748f10d9e8ba926103305239e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="optimizing-your-code"></a>Kodunuzu İyileştirme
Yürütülebilir bir dosya iyileştirerek Hızlı yürütme hızını ve küçük kod boyutu arasında bir denge elde edebilirsiniz. Bu konuda, Visual C++ kodu en iyi hale getirmenize Yardım sağlayan mekanizmaları bazıları açıklanmaktadır.  
  
## <a name="language-features"></a>Dil özellikleri  
 Aşağıdaki konularda C/C++ dil içindeki en iyi duruma getirme özelliklerinden bazıları açıklanmaktadır.  
  
 [En iyi duruma getirme pragmaları ve anahtar sözcükler](../../build/reference/optimization-pragmas-and-keywords.md)  
 Anahtar sözcükler ve pragmalar performansını artırmak için kodunuzda kullanabilirsiniz listesi.  
  
 [Kategoriye göre listelenen derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md)  
 Listesini **/O** özellikle yürütme hızını veya kod boyutunu etkiler derleyici seçenekleri.  
  
 [Rvalue başvuru Bildirimcisi: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)  
 Rvalue başvuru uygulaması Destek *semantiği taşıma*. Şablon kitaplıkları, bu şablonları kullanan uygulamaların performansını uygulamak için kullanılan semantiği taşıma önemli ölçüde iyileştirebilen durumunda.  
  
### <a name="the-optimize-pragma"></a>Optimize Pragması  
 En iyi duruma getirilmiş bir bölüm kod hataları veya yavaşlama neden olursa, kullanabileceğiniz [en iyi duruma getirme](../../preprocessor/optimize.md) iyileştirme Bu bölüm için devre dışı bırakmak üzere pragması.  
  
 Kod iki pragmaları arasında aşağıdaki gibi alın.  
  
```  
#pragma optimize("", off)  
// some code here   
#pragma optimize("", on)  
```  
  
## <a name="programming-practices"></a>Programlama yöntemler  
 Kodunuzu iyileştirme derlediğinizde ek uyarı iletileri görebilirsiniz. Bazı uyarılar yalnızca en iyi duruma getirilmiş kodla ilişkili olduğundan bu davranış beklenir. Bu uyarılar önemseyin varsa birçok iyileştirme sorunlarını önleyebilirsiniz.  
  
 Paradoxically, bir program hızı için en iyi duruma getirme kodun daha yavaş çalışmasına neden olabilir. Bazı iyileştirmeler hızı için kod boyutunu artırın olmasıdır. Örneğin, satır içi kullanım işlevleri işlev çağrılarını yükünü ortadan kaldırır. Ancak, satır içi kullanım programınızı çok fazla kod çok büyük sanal bellek sayfası sayısı arttıkça hataları neden olabilir. Bu nedenle, işlev çağrıları ortadan kazanılan hızı, bellek takası için kaybolmuş olabilir.  
  
 Aşağıdaki konular iyi programlama uygulamalarını tartışın.  
  
 [Zamana bağlı kodu geliştirme ipuçları](../../build/reference/tips-for-improving-time-critical-code.md)  
 Daha iyi teknikleri kodlama daha iyi performans sağlar. Bu konu, kodunuzu zaman açısından kritik bölümlerini başarılı şekilde gerçekleştirdiğinizden emin olun yardımcı olabilecek teknikleri kodlama önerir.  
  
 [En iyi uygulamaları iyileştirme](../../build/reference/optimization-best-practices.md)  
 En iyi nasıl uygulamanızı en iyi duruma getirme hakkında genel bilgi sağlar.  
  
## <a name="debugging-optimized-code"></a>İyileştirilmiş kodda hata ayıklama  
 En iyi duruma getirme derleyici tarafından oluşturulan kodu değişebileceğinden, uygulamanızda hata ayıklama ve kendi performansını ölçmek ve kodunuzu en iyi duruma öneririz.  
  
 Aşağıdaki konular, hata ayıklama hakkında temel bilgi sağlar.  
  
-   [Visual Studio'da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)  
  
-   [Yayın derlemesi oluşturma genel sorunlar](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
 Aşağıdaki konular, hata ayıklama hakkında daha gelişmiş bilgi sağlar.  
  
-   [Nasıl yapılır: iyileştirilmiş kodda hata ayıklama](/visualstudio/debugger/how-to-debug-optimized-code)  
  
-   [Kayan noktalı sayıların neden duyarlık kaybedebileceği](../../build/reference/why-floating-point-numbers-may-lose-precision.md)  
  
 Aşağıdaki konular çeşitli derleme, yükleme ve kodunuzu yürütülürken en iyi duruma getirme hakkında bilgi sağlar.  
  
-   [Derleyici üretimini geliştirme](../../build/reference/improving-compiler-throughput.md)  
  
-   [() Olmadan işlev adının kullanılması kod üretmez](../../build/reference/using-function-name-without-parens-produces-no-code.md)  
  
-   [Satır içi derleme en iyi duruma getirme](../../assembler/inline/optimizing-inline-assembly.md)  
  
-   [ATL projeleri için derleyici iyileştirmesi belirtme](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)  
  
-   [Yükleme yaparken istemci uygulamanın performansını artırmak için hangi iyileştirme tekniklerini kullanmalıyım?](../../build/dll-frequently-asked-questions.md#mfc_optimization)  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)]üzerinde DLL yöntemleri yüklenemedi, "MSDN dergisi" "Başlık altında" sütununda "En iyi duruma getirme DLL yükleme zamanı performans" Bkz süresini azaltmak nasıl [MSDN Kitaplığı](http://go.microsoft.com/fwlink/?linkid=556) Web sitesi.  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)]"Geliştirme çalışma zamanı performans ile düzgün çalışma kümesi aracı" Bkz uygulamalarında disk belleği en aza indirmek ve "arttırma çalışma zamanı performans düzgün çalışma ile kümesi aracı — 2" "MSDN dergisi" "Bugslayer" sütununda üzerinde Kısım [MSDN Kitaplık](http://go.microsoft.com/fwlink/?linkid=556) Web sitesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)