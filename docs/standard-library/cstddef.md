---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 15d13a3af35cb41950df8aeba0c86d779e701ddb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244443"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

C Standart Kitaplığı üst bilgisi \<stddef.h > ve ilişkili adlarına ekler `std` ad alanı. Bu üstbilginin dahil sağlar C Standart Kitaplığı üstbilgisinde harici bağlantı kullanılarak bildirilen adların bildirilir `std` ad alanı.

> [!NOTE]
> \<cstddef > türünü içeren **bayt** ve türü içermez **wchar_t**.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Namespace ve makroları

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
Uygulama tanımlı iki alt simgeler farkı bir dizi nesnesinde tutabilen bir tamsayı türü imzalanmış.

*size_t*\
Herhangi bir nesnenin bayt cinsinden boyut içerecek şekilde büyük bir uygulama tanımlı işaretsiz tamsayı türü.

*max_align_t*\
Hizalama gereksinimi olan en az olarak, her skalar türü mükemmeldir ve hizalama gereksinimi olan her bağlamda desteklenen bir POD türü.

*nullptr_t değerine*\
Türü için bir eşanlamlı bir **nullptr** ifade. Ancak bir **nullptr** adresi olamaz alınamadığından, başka bir *nullptr_t değerine* lvalue nesnesini alınabilmesini.

## <a name="byte-class"></a>bayt sınıfı

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

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
