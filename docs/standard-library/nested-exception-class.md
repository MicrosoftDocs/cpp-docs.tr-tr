---
title: nested_exception sınıfı
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 5741b3aa255f915500f5fe79ab5374c8c86f8814
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460185"
---
# <a name="nestedexception-class"></a>nested_exception sınıfı

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
|[operator=](#op_as)||

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

Bu `nested_exception` nesne tarafından yakalanan saklı özel durum.

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Açıklamalar

Null bir işaretçi `std::terminate()` döndürürse`nested_ptr()` , işlev çağırır. Aksi takdirde, tarafından `*this`yakalanan saklı özel durumu oluşturur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<özel durum >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
