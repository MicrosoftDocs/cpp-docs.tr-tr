---
description: ': Module:: MethodReleaseNotifier Class hakkında daha fazla bilgi'
title: Module::MethodReleaseNotifier Sınıfı
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: 6c0b2569abe8dbebde893bb7c8aee84abc3d8047
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186369"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier Sınıfı

Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi bir nesne ve onun işaretçiden yönteme üyesi tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Üye işlevi olay işleyicisi olan nesnenin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                                                 | Açıklama
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module:: MethodReleaseNotifier:: MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | `Module::MethodReleaseNotifier` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                                   | Açıklama
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module:: MethodReleaseNotifier:: Invoke](#methodreleasenotifier-invoke) | Geçerli nesneyle ilişkili olay işleyicisini çağırır `Module::MethodReleaseNotifier` .

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                                                    | Açıklama
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module:: MethodReleaseNotifier:: method_](#methodreleasenotifier-method) | Geçerli nesne için olay işleyicisine bir işaretçi tutar `Module::MethodReleaseNotifier` .
[Module:: MethodReleaseNotifier:: object_](#methodreleasenotifier-object) | Üye işlevi, geçerli nesne için olay işleyicisi olan nesneye bir işaretçi tutar `Module::MethodReleaseNotifier` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a> Module:: MethodReleaseNotifier:: Invoke

Geçerli nesneyle ilişkili olay işleyicisini çağırır `Module::MethodReleaseNotifier` .

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a> Module:: MethodReleaseNotifier:: method_

Geçerli nesne için olay işleyicisine bir işaretçi tutar `Module::MethodReleaseNotifier` .

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a> Module:: MethodReleaseNotifier:: MethodReleaseNotifier

`Module::MethodReleaseNotifier` sınıfının yeni bir örneğini başlatır.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>Parametreler

*object*<br/>
Üye işlevi olay işleyicisi olan bir nesne.

*yöntemidir*<br/>
Olay işleyicisi olan parametre *nesnesinin* üye işlevi.

*Yayın*<br/>
**`true`** Temeldeki modülün çağrılmasını etkinleştirmek için belirtin [:: ReleaseNotifier:: Release ()](module-releasenotifier-class.md#releasenotifier-release) yöntemi; aksi takdirde, belirtin **`false`** .

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a> Module:: MethodReleaseNotifier:: object_

Üye işlevi, geçerli nesne için olay işleyicisi olan nesneye bir işaretçi tutar `Module::MethodReleaseNotifier` .

```cpp
T* object_;
```
