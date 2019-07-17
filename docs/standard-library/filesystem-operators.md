---
title: '&lt;dosya sistemi&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
ms.openlocfilehash: 819c91e707e50a190aa58eda62f8e07f3451b033
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240723"
---
# <a name="ltfilesystemgt-operators"></a>&lt;dosya sistemi&gt; işleçleri

İşleçler, dize olarak iki yol sözcük temelli bir karşılaştırma yapar. Kullanım `equivalent` iki yolu (örneğin, göreli bir yol ve mutlak bir yol) aynı dosya veya dizin diskte başvurmadığını belirlemek için işlevi.

Daha fazla bilgi için [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

İşlev left.native() döndürür right.native() ==.

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

İşlev verir. (sağdan sola ==).

## <a name="operator"></a>operator<

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

İşlev left.native() döndürür < right.native().

## <a name="operator"></a>operator<=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

İşlev verir. (doğru \< sol).

## <a name="operator"></a>operator >

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

İşlevi hemen döndürür \< sol.

## <a name="operator"></a>operator>=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

İşlev verir. (sol < doğru).

## <a name="operator"></a>operator /

```cpp
path operator/(const path& left, const path& right);
```

İşlevi yürütür:

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a>işleç <<

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

İşletim sistemi işlevi döndürür << pval.string\<Elem, nitelikler > ().

## <a name="operator"></a>İşleç >>

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

İşlevi yürütür:

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```
