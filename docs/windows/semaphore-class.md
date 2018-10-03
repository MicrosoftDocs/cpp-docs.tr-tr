---
title: Semafor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 269b3229a0755e88d55fc4fa5d14b843345ccc44
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234460"
---
# <a name="semaphore-class"></a>Semafor Sınıfı

Sınırlı sayıda kullanıcıları destekleyen bir paylaşılan kaynak denetleyen bir eşitleme nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad       | Açıklama
---------- | ------------------------------------------------------
`SyncLock` | Zaman uyumlu kilitleri destekleyen bir sınıf için bir eşanlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                               | Açıklama
---------------------------------- | ----------------------------------------------------
[Semaphore::Semaphore](#semaphore) | Yeni bir örneğini başlatır `Semaphore` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                     | Açıklama
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semaphore::LOCK](#lock) | Geçerli nesne ya da belirtilen işleyici ile ilişkili nesne kadar bekler sinyal verilmiş duruma dönmesine ya da belirtilen zaman aşımı aralığı geçti.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                     | Açıklama
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semaphore::operator =](#operator-assign) | Belirtilen tanıtıcıdan taşır bir `Semaphore` geçerli nesneye `Semaphore` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Semaphore`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="lock"></a>Semaphore::LOCK

Geçerli nesne kadar bekler veya `Semaphore` nesne ile ilişkili belirtilen işleyici içinde sinyal verilmiş duruma dönmesine ya da belirtilen zaman aşımı aralığı geçti.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Parametreler

*Milisaniye*<br/>
Milisaniye cinsinden zaman aşımı aralığı. Varsayılan değer süresiz olarak bekler sonsuzdur.

*h*<br/>
İçin bir tanıtıcı bir `Semaphore` nesne.

### <a name="return-value"></a>Dönüş Değeri

A `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="operator-assign"></a>Semaphore::operator =

Belirtilen tanıtıcıdan taşır bir `Semaphore` geçerli nesneye `Semaphore` nesne.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Rvalue başvuru için bir `Semaphore` nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru `Semaphore` nesne.

## <a name="semaphore"></a>Semaphore::Semaphore

Yeni bir örneğini başlatır `Semaphore` sınıfı.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Tanıtıcı ya da bir rvalue başvurusuna bir `Semaphore` nesne.
