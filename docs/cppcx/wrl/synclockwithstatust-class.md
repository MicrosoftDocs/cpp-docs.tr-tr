---
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
ms.openlocfilehash: 77bcb8336e4650de7ed01a067fa1bdd7ec0ba3e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374272"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Parametreler

*Eşitleme Özellikleri*<br/>
Kaynağın münhasır veya ortak sahipliğini alabilecek bir tür.

## <a name="remarks"></a>Açıklamalar

Kaynağın münhasır veya ortak sahipliğini alabilecek bir türü temsil eder.

Sınıf `SyncLockWithStatusT` [Mutex](mutex-class.md) ve [Semaphore](semaphore-class.md) sınıfları uygulamak için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                             | Açıklama
---------------------------------------------------------------- | --------------------------------------------------------------
[Synclockwithstatust::synclockwithstatust](#synclockwithstatust) | `SyncLockWithStatusT` sınıfının yeni bir örneğini başlatır.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Adı                                                             | Açıklama
---------------------------------------------------------------- | --------------------------------------------------------------
[Synclockwithstatust::synclockwithstatust](#synclockwithstatust) | `SyncLockWithStatusT` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithstatusT::GetStatus](#getstatus) | Geçerli `SyncLockWithStatusT` nesnenin bekleme durumunu alır.
[SyncLockWithStatusT::Kilitli](#islocked)   | Geçerli `SyncLockWithStatusT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir `SyncLockWithStatusT` şey, nesne *kilitlenir.*

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                                    | Açıklama
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT::status_](#status) | Geçerli `SyncLockWithStatusT` nesneye dayalı bir kilit işleminden sonra temel bekleme işleminin sonucunu tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::D kuyrukları

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a>SyncLockWithstatusT::GetStatus

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

`SyncLockWithStatusT` [Mutex](mutex-class.md) veya [Semaphore](semaphore-class.md)gibi sınıfa dayalı nesne üzerinde bir bekleme işleminin sonucu. Sıfır (0), bekleme işleminin sinyal durumunu döndürür; aksi takdirde, geçen zaman aşımı değeri gibi başka bir durum oluştu.

### <a name="remarks"></a>Açıklamalar

Geçerli `SyncLockWithStatusT` nesnenin bekleme durumunu alır.

GetStatus() işlevi, alttaki [status_](#status) veri üyesinin değerini alır. `SyncLockWithStatusT` Sınıfa dayalı bir nesne bir kilit işlemi gerçekleştirirse, nesne önce nesnenin kullanılabilir olmasını bekler. Bu bekleme işleminin sonucu veri `status_` üyesinde depolanır. Veri üyesinin `status_` olası değerleri bekleme işleminin iade değerleridir. Daha fazla bilgi için, MSDN Kitaplığı'ndaki işlevin `WaitForSingleObjectEx()` geri dönüş değerlerine bakın.

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a>SyncLockWithStatusT::Kilitli

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `SyncLockWithStatusT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir `SyncLockWithStatusT` şey, nesne *kilitlenir.*

### <a name="return-value"></a>Dönüş Değeri

`SyncLockWithStatusT` nesne kilitliyse **doğru;** aksi takdirde, **yanlış**.

## <a name="synclockwithstatuststatus_"></a><a name="status"></a>SyncLockWithStatusT::status_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
DWORD status_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `SyncLockWithStatusT` nesneye dayalı bir kilit işleminden sonra temel bekleme işleminin sonucunu tutar.

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a>Synclockwithstatust::synclockwithstatust

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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

*Diğer*<br/>
Başka bir `SyncLockWithStatusT` nesneye rvalue-reference.

*Eşitleme*<br/>
Başka bir `SyncLockWithStatusT` nesneye başvuru.

*Durum*<br/>
*Diğer* parametrenin veya *eşitleme* parametresinin [status_](#status) veri üyesinin değeri.

### <a name="remarks"></a>Açıklamalar

`SyncLockWithStatusT` sınıfının yeni bir örneğini başlatır.

İlk oluşturucu, *diğer*parametre ile `SyncLockWithStatusT` belirtilen başka bir diğerinden geçerli `SyncLockWithStatusT` `SyncLockWithStatusT` nesneyi başharfe ait hale gelirse ve diğer nesneyi geçersiz kılarak geçersiz kılınır. İkinci oluşturucu `protected`ve geçersiz bir duruma `SyncLockWithStatusT` geçerli nesneyi başharf.
