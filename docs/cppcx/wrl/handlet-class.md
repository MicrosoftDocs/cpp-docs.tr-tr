---
title: HandleT Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: f66fbe23c305be15e09928242175dfa7ce8c141b
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821824"
---
# <a name="handlet-class"></a>HandleT Sınıfı

Bir nesneye olan tanıtıcıyı temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Parametreler

*HandleTraits*<br/>
Bir tanıtıcının ortak özelliklerini tanımlayan [Handlenitelikleri](handletraits-structure.md) yapısının bir örneği.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Name     | Açıklama
-------- | -----------------------------
`Traits` | `HandleTraits`için eş anlamlı.

### <a name="public-constructors"></a>Genel Oluşturucular

Name                                | Açıklama
----------------------------------- | --------------------------------------------------
[HandleT:: HandleT](#handlet)        | Yeni bir örneğini başlatır `HandleT` sınıfı.
[HandleT:: ~ HandleT](#tilde-handlet) | `HandleT` sınıfının bir örneğini kaldırır.

### <a name="public-methods"></a>Genel Yöntemler

Name                         | Açıklama
---------------------------- | ----------------------------------------------------------------------
[HandleT:: Attach](#attach)   | Belirtilen tanıtıcıyı geçerli `HandleT` nesnesi ile ilişkilendirir.
[HandleT:: Close](#close)     | Geçerli `HandleT` nesnesini kapatır.
[HandleT::D etach](#detach)   | Geçerli `HandleT` nesnesini temeldeki tanıtıcıdan ayırır.
[HandleT:: Get](#get)         | Temel alınan tanıtıcının değerini alır.
[HandleT:: IsValid](#isvalid) | Geçerli `HandleT` nesnesinin bir tanıtıcıyı temsil edip etmediğini gösterir.

### <a name="protected-methods"></a>Korumalı Yöntemler

Name                                     | Açıklama
---------------------------------------- | ------------------------------------
[HandleT:: InternalClose](#internalclose) | Geçerli `HandleT` nesnesini kapatır.

### <a name="public-operators"></a>Genel İşleçler

Name                                   | Açıklama
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT:: operator =](#operator-assign) | Belirtilen `HandleT` nesnesinin değerini geçerli `HandleT` nesnesine kaydırır.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Name                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[HandleT:: handle_](#handle) | `HandleT` nesnesi tarafından temsil edilen tanıtıcıyı içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="tilde-handlet"></a>HandleT:: ~ HandleT

`HandleT` sınıfının bir örneğini kaldırır.

```cpp
~HandleT();
```

## <a name="attach"></a>HandleT:: Attach

Belirtilen tanıtıcıyı geçerli `HandleT` nesnesi ile ilişkilendirir.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir tanıtıcı.

## <a name="close"></a>HandleT:: Close

Geçerli `HandleT` nesnesini kapatır.

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Geçerli `HandleT` bulunan tanıtıcı kapalıdır ve `HandleT` geçersiz duruma ayarlanır.

Tanıtıcı doğru şekilde kapanmazsa, çağıran iş parçacığında bir özel durum oluşturulur.

## <a name="detach"></a>HandleT::D etach

Geçerli `HandleT` nesnesini temeldeki tanıtıcıdan ayırır.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu işlem tamamlandığında geçerli `HandleT` geçersiz duruma ayarlanır.

## <a name="get"></a>HandleT:: Get

Temel alınan tanıtıcının değerini alır.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcı.

## <a name="handle"></a>HandleT:: handle_

`HandleT` nesnesi tarafından temsil edilen tanıtıcıyı içerir.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>HandleT:: HandleT

Yeni bir örneğini başlatır `HandleT` sınıfı.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir nesne için geçerli bir tanıtıcı olmayan bir `HandleT` nesnesini başlatır. İkinci Oluşturucu *h*parametresinden yeni bir `HandleT` nesnesi oluşturur.

## <a name="internalclose"></a>HandleT:: InternalClose

Geçerli `HandleT` nesnesini kapatır.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Dönüş Değeri

geçerli `HandleT` başarıyla kapatılırsa **doğru** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

`InternalClose()` `protected`.

## <a name="isvalid"></a>HandleT:: IsValid

Geçerli `HandleT` nesnesinin bir tanıtıcıyı temsil edip etmediğini gösterir.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

`HandleT` bir tanıtıcıyı temsil ediyorsa **true** ; Aksi takdirde, **false**.

## <a name="operator-assign"></a>HandleT:: operator =

Belirtilen `HandleT` nesnesinin değerini geçerli `HandleT` nesnesine kaydırır.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir tanıtıcıya bir rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `HandleT` nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlem *h*parametresi tarafından belirtilen `HandleT` nesnesini geçersiz kılar.
