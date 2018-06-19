---
title: Kapsayıcılar (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49a77234b679fd61d801bb78d751891467d6b4e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412081"
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

- [Dizi](../standard-library/array-class-stl.md) katıştırma Örneğin, bir sınıf üyesi olarak önemli olduğunda yazın.

- İlişkilendirilebilir kapsayıcıları gibi sıralanmamış [unordered_map](../standard-library/unordered-map-class.md). Bu alt öğesi başına yükü sahip ve sabiti zamanı arama, ancak bunlar doğru ve verimli şekilde kullanmanıza zor olabilir.

- Sıralanmış **vektör**. Daha fazla bilgi için bkz: [algoritmaları](../cpp/algorithms-modern-cpp.md).

C türü diziler kullanmayın. Verilere erişim doğrudan eski API'ler erişimci yöntemleri gibi kullandığınız `f(vec.data(), vec.size());` yerine.

Kapsayıcıları hakkında daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)  
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)  
