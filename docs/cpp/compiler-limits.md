---
title: "Derleyici sınırları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e64bedc169fb4737a7e16175099df5571df82ef2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-limits"></a>Derleyici Sınırları
C++ Standart çeşitli dil yapıları için sınırlar önerir. Burada Visual C++ derleyicisi önerilen sınırları uygulamıyor örneklerinin bir listesi verilmiştir. İlk sayı ISO C++ 11'de standart (INCITS/ISO/IEC 14882-2011 [2012] eki B) belirlenen sınırı ve ikinci sayı Visual C++ tarafından uygulanan sınır:  
  
-   Bileşik deyimler, yineleme denetim yapıları ve seçimi iç içe geçme düzeyi denetim yapıları - C++ Standart: 256, Visual C++ Derleyici: iç içe deyimlerinin ancak genellikle 100 110 arasındaki birleşimi bağlıdır.  
  
-   Bir makro tanımı - C++ Standart parametrelerinde: 256, Visual C++ Derleyici: 127.  
  
-   Bir makrosu çağırma - C++ standart bağımsız değişkenler: 256, Visual C++ Derleyici 127.  
  
-   Bir karakterin karakter dizelerle değişmez değer veya geniş dize sabit değeri (sonra) - C++ Standart: 65536, Visual C++ Derleyici: 65535 tek baytlık karakterler `null` Sonlandırıcı ve dahilolmaküzere32767çiftbaytlıkkarakterler`null` Sonlandırıcı.  
  
-   Düzey iç içe geçmiş sınıf, yapı ve birleşim tanımları tek bir `struct-declaration-list` -C++ Standart: 256, Visual C++ Derleyici: 16.  
  
-   Üye başlatıcıları Oluşturucusu tanımında - C++ Standart: 6144, Visual C++ Derleyici: en az 6144.  
  
-   Kapsam bir tanımlayıcı - C++ Standart nitelikleri: 256, Visual C++ Derleyici: 127.  
  
-   İç içe geçmiş `extern` belirtimleri - C++ Standart: 1024, Visual C++ Derleyici: 9 (örtük saymaz `extern` belirtimi genel kapsamda ya da örtük sayım yapmak istiyorsanız 10 `extern` genel kapsam belirtiminde..  
  
-   Bir şablon bildirimi - C++ standart şablon bağımsız değişkenler: 1024, Visual C++ Derleyici: 2046.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Standart olmayan davranış](../cpp/nonstandard-behavior.md)