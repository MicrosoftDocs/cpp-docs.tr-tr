---
title: '&lt;dosya sistemi&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 237287af88a7bf726948e0b17e5d1f3980ab459f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltfilesystemgt-operators"></a>&lt;dosya sistemi&gt; işleçleri

İşleçler iki yolu sözcük karşılaştırması dize olarak gerçekleştirin. Kullanım **eşdeğer** iki yolu (örneğin, göreli bir yol ve mutlak bir yol) aynı dosya veya dizin diskteki başvurmak olup olmadığını belirlemek için işlev.

Daha fazla bilgi için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

Left.native() işlevi döndürür right.native() ==.

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

İşlev verir! (sağdan sola ==).

## <a name="operator"></a>operator<

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

Left.native() işlevi döndürür < right.native().

## <a name="operator"></a>operator<=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

İşlev verir! (sağ \< sol).

## <a name="operator"></a>operator >

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

İşlev sağa döndürür \< sol.

## <a name="operator"></a>operator > =

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

İşlev verir! (sol < sağ).

## <a name="operator"></a>operator /

```cpp
path operator/(const path& left, const path& right);
```

İşlev çalıştırır:

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

İşlev çalıştırır:

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```

## <a name="see-also"></a>Ayrıca bkz.

[PATH sınıfı (Standart C++ Kitaplığı)](../standard-library/path-class.md)<br/>
[Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
