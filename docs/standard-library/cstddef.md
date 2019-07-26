---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 87d268977ee46112fedce517e66a9e68071863db
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457568"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

, STDDEF. h > \<C standart kitaplığı başlığını içerir ve ilgili adları `std` ad alanına ekler. Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<cstddef > tür **baytı** içerir ve **wchar_t**türü içermez.

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
Bir **nullptr** ifadesinin türü için bir eş anlamlı. Bir **nullptr** adresi alınmasa da, lvalue olan başka bir *nullptr_t* nesnesinin adresi alınabilir.

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
[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
