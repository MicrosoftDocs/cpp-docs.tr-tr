---
title: ComPtrRef Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
ms.openlocfilehash: f92a3e14018cf8c02dec40b664b72a0956f6220e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220541"
---
# <a name="comptrref-class"></a>ComPtrRef Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir [ComPtr \<T> ](comptr-class.md) türü veya ondan türetilmiş bir tür veya yalnızca tarafından temsil edilen arabirim değil `ComPtr` .

## <a name="remarks"></a>Açıklamalar

Türündeki bir nesneye yapılan başvuruyu temsil eder `ComPtr<T>` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                               | Açıklama
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef:: ComPtrRef](#comptrref) | `ComPtrRef`Belirtilen işaretçiden başka bir nesneye sınıfın yeni bir örneğini başlatır `ComPtrRef` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef:: GetAddressOf](#getaddressof)                     | Geçerli nesne tarafından temsil edilen arabirime yönelik işaretçinin adresini alır `ComPtrRef` .
[ComPtrRef:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | Geçerli nesneyi siler `ComPtrRef` ve nesne tarafından temsil edilen arabirime bir işaretçi işaretçisi döndürür `ComPtrRef` .

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                                     | Açıklama
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef:: operator InterfaceType * *](#operator-interfacetype-star-star) | Geçerli nesneyi siler `ComPtrRef` ve nesne tarafından temsil edilen arabirime bir işaretçi işaretçisi döndürür `ComPtrRef` .
[ComPtrRef:: operator T *](#operator-t-star)                               | Geçerli ComPtrRef nesnesinin [ptr_](comptrrefbase-class.md#ptr) veri üyesinin değerini döndürür.
[ComPtrRef:: operator void * *](#operator-void-star-star)                   | Geçerli nesneyi siler `ComPtrRef` , işaretçiyi nesne tarafından bir işaretçi işaretçisi olarak temsil edilen arabirime çevirir `ComPtrRef` **`void`** ve sonra atama işaretçisini döndürür.
[ComPtrRef:: operator *](#operator-star)                                   | Geçerli nesne tarafından temsil edilen arabirime işaretçiyi alır `ComPtrRef` .
[ComPtrRef:: operator = =](#operator-equality)                              | İki nesnenin eşit olup olmadığını gösterir `ComPtrRef` .
[ComPtrRef:: operator! =](#operator-inequality)                            | İki nesnenin eşit olup olmadığını gösterir `ComPtrRef` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>ComPtrRef:: ComPtrRef

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Başka bir nesnenin temel alınan değeri `ComPtrRef` .

### <a name="remarks"></a>Açıklamalar

`ComPtrRef`Belirtilen işaretçiden başka bir nesneye sınıfın yeni bir örneğini başlatır `ComPtrRef` .

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>ComPtrRef:: GetAddressOf

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesne tarafından temsil edilen arabirim işaretçisinin adresi `ComPtrRef` .

### <a name="remarks"></a>Açıklamalar

Geçerli nesne tarafından temsil edilen arabirime yönelik işaretçinin adresini alır `ComPtrRef` .

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>ComPtrRef:: operator = =

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parametreler

*a*<br/>
Bir `ComPtrRef` nesneye başvuru.

*kenarı*<br/>
Başka bir `ComPtrRef` nesneye veya anonim bir türün işaretçisine () yönelik bir başvuru **`void*`** .

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, **`true`** nesne *b*nesnesine *a* eşitse, aksi takdirde, **`false`** .

İkinci ve üçüncü operatörler **`true`** nesne *a* eşitse **`nullptr`** , aksi takdirde, **`false`** .

Dördüncü ve beşinci operatörler, **`true`** nesne *b*nesnesine *a* eşitse, aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

İki nesnenin eşit olup olmadığını gösterir `ComPtrRef` .

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>ComPtrRef:: operator! =

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parametreler

*a*<br/>
Bir `ComPtrRef` nesneye başvuru.

*kenarı*<br/>
Başka bir `ComPtrRef` nesneye veya bir anonim nesne () işaretçisine yönelik bir başvuru **`void*`** .

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, **`true`** nesne *b*nesnesine *a* eşit değilse, aksi takdirde, olur **`false`** .

İkinci ve üçüncü operatörler, **`true`** nesne *a* eşit değilse **`nullptr`** , aksi takdirde, **`false`** .

Dördüncü ve beşinci operatörler, **`true`** nesne *b*nesnesine *a* eşit değilse, aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

İki nesnenin eşit olup olmadığını gösterir `ComPtrRef` .

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>ComPtrRef:: operator InterfaceType\*\*

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesneyi siler `ComPtrRef` ve nesne tarafından temsil edilen arabirime bir işaretçi işaretçisi döndürür `ComPtrRef` .

## <a name="comptrrefoperator"></a><a name="operator-star"></a>ComPtrRef:: operator *

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesnenin temsil ettiği arabirime yönelik işaretçi `ComPtrRef` .

### <a name="remarks"></a>Açıklamalar

Geçerli nesne tarafından temsil edilen arabirime işaretçiyi alır `ComPtrRef` .

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>ComPtrRef:: operator T *

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator T*();
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesnenin [ptr_](comptrrefbase-class.md#ptr) veri üyesinin değerini döndürür `ComPtrRef` .

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>ComPtrRef:: operator void\*\*

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesneyi siler `ComPtrRef` , işaretçiyi nesne tarafından bir işaretçi işaretçisi olarak temsil edilen arabirime çevirir `ComPtrRef` **`void`** ve sonra atama işaretçisini döndürür.

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtrRef:: ReleaseAndGetAddressOf

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Silinen nesne tarafından temsil edilen arabirime yönelik işaretçi `ComPtrRef` .

### <a name="remarks"></a>Açıklamalar

Geçerli nesneyi siler `ComPtrRef` ve nesne tarafından temsil edilen arabirime bir işaretçi işaretçisi döndürür `ComPtrRef` .
