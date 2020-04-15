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
ms.openlocfilehash: df9ded817227547493c04035e0abc3d948e24495
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372630"
---
# <a name="comptrref-class"></a>ComPtrRef Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[ComPtr\<T>](comptr-class.md) türü veya ondan türetilen bir tür, sadece arayüz tarafından temsil edilen . `ComPtr`

## <a name="remarks"></a>Açıklamalar

Türdeki `ComPtr<T>`bir nesneye başvurutemsil eder.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                               | Açıklama
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef::ComPtrRef](#comptrref) | Belirtilen işaretçiden başka `ComPtrRef` `ComPtrRef` bir nesneye sınıfın yeni bir örneğini başolarak adlandırır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                         | Açıklama
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::GetAddressOf](#getaddressof)                     | Geçerli `ComPtrRef` nesne tarafından temsil edilen arabirimin işaretçi adresini alır.
[ComPtrRef::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Geçerli `ComPtrRef` nesneyi siler ve `ComPtrRef` işaretçiden işaretçiye nesne tarafından temsil edilen arabirime döndürür.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                                                     | Açıklama
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::operatör InterfaceType**](#operator-interfacetype-star-star) | Geçerli `ComPtrRef` nesneyi siler ve `ComPtrRef` işaretçiden işaretçiye nesne tarafından temsil edilen arabirime döndürür.
[ComPtrRef::operatör T*](#operator-t-star)                               | Geçerli ComPtrRef nesnesinin [ptr_](comptrrefbase-class.md#ptr) veri üyesinin değerini verir.
[ComPtrRef::operatör geçersiz**](#operator-void-star-star)                   | Geçerli `ComPtrRef` nesneyi siler, işaretçiyi `ComPtrRef` nesne tarafından temsil edilen arabirime işaretçiye `void`işaretçi olarak atar ve ardından döküm işaretçisini döndürür.
[ComPtrRef::operatör*](#operator-star)                                   | Geçerli `ComPtrRef` nesne tarafından temsil edilen arabirimin işaretçisini alır.
[ComPtrRef::operator==](#operator-equality)                              | İki nesnenin `ComPtrRef` eşit olup olmadığını gösterir.
[ComPtrRef::operatör!=](#operator-inequality)                            | İki nesnenin `ComPtrRef` eşit olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** client.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>ComPtrRef::ComPtrRef

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*Ptr*<br/>
Başka bir `ComPtrRef` nesnenin temel değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen işaretçiden başka `ComPtrRef` `ComPtrRef` bir nesneye sınıfın yeni bir örneğini başolarak adlandırır.

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>ComPtrRef::GetAddressOf

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtrRef` nesne tarafından temsil edilen arabirimin işaretçisinin adresi.

### <a name="remarks"></a>Açıklamalar

Geçerli `ComPtrRef` nesne tarafından temsil edilen arabirimin işaretçi adresini alır.

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>ComPtrRef::operator==

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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

*A*<br/>
Bir `ComPtrRef` nesneye başvuru.

*B*<br/>
Başka bir `ComPtrRef` nesneye başvuru veya anonim bir`void*`türe işaretçi ( ).

### <a name="return-value"></a>Dönüş Değeri

*A* nesnesi *b*nesnesine eşitse ilk işleç **doğru** verir; aksi takdirde, **yanlış**.

A *nesnesi* **nullptr'a**eşitse ikinci ve üçüncü işleçler **doğru** verim verir; aksi takdirde, **yanlış**.

Dördüncü ve beşinci işleçler, *a* nesnesi *b*nesnesine eşitse **doğru** verim verir; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

İki nesnenin `ComPtrRef` eşit olup olmadığını gösterir.

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>ComPtrRef::operatör!=

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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

*A*<br/>
Bir `ComPtrRef` nesneye başvuru.

*B*<br/>
Başka bir `ComPtrRef` nesneye başvuru veya anonim bir`void*`nesneye işaretçi ( ).

### <a name="return-value"></a>Dönüş Değeri

*A* nesnesi *b*nesnesine eşit değilse ilk işleç **doğru** verir; aksi takdirde, **yanlış**.

A *nesnesi* **nullptr'a**eşit değilse ikinci ve üçüncü işleçler **doğru** verim verir; aksi takdirde, **yanlış**.

Dördüncü ve beşinci işleçler, *a* nesnesi *b*nesnesine eşit değilse **doğru** verim verir; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

İki nesnenin `ComPtrRef` eşit olup olmadığını gösterir.

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>ComPtrRef::operatör InterfaceType**

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Açıklamalar

Geçerli `ComPtrRef` nesneyi siler ve `ComPtrRef` işaretçiden işaretçiye nesne tarafından temsil edilen arabirime döndürür.

## <a name="comptrrefoperator"></a><a name="operator-star"></a>ComPtrRef::operatör*

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `ComPtrRef` nesne tarafından temsil edilen arabirimeye işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli `ComPtrRef` nesne tarafından temsil edilen arabirimin işaretçisini alır.

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>ComPtrRef::operatör T*

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
operator T*();
```

### <a name="remarks"></a>Açıklamalar

Geçerli `ComPtrRef` nesnenin [ptr_](comptrrefbase-class.md#ptr) veri üyesinin değerini verir.

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>ComPtrRef::operatör geçersiz\*\*

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `ComPtrRef` nesneyi siler, işaretçiyi `ComPtrRef` nesne tarafından temsil edilen arabirime işaretçiye `void`işaretçi olarak atar ve ardından döküm işaretçisini döndürür.

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtrRef::ReleaseAndGetAddressOf

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Silinen `ComPtrRef` nesne tarafından temsil edilen arabirimi işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli `ComPtrRef` nesneyi siler ve `ComPtrRef` işaretçiden işaretçiye nesne tarafından temsil edilen arabirime döndürür.
