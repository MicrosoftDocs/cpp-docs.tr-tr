---
description: 'Daha fazla bilgi edinin: &lt; dosya sistemi &gt; işleçleri'
title: '&lt;dosya sistemi &gt; işleçleri'
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
ms.openlocfilehash: 140ef553cbfd17fe2b1cfc41bedba397506da817
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232478"
---
# <a name="ltfilesystemgt-operators"></a>&lt;dosya sistemi &gt; işleçleri

İşleçler, iki yolun dizeler olarak çok yönlü bir karşılaştırmasını yapar. İki yolun `equivalent` (örneğin, göreli yol ve mutlak yol) diskte aynı dosyaya veya dizine başvurmasını sağlamak için işlevini kullanın.

Daha fazla bilgi için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

İşlev Left. Native () = = right. Native () döndürür.

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

İşlev döndürür! (sol = = sağ).

## <a name="operator"></a>işleç<

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

İşlevi Left. Native () < Right. Native () döndürür.

## <a name="operator"></a>işleç<=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

İşlev döndürür! (sağ \< ok).

## <a name="operator"></a>işleç>

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

İşlev sağ sola döndürür \< .

## <a name="operator"></a>operator>=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

İşlev döndürür! (sol < sağ).

## <a name="operator"></a>işlecinde

```cpp
path operator/(const path& left, const path& right);
```

İşlevi çalıştırılır:

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a>işleç<<

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

İşlev, OS << Pval. String \<Elem, Traits> () döndürür.

## <a name="operator"></a>işleç>>

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

İşlevi çalıştırılır:

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```
