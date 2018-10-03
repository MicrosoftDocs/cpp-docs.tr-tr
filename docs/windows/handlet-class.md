---
title: HandleT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2018
ms.technology:
- cpp-windows
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb39d7418ece213e9c36c048fb5bcd3c000beca4
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235327"
---
# <a name="handlet-class"></a>HandleT Sınıfı

Bir tutamacı nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename HandleTraits
>
class HandleT;
```

### <a name="parameters"></a>Parametreler

*HandleTraits*<br/>
Örneği [HandleTraits](../windows/handletraits-structure.md) ortak bir tanıtıcı özelliklerini tanımlayan bir yapıda.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad     | Açıklama
-------- | -----------------------------
`Traits` | İçin bir eşanlamlı `HandleTraits`.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                | Açıklama
----------------------------------- | --------------------------------------------------
[HandleT::HandleT](#handlet)        | Yeni bir örneğini başlatır `HandleT` sınıfı.
[HandleT:: ~ HandleT](#tilde-handlet) | Örneği başlatılmasını geri alır `HandleT` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                         | Açıklama
---------------------------- | ----------------------------------------------------------------------
[HandleT::Attach](#attach)   | Belirtilen tanıtıcı geçerli ilişkilendirir `HandleT` nesne.
[HandleT::Close](#close)     | Geçerli kapatır `HandleT` nesne.
[HandleT::Detach](#detach)   | Geçerli ayırır `HandleT` , temel alınan tanıtıcısını nesne.
[HandleT::Get](#get)         | Temel alınan tanıtıcısının değerini alır.
[Handlet::IsValid](#isvalid) | Belirtir olup olmadığını geçerli `HandleT` nesnesi bir işleyici temsil eder.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                     | Açıklama
---------------------------------------- | ------------------------------------
[Handlet::ınternalclose](#internalclose) | Geçerli kapatır `HandleT` nesne.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                   | Açıklama
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator =](#operator-assign) | Belirtilen değer taşır `HandleT` geçerli nesneye `HandleT` nesne.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[HandleT::handle_](#handle) | Tarafından temsil edilen tanıtıcı içeren `HandleT` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="tilde-handlet"></a>HandleT:: ~ HandleT

Örneği başlatılmasını geri alır `HandleT` sınıfı.

```cpp
~HandleT();
```

## <a name="attach"></a>HandleT::Attach

Belirtilen tanıtıcı geçerli ilişkilendirir `HandleT` nesne.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Tanıtıcı.

## <a name="close"></a>HandleT::Close

Geçerli kapatır `HandleT` nesne.

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Geçerli altını tanıtıcı `HandleT` kapatılır ve `HandleT` geçersiz duruma ayarlanır.

Tanıtıcı düzgün kapatmadığına, çağıran iş parçacığında bir özel durum oluşturulur.

## <a name="detach"></a>HandleT::Detach

Geçerli ayırır `HandleT` , temel alınan tanıtıcısını nesne.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu işlem tamamlandığında, geçerli `HandleT` geçersiz duruma ayarlanır.

## <a name="get"></a>HandleT::Get

Temel alınan tanıtıcısının değerini alır.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı.

## <a name="handle"></a>HandleT::handle_

Tarafından temsil edilen tanıtıcı içeren `HandleT` nesne.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>HandleT::HandleT

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
Tanıtıcı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu başlatan bir `HandleT` değil bir nesne için geçerli bir tanıtıcı nesnesi. İkinci oluşturucu yeni bir oluşturur `HandleT` parametre nesneden *h*.

## <a name="internalclose"></a>Handlet::ınternalclose

Geçerli kapatır `HandleT` nesne.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Dönüş Değeri

`true` varsa geçerli `HandleT` kapalı başarıyla; Aksi takdirde `false`.

### <a name="remarks"></a>Açıklamalar

`InternalClose()` olan `protected`.

## <a name="isvalid"></a>Handlet::IsValid

Belirtir olup olmadığını geçerli `HandleT` nesnesi bir işleyici temsil eder.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

`true` varsa `HandleT` temsil eden bir işleyici; Aksi takdirde `false`.

## <a name="operator-assign"></a>HandleT::operator =

Belirtilen değer taşır `HandleT` geçerli nesneye `HandleT` nesne.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir rvalue başvuru için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru `HandleT` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlem geçersiz kılar `HandleT` parametresi tarafından belirtilen nesne *h*.
