---
title: Kapsayıcılar (Modern C++)
ms.date: 01/18/2018
ms.topic: conceptual
ms.openlocfilehash: 37b540132fc9ddc03d5eaafd33c545b5db5e7935
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926253"
---
# <a name="containers-modern-c"></a>Kapsayıcılar (Modern C++)

Varsayılan olarak, [vektör](../standard-library/vector-class.md) ' de C++tercih edilen sıralı kapsayıcı olarak kullanın. Bu, .NET dilleri `List<T>` ile eşdeğerdir.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Varsayılan [](../standard-library/map-class.md) ilişkilendirilebilir kapsayıcı olarak `unordered_map`eşleme (Not) kullanın. & Çoklu durumlar için set, [multimap](../standard-library/multimap-class.md)ve [multıset](../standard-library/set-class.md)kullanın. [](../standard-library/multiset-class.md)

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Performans iyileştirmesi gerektiğinde şunu kullanmayı göz önünde bulundurun:

- Gömme önemli olduğunda [dizi](../standard-library/array-class-stl.md) türü, örneğin bir sınıf üyesi olarak.

- [Unordered_map](../standard-library/unordered-map-class.md)gibi sırasız ilişkilendirilebilir kapsayıcılar. Bunlar, öğe başına ek yüke ve sabit zamanlı aramaya sahiptir, ancak doğru ve verimli bir şekilde kullanılması daha zor olabilir.

- Sıralanır `vector`. Daha fazla bilgi için bkz. [algoritmalar](../cpp/algorithms-modern-cpp.md).

C stili dizileri kullanmayın. Verilere doğrudan erişmesi gereken eski API 'ler için, `f(vec.data(), vec.size());` bunun yerine erişimci yöntemlerini kullanın.

Kapsayıcılar hakkında daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
