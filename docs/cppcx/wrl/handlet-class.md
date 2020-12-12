---
description: 'Daha fazla bilgi edinin: HandleT Sınıfı'
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
ms.openlocfilehash: 608433193729e3d9be5b9490c469bf0b04d3531c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250016"
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

Ad     | Açıklama
-------- | -----------------------------
`Traits` | İçin bir eş anlamlı `HandleTraits` .

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                | Açıklama
----------------------------------- | --------------------------------------------------
[HandleT:: HandleT](#handlet)        | `HandleT` sınıfının yeni bir örneğini başlatır.
[HandleT:: ~ HandleT](#tilde-handlet) | Sınıfının bir örneğini kaldırır `HandleT` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                         | Açıklama
---------------------------- | ----------------------------------------------------------------------
[HandleT:: Attach](#attach)   | Belirtilen tanıtıcıyı geçerli `HandleT` nesneyle ilişkilendirir.
[HandleT:: Close](#close)     | Geçerli nesneyi kapatır `HandleT` .
[HandleT::D etach](#detach)   | Geçerli `HandleT` nesneyi temeldeki tanıtıcıdan ayırır.
[HandleT:: Get](#get)         | Temel alınan tanıtıcının değerini alır.
[HandleT:: IsValid](#isvalid) | Geçerli `HandleT` nesnenin bir tanıtıcıyı temsil edip etmediğini gösterir.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                     | Açıklama
---------------------------------------- | ------------------------------------
[HandleT:: InternalClose](#internalclose) | Geçerli nesneyi kapatır `HandleT` .

### <a name="public-operators"></a>Ortak İşleçler

Ad                                   | Açıklama
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT:: operator =](#operator-assign) | Belirtilen `HandleT` nesnenin değerini geçerli `HandleT` nesneye kaydırır.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[HandleT:: handle_](#handle) | Nesnesi tarafından temsil edilen tanıtıcıyı içerir `HandleT` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="handlethandlet"></a><a name="tilde-handlet"></a> HandleT:: ~ HandleT

Sınıfının bir örneğini kaldırır `HandleT` .

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a> HandleT:: Attach

Belirtilen tanıtıcıyı geçerli `HandleT` nesneyle ilişkilendirir.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir tanıtıcı.

## <a name="handletclose"></a><a name="close"></a> HandleT:: Close

Geçerli nesneyi kapatır `HandleT` .

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Geçerli olan tanıtıcı `HandleT` kapalıdır ve `HandleT` geçersiz duruma ayarlanır.

Tanıtıcı doğru şekilde kapanmazsa, çağıran iş parçacığında bir özel durum oluşturulur.

## <a name="handletdetach"></a><a name="detach"></a> HandleT::D etach

Geçerli `HandleT` nesneyi temeldeki tanıtıcıdan ayırır.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu işlem tamamlandığında, geçerli `HandleT` durum geçersiz duruma ayarlanır.

## <a name="handletget"></a><a name="get"></a> HandleT:: Get

Temel alınan tanıtıcının değerini alır.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcı.

## <a name="handlethandle_"></a><a name="handle"></a> HandleT:: handle_

Nesnesi tarafından temsil edilen tanıtıcıyı içerir `HandleT` .

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a> HandleT:: HandleT

`HandleT` sınıfının yeni bir örneğini başlatır.

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

İlk Oluşturucu bir `HandleT` nesne için geçerli bir tanıtıcı olmayan bir nesne başlatır. İkinci Oluşturucu h parametresinden yeni bir `HandleT` nesne oluşturur. 

## <a name="handletinternalclose"></a><a name="internalclose"></a> HandleT:: InternalClose

Geçerli nesneyi kapatır `HandleT` .

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli bir `HandleT` şekilde kapatılırsa, aksi durumda, **`false`** .

### <a name="remarks"></a>Açıklamalar

`InternalClose()`**`protected`**.

## <a name="handletisvalid"></a><a name="isvalid"></a> HandleT:: IsValid

Geçerli `HandleT` nesnenin bir tanıtıcıyı temsil edip etmediğini gösterir.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Eğer Eğer `HandleT` bir tanıtıcıyı temsil ediyorsa, tersi durumda **`false`** .

## <a name="handletoperator"></a><a name="operator-assign"></a> HandleT:: operator =

Belirtilen `HandleT` nesnenin değerini geçerli `HandleT` nesneye kaydırır.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir tanıtıcıya bir rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru `HandleT` .

### <a name="remarks"></a>Açıklamalar

Bu işlem `HandleT` *h* parametresi tarafından belirtilen nesneyi geçersiz kılar.
