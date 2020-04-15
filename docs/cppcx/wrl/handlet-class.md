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
ms.openlocfilehash: bde7d7f1bd6730d96cb0f7a0d191a32eb8ed3e8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371461"
---
# <a name="handlet-class"></a>HandleT Sınıfı

Bir nesneye bir tutamacı temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Parametreler

*Kulp Özellikleri*<br/>
[Bir tanıtıcının](handletraits-structure.md) ortak özelliklerini tanımlayan HandleTraits yapısının bir örneği.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı     | Açıklama
-------- | -----------------------------
`Traits` | Bir eşanlamlı `HandleTraits`.

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                | Açıklama
----------------------------------- | --------------------------------------------------
[Elek::Handlet](#handlet)        | `HandleT` sınıfının yeni bir örneğini başlatır.
[Handlet::~Handlet](#tilde-handlet) | Sınıfın bir örneğini `HandleT` deinitialize eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                         | Açıklama
---------------------------- | ----------------------------------------------------------------------
[HandleT::Ekle](#attach)   | Belirtilen tutamacı geçerli `HandleT` nesneyle ilişkilendirer.
[Başa::Kapat](#close)     | Geçerli `HandleT` nesneyi kapatır.
[Kulp::Detach](#detach)   | Geçerli `HandleT` nesneyi alttaki tutamacından susun.
[Handlet::Get](#get)         | Dayanak tutamacın değerini alır.
[Handlet::Geçersiz](#isvalid) | Geçerli `HandleT` nesnenin bir tanıtıcıyı temsil edip etmediğini gösterir.

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                     | Açıklama
---------------------------------------- | ------------------------------------
[Başa::InternalClose](#internalclose) | Geçerli `HandleT` nesneyi kapatır.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                   | Açıklama
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator=](#operator-assign) | Belirtilen `HandleT` nesnenin değerini geçerli `HandleT` nesneye taşır.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[Başa::handle_](#handle) | `HandleT` Nesne tarafından temsil edilen tutamacı içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="handlethandlet"></a><a name="tilde-handlet"></a>Handlet::~Handlet

Sınıfın bir örneğini `HandleT` deinitialize eder.

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a>HandleT::Ekle

Belirtilen tutamacı geçerli `HandleT` nesneyle ilişkilendirer.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir kulp.

## <a name="handletclose"></a><a name="close"></a>Başa::Kapat

Geçerli `HandleT` nesneyi kapatır.

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Akımın altında yatan `HandleT` tutamaç kapatılır `HandleT` ve geçersiz duruma ayarlanır.

Tanıtıcı düzgün kapanmazsa, arama iş parçacığında bir özel durum yükseltilir.

## <a name="handletdetach"></a><a name="detach"></a>Kulp::Detach

Geçerli `HandleT` nesneyi alttaki tutamacından susun.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Altta yatan tutamak.

### <a name="remarks"></a>Açıklamalar

Bu işlem tamamlandığında, akım `HandleT` geçersiz duruma ayarlanır.

## <a name="handletget"></a><a name="get"></a>Handlet::Get

Dayanak tutamacın değerini alır.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kulp.

## <a name="handlethandle_"></a><a name="handle"></a>Başa::handle_

`HandleT` Nesne tarafından temsil edilen tutamacı içerir.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a>Elek::Handlet

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

*H*<br/>
Bir kulp.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, bir `HandleT` nesneye geçerli bir tutamacı olmayan bir nesneyi başharfe alerler. İkinci oluşturucu `HandleT` *h*parametresinden yeni bir nesne oluşturur.

## <a name="handletinternalclose"></a><a name="internalclose"></a>Başa::InternalClose

Geçerli `HandleT` nesneyi kapatır.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Dönüş Değeri

geçerli `HandleT` başarıyla kapalı ise **doğru;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

`InternalClose()``protected`.

## <a name="handletisvalid"></a><a name="isvalid"></a>Handlet::Geçersiz

Geçerli `HandleT` nesnenin bir tanıtıcıyı temsil edip etmediğini gösterir.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

**bir** tutamacı `HandleT` temsil ederse doğrudur; aksi takdirde, **yanlış**.

## <a name="handletoperator"></a><a name="operator-assign"></a>HandleT::operator=

Belirtilen `HandleT` nesnenin değerini geçerli `HandleT` nesneye taşır.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir tanıtıcıya rvalue-reference.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `HandleT` nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu *işlem,* h `HandleT` parametresi ile belirtilen nesneyi geçersiz kılarak
