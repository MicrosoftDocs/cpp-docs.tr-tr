---
title: "1.3 yürütme modeli | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dddc4c10a77ca5dd277435837169478e0d5daca5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="13-execution-model"></a>1.3 Yürütme Modeli
OpenMP Paralel yürütme çatalı birleştirme modelini kullanır. Bu çatalı birleştirme model çeşitli sorunlarını çözmek için yararlı olsa da, bunu biraz büyük dizi tabanlı uygulamalar için özel olarak oluşturulmuştur. OpenMP paralel (birden çok iş parçacığı yürütme ve tam OpenMP destek kitaplık) programları gibi her ikisi de düzgün yürütecek destek programları ve sıralı programlar (göz ardı yönergeleri ve basit bir OpenMP saplamalar kitaplık) olarak tasarlanmıştır. Ancak, mümkündür ve doğru sırayla çalıştırıldığında davranıyor olmayan bir programı geliştirmek için izin verilir. Ayrıca, farklı paralellik derecesi sayısal işlemlerinin association'daki değişiklikler nedeniyle farklı sayısal sonuçlar neden olabilir. Örneğin, bir seri toplama azaltma toplama İlişkilendirmelerin paralel azaltma daha farklı bir desen olabilir. Bu farklı ilişkilendirmeleri kayan nokta toplama sonuçlarını değişebilir.  
  
 OpenMP C/C++ API ile yazılmış bir program tek bir iş parçacığı olarak adlı yürütme yürütülmeye *ana iş parçacığı*. İlk paralel yapısıyla karşılaştı kadar ana iş parçacığı bir seri bölgede yürütür. OpenMP C/C++ API'sindeki **paralel** yönergesi oluşturduğunu paralel yapı. Paralel yapı karşılaşıldığında, iş parçacıklarının takım ana iş parçacığı oluşturur ve ana ekibi ana olur. Her iş parçacığı ekipteki ifadeleri iş paylaşım yapıları dışında paralel bir bölgenin dinamik kapsam içinde yürütür. İş paylaşım yapıları aynı sırada ekibindeki tüm iş parçacıkları tarafından karşılaşılan gerekir ve deyimleri ilişkili yapılandırılmış bloğu içinde bir veya daha fazla iş parçacığı tarafından yürütülür. Bir iş paylaşım yapısı sonunda kapsanan engel bir `nowait` yan tümcesi ekibindeki tüm iş parçacıkları tarafından gerçekleştirilir.  
  
 Bir iş parçacığı bir paylaşılan nesne değiştirirse, yalnızca kendi yürütme ortamı, aynı zamanda bu programı başka bir iş parçacığı etkiler. Değiştirme, nesne geçici olarak bildirilirse (temel dilinde tanımlandığı gibi), açısından, başka bir iş parçacığı, sonraki dizisi noktada birinin tamamlanması sağlanır. Aksi takdirde, değişikliği ilk değiştirme iş parçacığı sonra tamamlanması garanti ve sonra (veya aynı anda) başka bir iş parçacığı, karşılaştığınız bir **flush** nesnesini (örtük veya açık olarak) belirtir. yönergesi. Unutmayın **Temizleme** diğer OpenMP yönergeleri tarafından kapsanan yönergeleri yan etkileri istenen sıralama emin olmak yeterli değildir, bu ek, açık sağlamak için programcı sorumluluğundadır  **Flush** yönergeleri.  
  
 Tamamlanmasıyla paralel yapı, takım parçacıklarında örtük bir engel eşitlemek ve yalnızca ana iş parçacığı yürütme devam eder. Herhangi bir sayıda paralel yapıları tek bir program belirtilebilir. Sonuç olarak, bir program çatallaştırma ve yürütme sırasında birçok kez katılın.  
  
 OpenMP C/C++ API yönergeleri içinde paralel yapıları çağrılır işlevleri kullanmak programcıları sağlar. Paralel yapı içindeki sözcük kapsamı görünmez, ancak dinamik kapsam içinde yer alan yönergeleri çağrılır *yalnız bırakılmış* yönergeleri. Yalnız bırakılmış yönergeleri programcıları kendi programın ana bölümleri sıralı program sadece küçük değişiklikler ile Paralel yürütme olanağı verir. Bu işlev ile kullanıcıların program çağrı ağacı üst düzeylerinde paralel yapıları kod ve yürütme çağrılan işlevlerin hiçbirinde denetlemek için yönergeleri kullanın.  
  
 C ve C++ eşitlenmemiş çağrıları aynı dosyaya yazma işlevleri farklı iş parçacıkları tarafından yazılan veriler belirleyici sırayla göründüğü çıkış sonuçlanabilir çıktı. Benzer şekilde, aynı dosyadan okunan işlevleri giriş eşitlenmemiş çağrıları verileri belirleyici sırayla okuyabilirsiniz. Her iş parçacığı farklı bir dosya erişen şekilde eşitlenmemiş g/ç kullanımını seri g/ç işlevleri yürütmesini olarak aynı sonucu verir.