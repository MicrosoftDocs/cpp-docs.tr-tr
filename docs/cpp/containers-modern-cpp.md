---
title: "Kapsayıcılar (Modern C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8617bf35f3de0575c365f57ba78edbc8a79cc0e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="containers-modern-c"></a>Kapsayıcılar (Modern C++)  
  
Varsayılan olarak, [vektör](../standard-library/vector-class.md) c++ tercih edilen sıralı kapsayıcı olarak. Bu eşdeğer olan `List<T>` .NET dillerinde.  
  
```cpp  
vector<string> apples;  
apples.push_back("Granny Smith");  
```  
  
Kullanım [harita](../standard-library/map-class.md) (değil `unordered_map`) varsayılan ilişkilendirilebilir kapsayıcı olarak. Kullanım [ayarlamak](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), ve [multiset](../standard-library/multiset-class.md) bozuk & çoklu durumlarda.  
  
```cpp  
map<string, string> apple_color;  
// ...  
apple_color["Granny Smith"] = "Green";  
```  
  
Performansı en iyi duruma getirme gerektiğinde kullanmayı dikkate alın:  
  
1.  [Dizi](../standard-library/array-class-stl.md) katıştırma Örneğin, bir sınıf üyesi olarak önemli olduğunda yazın.  
  
2.  [Unordered_map] gibi ilişkilendirilebilir kapsayıcılarına sıralanmamış ((.. /Standard-library/unordered-Map-class.MD). Bu alt öğesi başına yükü sahip ve sabiti zamanı arama, ancak bunlar doğru ve verimli şekilde kullanmanıza zor olabilir.  
  
3.  Sıralanmış `vector`. Daha fazla bilgi için bkz: [algoritmaları](../cpp/algorithms-modern-cpp.md).  
  
C türü diziler kullanmayın. Verilere erişim doğrudan eski API'ler erişimci yöntemleri gibi kullandığınız `f(vec.data(), vec.size());` yerine.  
  
Kapsayıcıları hakkında daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
