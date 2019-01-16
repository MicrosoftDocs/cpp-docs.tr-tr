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
ms.openlocfilehash: 281e02d85e70a84530e6980d31669a73091448d5
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335003"
---
# <a name="comptrref-class"></a>ComPtrRef Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
A [ComPtr\<T >](comptr-class.md) türü veya tür, kesmenin tarafından temsil edilen arabirim sınıfından türetilen `ComPtr`.

## <a name="remarks"></a>Açıklamalar

Bir nesne türü bir başvuruyu temsil eder `ComPtr<T>`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                               | Açıklama
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef::ComPtrRef](#comptrref) | Yeni bir örneğini başlatır `ComPtrRef` belirtilen işaretçisinden sınıfa `ComPtrRef` nesne.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::GetAddressOf](#getaddressof)                     | Adresi geçerli tarafından temsil edilen arabirimi için bir işaretçi alır `ComPtrRef` nesne.
[ComPtrRef::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Geçerli siler `ComPtrRef` nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür `ComPtrRef` nesne.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                                     | Açıklama
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::operator InterfaceType **](#operator-interfacetype-star-star) | Geçerli siler `ComPtrRef` nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür `ComPtrRef` nesne.
[ComPtrRef::operator T *](#operator-t-star)                               | Değerini döndürür [ptr_](comptrrefbase-class.md#ptr) geçerli ComPtrRef nesnenin veri üyesi.
[ComPtrRef::operator void **](#operator-void-star-star)                   | Geçerli siler `ComPtrRef` nesne, işaretçi tarafından temsil arabirimine bıraktığı `ComPtrRef` nesnesi olarak bir işaretçiyi-için-işaretçi- `void`ve ardından atama işaretçiyi döndürür.
[ComPtrRef::operator*](#operator-star)                                   | Geçerli tarafından temsil edilen arabirim işaretçisi alır `ComPtrRef` nesne.
[ComPtrRef::operator==](#operator-equality)                              | Belirtir olup iki `ComPtrRef` nesneler.
[ComPtrRef::operator!=](#operator-inequality)                            | Belirtir olup iki `ComPtrRef` nesneler eşit değildir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="comptrref"></a>ComPtrRef::ComPtrRef

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Temeldeki değeri başka bir `ComPtrRef` nesne.

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `ComPtrRef` belirtilen işaretçisinden sınıfa `ComPtrRef` nesne.

## <a name="getaddressof"></a>ComPtrRef::GetAddressOf

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Adres geçerli tarafından temsil edilen arabirimi için bir işaretçi `ComPtrRef` nesne.

### <a name="remarks"></a>Açıklamalar

Adresi geçerli tarafından temsil edilen arabirimi için bir işaretçi alır `ComPtrRef` nesne.

## <a name="operator-equality"></a>ComPtrRef::operator==

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
Bir başvuru bir `ComPtrRef` nesne.

*b*<br/>
Başka bir başvuru `ComPtrRef` nesne veya anonim bir tür için bir işaretçi (`void*`).

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sayıları **true** , nesne *bir* nesneye eşit olup *b*; Aksi takdirde **false**.

İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşittir **nullptr**; Aksi takdirde **false**.

Dördüncü ve beşinci işleçleri yield **true** , nesne *bir* nesneye eşit olup *b*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Belirtir olup iki `ComPtrRef` nesneler.

## <a name="operator-inequality"></a>ComPtrRef::operator!=

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
Bir başvuru bir `ComPtrRef` nesne.

*b*<br/>
Başka bir başvuru `ComPtrRef` nesne veya anonim bir nesneye bir işaretçi (`void*`).

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sayıları **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.

İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşit değildir **nullptr**; Aksi takdirde **false**.

Dördüncü ve beşinci işleçleri yield **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Belirtir olup iki `ComPtrRef` nesneler eşit değildir.

## <a name="operator-interfacetype-star-star"></a>ComPtrRef::operator InterfaceType **

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Açıklamalar

Geçerli siler `ComPtrRef` nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür `ComPtrRef` nesne.

## <a name="operator-star"></a>ComPtrRef::operator *

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli tarafından temsil edilen bir arabirim işaretçisine `ComPtrRef` nesne.

### <a name="remarks"></a>Açıklamalar

Geçerli tarafından temsil edilen arabirim işaretçisi alır `ComPtrRef` nesne.

## <a name="operator-t-star"></a>ComPtrRef::operator T *

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator T*();
```

### <a name="remarks"></a>Açıklamalar

Değerini döndürür [ptr_](comptrrefbase-class.md#ptr) geçerli veri üyesi `ComPtrRef` nesne.

## <a name="operator-void-star-star"></a>ComPtrRef::operator void\*\*

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli siler `ComPtrRef` nesne, işaretçi tarafından temsil arabirimine bıraktığı `ComPtrRef` nesnesi olarak bir işaretçiyi-için-işaretçi- `void`ve ardından atama işaretçiyi döndürür.

## <a name="releaseandgetaddressof"></a>ComPtrRef::ReleaseAndGetAddressOf

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Dönüş Değeri

Sunulacağı arabirim işaretçisi tarafından silinen `ComPtrRef` nesne.

### <a name="remarks"></a>Açıklamalar

Geçerli siler `ComPtrRef` nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür `ComPtrRef` nesne.
