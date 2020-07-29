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
ms.openlocfilehash: 25fbb23ee7ecb7e55377aed74effe8bfa43a1597
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218370"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier Sınıfı

Bir modüldeki son nesne bırakıldığında bir olay işleyicisini çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                                | Açıklama
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module:: ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Sınıfın geçerli örneğini kaldırır `Module::ReleaseNotifier` .
[Module:: ReleaseNotifier:: ReleaseNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module:: ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | Uygulandığında, modüldeki son nesne bırakıldığında bir olay işleyicisi çağırır.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | `Module::ReleaseNotifier`Nesne bir parametresiyle oluşturulduysa geçerli nesneyi siler **`true`** .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>Module:: ReleaseNotifier:: ~ ReleaseNotifier

Sınıfın geçerli örneğini kaldırır `Module::ReleaseNotifier` .

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>Module:: ReleaseNotifier:: Invoke

Uygulandığında, modüldeki son nesne bırakıldığında bir olay işleyicisi çağırır.

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>Module:: ReleaseNotifier:: Release

`Module::ReleaseNotifier`Nesne bir parametresiyle oluşturulduysa geçerli nesneyi siler **`true`** .

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>Module:: ReleaseNotifier:: ReleaseNotifier

`Module::ReleaseNotifier` sınıfının yeni bir örneğini başlatır.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parametreler

*Yayın*<br/>
**`true`** yöntemi çağrıldığında bu örneği silmek için `Release` ; **`false`** Bu örneği silmemelidir.
