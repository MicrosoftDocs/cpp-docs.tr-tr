---
title: Module::GenericReleaseNotifier Sınıfı
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
ms.openlocfilehash: 318415c9726426cbd60c205759a6ff8572cc555e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787639"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier Sınıfı

Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyici lambda, functor veya işaretçi işlevi tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Olay işleyicisi konumunu içeren veri üye türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                                                     | Açıklama
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Module::genericreleasenotifier:: genericreleasenotifier](#genericreleasenotifier-genericreleasenotifier) | Yeni bir örneğini başlatır `Module::GenericReleaseNotifier` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                                     | Açıklama
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier:: Invoke](#genericreleasenotifier-invoke) | Geçerli ile ilişkili olay işleyicisini çağırır `Module::GenericReleaseNotifier` nesne.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                                                          | Açıklama
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Module::genericreleasenotifier:: callback_](#genericreleasenotifier-callback) | Lambda, functor ya da işaretçi işlevi olay işleyicisi geçerli ilişkili `Module::GenericReleaseNotifier` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="genericreleasenotifier-callback"></a>Module::genericreleasenotifier:: callback_

Lambda, functor ya da işaretçi işlevi olay işleyicisi geçerli ilişkili `Module::GenericReleaseNotifier` nesne.

```cpp
T callback_;
```

## <a name="genericreleasenotifier-genericreleasenotifier"></a>Module::genericreleasenotifier:: genericreleasenotifier

Yeni bir örneğini başlatır `Module::GenericReleaseNotifier` sınıfı.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Parametreler

*geri çağırma*<br/>
Bir lambda, functor veya parantez işlevi işleci ile çağrılabilir işaretçi işlevi olay işleyicisi (`()`).

*Yayın*<br/>
Belirtin `true` temel çağırma etkinleştirmek için [Modülü:: ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) yöntemi; Aksi takdirde belirtin `false`.

## <a name="genericreleasenotifier-invoke"></a>Module::GenericReleaseNotifier:: Invoke

Geçerli ile ilişkili olay işleyicisini çağırır `Module::GenericReleaseNotifier` nesne.

```cpp
void Invoke();
```
