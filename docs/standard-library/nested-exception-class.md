---
title: nested_exception sınıfı
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: a568a8d9a3817883656406d63c3dd948539bb385
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267912"
---
# <a name="nestedexception-class"></a>nested_exception sınıfı

Sınıfı, birden çok devralma ile kullanmak için bir özel durum açıklar. Şu anda işleniyorsa özel durumu yakalar ve bunu daha sonra kullanmak üzere depolar.

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
|[rethrow_nested](#rethrow_nested)|Depolanan özel durum oluşturur.|
|[nested_ptr](#nested_ptr)|Depolanan özel durum verir.|

### <a name="op_as"></a> işleç =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Bu tarafından yakalanan depolanan özel durum `nested_exception` nesne.

### <a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Açıklamalar

Varsa `nested_ptr()` null işaretçisiyse, işlev çağrıları döndürür `std::terminate()`. Aksi takdirde, yakalanan tarafından depolanan özel durum atar `*this`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<özel durum >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[exception Sınıfı](../standard-library/exception-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
