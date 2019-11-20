---
title: Kapsayıcılar (Modern C++)
ms.date: 11/12/2019
ms.topic: conceptual
ms.openlocfilehash: 41b9d560ce827cee5c90467184ef5b2b729e0639
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188897"
---
# <a name="containers-modern-c"></a>Kapsayıcılar (Modern C++)

By default, use [std::vector](../standard-library/vector-class.md) as the preferred sequential container in C++. The performance of **std::vector** is comparable to C-style arrays in most scenarios and is far safer. **std::vector** is equivalent to `List<T>` in .NET languages.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Use [map](../standard-library/map-class.md) (not `unordered_map`) as the default associative container. Use [set](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), and [multiset](../standard-library/multiset-class.md) for degenerate & multi cases.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

When performance optimization is needed, consider using:

- The [array](../standard-library/array-class-stl.md) type when embedding is important, for example, as a class member.

- Unordered associative containers such as [unordered_map](../standard-library/unordered-map-class.md). These have lower per-element overhead and constant-time lookup, but they can be harder to use correctly and efficiently.

- Sorted `vector`. For more information, see [Algorithms](../cpp/algorithms-modern-cpp.md).

Don’t use C-style arrays. For older APIs that need direct access to the data, use accessor methods such as `f(vec.data(), vec.size());` instead.

For more information about containers, see [C++ Standard Library Containers](../standard-library/stl-containers.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
