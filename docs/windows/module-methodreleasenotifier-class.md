---
title: Module::MethodReleaseNotifier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68f85794c8d70d642295f9125ac45311df29f16e
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163523"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier Sınıfı

Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyicisi, bir nesne ve onun yöntemi için işaretçi üye tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Olay işleyicisi üye işlevi olan nesnenin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                                                 | Açıklama
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module::methodreleasenotifier:: methodreleasenotifier](#methodreleasenotifier-methodreleasenotifier) | Yeni bir örneğini başlatır `Module::MethodReleaseNotifier` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                                   | Açıklama
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier:: Invoke](#methodreleasenotifier-invoke) | Geçerli ile ilişkili olay işleyicisini çağırır `Module::MethodReleaseNotifier` nesne.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                                                    | Açıklama
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module::methodreleasenotifier:: method_](#methodreleasenotifier-method) | İçin geçerli olay işleyicisine bir işaretçiyi tuttuğu `Module::MethodReleaseNotifier` nesne.
[Module::methodreleasenotifier:: object_](#methodreleasenotifier-object) | Üye işlevi için geçerli olay işleyicisi olan nesneye bir işaretçi tutan `Module::MethodReleaseNotifier` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="methodreleasenotifier-invoke"></a>Module::MethodReleaseNotifier:: Invoke

Geçerli ile ilişkili olay işleyicisini çağırır `Module::MethodReleaseNotifier` nesne.

```cpp
void Invoke();
```

## <a name="methodreleasenotifier-method"></a>Module::methodreleasenotifier:: method_

İçin geçerli olay işleyicisine bir işaretçiyi tuttuğu `Module::MethodReleaseNotifier` nesne.

```cpp
void (T::* method_)();
```

## <a name="methodreleasenotifier-methodreleasenotifier"></a>Module::methodreleasenotifier:: methodreleasenotifier

Yeni bir örneğini başlatır `Module::MethodReleaseNotifier` sınıfı.

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
Bir olay işleyicisi üye işlevi olan nesne.

*Yöntemi*<br/>
Üye işlevi parametresinin *nesne* yani olay işleyicisi.

*Yayın*<br/>
Belirtin **true** temel çağırma etkinleştirmek için [Modülü:: ReleaseNotifier::Release()](../windows/module-releasenotifier-class.md#releasenotifier-release) yöntemi; Aksi takdirde belirtin **false**.

## <a name="methodreleasenotifier-object"></a>Module::methodreleasenotifier:: object_

Üye işlevi için geçerli olay işleyicisi olan nesneye bir işaretçi tutan `Module::MethodReleaseNotifier` nesne.

```cpp
T* object_;
```
