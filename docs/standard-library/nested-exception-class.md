---
title: nested_exception sınıfı
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: ed58eb6cc074b54ae6801d2b11089af9a79f8c8f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441623"
---
# <a name="nested_exception-class"></a>nested_exception sınıfı

Sınıfı, birden çok Devralmada kullanılmak üzere bir özel durum tanımlar. Şu anda işlenmiş özel durumu yakalar ve daha sonra kullanmak üzere depolar.

## <a name="syntax"></a>Sözdizimi

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_as)||

### <a name="functions"></a>İşlevler

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|Saklı özel durumu oluşturur.|
|[nested_ptr](#nested_ptr)|Depolanan özel durumu döndürür.|

### <a name="op_as"></a>işleç =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Bu `nested_exception` nesnesi tarafından yakalanan saklı özel durum.

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Açıklamalar

`nested_ptr()` null bir işaretçi döndürürse, işlev `std::terminate()`çağırır. Aksi takdirde, `*this`tarafından yakalanan saklı özel durumu oluşturur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<özel durum >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
