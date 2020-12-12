---
description: 'Daha fazla bilgi edinin: SyncLockWithStatusT sınıfı'
title: SyncLockWithStatusT Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: 6a19ae22253fddd48c7baaf29e4b88a4863b89bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186161"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Parametreler

*Syncnitelikler*<br/>
Bir kaynağın özel veya paylaşılan sahipliğini ele alan bir tür.

## <a name="remarks"></a>Açıklamalar

Bir kaynağın özel veya paylaşılan sahipliğini alabileceği bir türü temsil eder.

`SyncLockWithStatusT`Sınıfı, [mutex](mutex-class.md) ve [semafor](semaphore-class.md) sınıflarını uygulamak için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                             | Açıklama
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT:: SyncLockWithStatusT](#synclockwithstatust) | `SyncLockWithStatusT` sınıfının yeni bir örneğini başlatır.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Ad                                                             | Açıklama
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT:: SyncLockWithStatusT](#synclockwithstatust) | `SyncLockWithStatusT` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT:: GetStatus](#getstatus) | Geçerli nesnenin bekleme durumunu alır `SyncLockWithStatusT` .
[SyncLockWithStatusT:: ıskilitlendi](#islocked)   | Geçerli `SyncLockWithStatusT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, `SyncLockWithStatusT` nesne *kilitlenir*.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                    | Açıklama
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT:: status_](#status) | Geçerli nesneye dayalı bir nesne üzerindeki kilit işleminden sonra temeldeki bekleme işleminin sonucunu tutar `SyncLockWithStatusT` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar::D euçlar

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a> SyncLockWithStatusT:: GetStatus

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

`SyncLockWithStatusT`Bir [mutex](mutex-class.md) veya [semafor](semaphore-class.md)gibi sınıfı temel alan nesne üzerindeki bir bekleme işleminin sonucu. Sıfır (0), bekleme işleminin sinyal verilen durumu döndürmediğini belirtir; Aksi takdirde, zaman aşımı değeri gibi başka bir durum ortaya çıkar.

### <a name="remarks"></a>Açıklamalar

Geçerli nesnenin bekleme durumunu alır `SyncLockWithStatusT` .

GetStatus () işlevi, temel alınan [status_](#status) veri üyesinin değerini alır. Sınıfı temel alan bir nesne `SyncLockWithStatusT` bir kilit işlemi gerçekleştirdiğinde, nesne önce nesnenin kullanılabilir hale gelmesini bekler. Bu bekleme işleminin sonucu `status_` veri üyesinde saklanır. Veri üyesinin olası değerleri, `status_` bekleme işleminin dönüş değerleridir. Daha fazla bilgi için, bkz. işlevin dönüş değerleri [`WaitForSingleObjectEx`](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobjectex) .

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a> SyncLockWithStatusT:: ıskilitlendi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `SyncLockWithStatusT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, `SyncLockWithStatusT` nesne *kilitlenir*.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`SyncLockWithStatusT`nesne kilitliyse, tersi durumda **`false`** .

## <a name="synclockwithstatuststatus_"></a><a name="status"></a> SyncLockWithStatusT:: status_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
DWORD status_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesneye dayalı bir nesne üzerindeki kilit işleminden sonra temeldeki bekleme işleminin sonucunu tutar `SyncLockWithStatusT` .

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a> SyncLockWithStatusT:: SyncLockWithStatusT

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bir rvalue başvurusu, başka bir `SyncLockWithStatusT` nesneye başvuru.

*Eşitleme*<br/>
Başka bir nesneye başvuru `SyncLockWithStatusT` .

*durumlarına*<br/>
*Diğer* parametrenin [status_](#status) veri üyesinin veya *Sync* parametresinin değeri.

### <a name="remarks"></a>Açıklamalar

`SyncLockWithStatusT` sınıfının yeni bir örneğini başlatır.

İlk Oluşturucu geçerli `SyncLockWithStatusT` nesneyi `SyncLockWithStatusT` *diğer* parametreye göre belirtilen başka bir nesneden başlatır ve ardından diğer nesneyi geçersiz kılar `SyncLockWithStatusT` . İkinci Oluşturucu olur **`protected`** ve geçerli `SyncLockWithStatusT` nesneyi geçersiz bir duruma başlatır.
