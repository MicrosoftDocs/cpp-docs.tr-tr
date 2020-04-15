---
title: Module::ReleaseNotifier Sınıfı
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: f314d09c443d0d284e3a821b5c879bfb74baf812
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371284"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier Sınıfı

Modüldeki son nesne serbest bırakıldığında bir olay işleyicisi çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                                                | Açıklama
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Modül::ReleaseNotifier::~ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Sınıfın geçerli örneğini `Module::ReleaseNotifier` deinitialize eder.
[Modül::ReleaseNotifier::ReleaseNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                         | Açıklama
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Modül::ReleaseNotifier::Invoke](#releasenotifier-invoke)   | Uygulandığında, modüldeki son nesne serbest bırakıldığında olay işleyicisi çağırır.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Nesne gerçek `Module::ReleaseNotifier` bir parametre ile oluşturulmuşsa **true**geçerli nesneyi siler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>Modül::ReleaseNotifier::~ReleaseNotifier

Sınıfın geçerli örneğini `Module::ReleaseNotifier` deinitialize eder.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>Modül::ReleaseNotifier::Invoke

Uygulandığında, modüldeki son nesne serbest bırakıldığında olay işleyicisi çağırır.

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>Modül::ReleaseNotifier::Yayın

Nesne gerçek `Module::ReleaseNotifier` bir parametre ile oluşturulmuşsa **true**geçerli nesneyi siler.

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>Modül::ReleaseNotifier::ReleaseNotifier

`Module::ReleaseNotifier` sınıfının yeni bir örneğini başlatır.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parametreler

*Sürüm*<br/>
`true``Release` yöntem çağrıldığında bu örneği silmek için; `false` bu örneği silmek için değil.
