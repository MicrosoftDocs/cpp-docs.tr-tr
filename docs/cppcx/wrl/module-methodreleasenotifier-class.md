---
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
ms.openlocfilehash: c641f150b6f029facffa62f7b47c7da32138735e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371295"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier Sınıfı

Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisi çağırır. Olay işleyicisi bir nesne ve onun işaretçi-to-a-method üyesi tarafından belirtilir.

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

Adı                                                                                                 | Açıklama
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Modül::MethodReleaseNotifier::MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | `Module::MethodReleaseNotifier` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                                   | Açıklama
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Modül::MethodReleaseNotifier::Invoke](#methodreleasenotifier-invoke) | Geçerli `Module::MethodReleaseNotifier` nesneyle ilişkili olay işleyicisini çağırır.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                                                                    | Açıklama
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Modül::MethodReleaseNotifier::method_](#methodreleasenotifier-method) | Geçerli `Module::MethodReleaseNotifier` nesne için olay işleyicisi için bir işaretçi tutar.
[Modül::MethodReleaseNotifier::object_](#methodreleasenotifier-object) | Üye işlevi geçerli `Module::MethodReleaseNotifier` nesnenin olay işleyicisi olan nesneye işaretçi tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a>Modül::MethodReleaseNotifier::Invoke

Geçerli `Module::MethodReleaseNotifier` nesneyle ilişkili olay işleyicisini çağırır.

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a>Modül::MethodReleaseNotifier::method_

Geçerli `Module::MethodReleaseNotifier` nesne için olay işleyicisi için bir işaretçi tutar.

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a>Modül::MethodReleaseNotifier::MethodReleaseNotifier

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

*Nesne*<br/>
Üye işlevi olay işleyicisi olan bir nesne.

*Yöntem*<br/>
Olay işleyicisi olan parametre *nesnesinin* üye işlevi.

*Sürüm*<br/>
Temel `true` Modülü aramayı etkinleştirmek için [belirtin::ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) yöntemi; aksi takdirde, belirtin. `false`

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a>Modül::MethodReleaseNotifier::object_

Üye işlevi geçerli `Module::MethodReleaseNotifier` nesnenin olay işleyicisi olan nesneye işaretçi tutar.

```cpp
T* object_;
```
