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
ms.openlocfilehash: 5fc1b8965bf8bf2f86dd30f2195fa825f85f6d7e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787049"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier Sınıfı

Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                                | Açıklama
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module::ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Geçerli örneğinin başlatmasını geri alır `Module::ReleaseNotifier` sınıfı.
[Module::releasenotifier:: releasenotifier](#releasenotifier-releasenotifier)        | Yeni bir örneğini başlatır `Module::ReleaseNotifier` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module::ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | Modül içindeki son nesnenin serbest bırakıldığında uygulandığında, bir olay işleyici çağırır.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Geçerli siler `Module::ReleaseNotifier` nesnesi bir parametre ile oluşturulmuş nesne **true**.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module::ReleaseNotifier:: ~ ReleaseNotifier

Geçerli örneğinin başlatmasını geri alır `Module::ReleaseNotifier` sınıfı.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module::ReleaseNotifier:: Invoke

Modül içindeki son nesnenin serbest bırakıldığında uygulandığında, bir olay işleyici çağırır.

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Module::ReleaseNotifier::Release

Geçerli siler `Module::ReleaseNotifier` nesnesi bir parametre ile oluşturulmuş nesne **true**.

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Module::releasenotifier:: releasenotifier

Yeni bir örneğini başlatır `Module::ReleaseNotifier` sınıfı.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parametreler

*Yayın*<br/>
`true` silmek için bu örnek zaman `Release` yöntemi çağrılır; `false` Bu örneği silmemeyi.
