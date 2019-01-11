---
title: Kapsayıcılar (Modern C++)
ms.date: 1/18/2018
ms.topic: conceptual
ms.openlocfilehash: 2da57bfca8b04f50a223dddfb886835c69f746a4
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220146"
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

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
