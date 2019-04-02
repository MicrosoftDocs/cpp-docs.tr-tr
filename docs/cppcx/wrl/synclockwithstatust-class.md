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
ms.openlocfilehash: 1c9c0805834a59d10a559bfc2b6da0f10e2fe160
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787812"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Parametreler

*SyncTraits*<br/>
Özel alan bir türü veya bir kaynağa ilişkin paylaşılan sahipliğiniz.

## <a name="remarks"></a>Açıklamalar

Özel alan türünü temsil eder ya da bir kaynak ilişkin paylaşılan sahipliğiniz.

`SyncLockWithStatusT` Sınıfı uygulamak için kullanılan [Mutex](mutex-class.md) ve [semafor](semaphore-class.md) sınıfları.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                             | Açıklama
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT::SyncLockWithStatusT](#synclockwithstatust) | Yeni bir örneğini başlatır `SyncLockWithStatusT` sınıfı.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Ad                                                             | Açıklama
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT::SyncLockWithStatusT](#synclockwithstatust) | Yeni bir örneğini başlatır `SyncLockWithStatusT` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                         | Açıklama
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT::GetStatus](#getstatus) | Geçerli bekleme durumunu alır `SyncLockWithStatusT` nesne.
[Synclockwithstatust::IsLocked](#islocked)   | Belirtir olup olmadığını geçerli `SyncLockWithStatusT` nesnesi bir kaynağa sahiptir; diğer bir deyişle, `SyncLockWithStatusT` nesnedir *kilitli*.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                    | Açıklama
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT::status_](#status) | Geçerli bir nesne üzerinde bir kilit işlemi temel sonra alttaki bekleme işleminin sonucu tutan `SyncLockWithStatusT` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::details

## <a name="getstatus"></a>SyncLockWithStatusT::GetStatus

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alan bir nesne üzerinde bir bekleme işlemini sonucunu `SyncLockWithStatusT` gibi sınıfı bir [Mutex](mutex-class.md) veya [semafor](semaphore-class.md). Sinyal verilmiş duruma dönmesine bekleme işlemi döndürülen sıfır (0) gösterir. geçen zaman aşımı değeri gibi Aksi takdirde, başka bir durum, oluştu.

### <a name="remarks"></a>Açıklamalar

Geçerli bekleme durumunu alır `SyncLockWithStatusT` nesne.

GetStatus() işlevi, temel alınan değeri alır. [status_](#status) veri üyesi. Bir nesne, temel alarak `SyncLockWithStatusT` sınıfı bir kilit işlemi gerçekleştirir, nesne ilk nesne kullanılabilir olana kadar bekler. Bu bekleme işleminin sonucu depolanan `status_` veri üyesi. Olası değerleri `status_` veri üyesi olan dönüş değerlerini bekleme işlemi. Daha fazla bilgi için bkz: dönüş değerlerini `WaitForSingleObjectEx()` MSDN Kitaplığı'nda işlevi.

## <a name="islocked"></a>Synclockwithstatust::IsLocked

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Açıklamalar

Belirtir olup olmadığını geçerli `SyncLockWithStatusT` nesnesi bir kaynağa sahiptir; diğer bir deyişle, `SyncLockWithStatusT` nesnedir *kilitli*.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `SyncLockWithStatusT` nesnedir kilitli; Aksi takdirde **false**.

## <a name="status"></a>SyncLockWithStatusT::status_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
DWORD status_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli bir nesne üzerinde bir kilit işlemi temel sonra alttaki bekleme işleminin sonucu tutan `SyncLockWithStatusT` nesne.

## <a name="synclockwithstatust"></a>SyncLockWithStatusT::SyncLockWithStatusT

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

*Diğer*<br/>
Diğer bir rvalue başvurusuna `SyncLockWithStatusT` nesne.

*Eşitleme*<br/>
Başka bir başvuru `SyncLockWithStatusT` nesne.

*Durumu*<br/>
Değerini [status_](#status) veri üyesi *diğer* parametresi veya *eşitleme* parametresi.

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `SyncLockWithStatusT` sınıfı.

İlk Oluşturucu geçerli başlatır `SyncLockWithStatusT` başka bir nesne `SyncLockWithStatusT` parametresi tarafından belirtilen *diğer*ve diğeri geçersiz kılar `SyncLockWithStatusT` nesne. İkinci oluşturucu `protected`ve geçerli başlatır `SyncLockWithStatusT` nesnesi için geçersiz bir durumda.
