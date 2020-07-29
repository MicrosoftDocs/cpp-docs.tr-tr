---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: f1582a4af1c26e1ef85cf0dce8406a4046a8fe8b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222530"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

C standart kitaplığı üst bilgisini içerir \<stddef.h> ve ad alanına ilişkili adlar ekler `std` . Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<cstddef>tür **baytı** içerir ve türü içermez **`wchar_t`** .

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Ad alanı ve makrolar

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>Parametreler

*ptrdiff_t*\
Bir dizi nesnesinde iki alt simgelerin farkını tutabilecek, uygulama tanımlı bir işaretli tamsayı türü.

*size_t*\
Herhangi bir nesnenin bayt cinsinden boyutunu içermesi için yeterince büyük olan uygulama tanımlı işaretsiz bir tamsayı türü.

*max_align_t*\
Hizalama gereksinimini en az her skalar türde olan ve hizalama gereksinimini her bağlamda desteklenen bir POD türü.

*nullptr_t*\
Bir ifadenin türü için bir eş anlamlı **`nullptr`** . Bir **`nullptr`** Adres alınmasa da, lvalue olan başka bir *nullptr_t* nesnesinin adresi alınabilir.

## <a name="byte-class"></a>Byte sınıfı

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
