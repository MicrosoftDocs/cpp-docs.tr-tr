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
ms.openlocfilehash: 2eb9419562382d3494e64dd7fb0472882fe73c13
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939045"
---
# <a name="containers-modern-c"></a>Kapsayıcılar (Modern C++)

Varsayılan olarak, [vektör](../standard-library/vector-class.md) c++ tercih edilen sıralı kapsayıcısı. Bunun eşdeğeri olan `List<T>` .NET dillerinde.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Kullanım [harita](../standard-library/map-class.md) (değil `unordered_map`) ilişkili kapsayıcı olarak. Kullanım [ayarlamak](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), ve [multiset](../standard-library/multiset-class.md) bozabilirler & çoklu durumlar için.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Performans iyileştirmesi gerektiğinde kullanmayı dikkate alın:

- [Dizi](../standard-library/array-class-stl.md) ekleme gibi bir sınıf üyesi olarak önemli olduğunda yazın.

- İlişkilendirilebilir kapsayıcılar gibi sırasız [unordered_map](../standard-library/unordered-map-class.md). Bu alt öğe başına ek yükü vardır ve sabit zamanlı arama, ancak doğru ve verimli bir şekilde kullanmak daha zor olabilir.

- Sıralanmış `vector`. Daha fazla bilgi için [algoritmaları](../cpp/algorithms-modern-cpp.md).

C stili diziler kullanmayın. Doğrudan veri erişim daha eski API'lar için erişimci metotlarını gibi kullanın `f(vec.data(), vec.size());` yerine.

Kapsayıcıları hakkında daha fazla bilgi için bkz. [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)  
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)  
