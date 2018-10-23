---
title: Module::ReleaseNotifier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2128164fe3196a77991e755b865357e1aefcac23
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808491"
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
