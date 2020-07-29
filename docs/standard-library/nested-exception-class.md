---
title: nested_exception sınıfı
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6ae95880f0bc18928ed9bd4f6b6da14722f6ec60
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212195"
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

### <a name="operator"></a><a name="op_as"></a>işleç =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a><a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Bu nesne tarafından yakalanan saklı özel durum `nested_exception` .

### <a name="rethrow_nested"></a><a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Açıklamalar

`nested_ptr()`Null bir işaretçi döndürürse, işlev çağırır `std::terminate()` . Aksi takdirde, tarafından yakalanan saklı özel durumu oluşturur **`*this`** .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<exception>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
