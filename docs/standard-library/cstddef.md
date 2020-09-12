---
title: '&lt;cstddef&gt;'
description: C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların ad alanında bildirilmesini sağlayan <stddef. h> açıklanmaktadır `std` .
ms.date: 9/4/2020
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 186de0e893c413a25d31d4f1431c280d749e9541
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040034"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

C standart kitaplığı üst bilgisini içerir \<stddef.h> ve ad alanına ilişkili adlar ekler `std` . Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<cstddef> tür **baytı** içerir ve türü içermez **`wchar_t`** .

## <a name="syntax"></a>Syntax

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
