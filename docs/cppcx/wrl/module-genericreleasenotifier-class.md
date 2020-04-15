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
ms.openlocfilehash: e3cc8e33d596fb1d3ecc4a94fee7971a50ffe596
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371304"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier Sınıfı

Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisi çağırır. Olay işleyicisi bir lambda, functor veya işaretçi-to-fonksiyon tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Olay işleyicisinin konumunu içeren veri üyesinin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                                                                     | Açıklama
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Modül::GenericReleaseNotifier::GenericReleaseNotifier](#genericreleasenotifier-genericreleasenotifier) | `Module::GenericReleaseNotifier` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                                     | Açıklama
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Modül::GenericReleaseNotifier::Invoke](#genericreleasenotifier-invoke) | Geçerli `Module::GenericReleaseNotifier` nesneyle ilişkili olay işleyicisini çağırır.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                                                                          | Açıklama
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Modül::GenericReleaseNotifier::callback_](#genericreleasenotifier-callback) | Geçerli nesneyle ilişkili lambda, functor veya işaretçi-işlev `Module::GenericReleaseNotifier` olay işleyicisi tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a>Modül::GenericReleaseNotifier::callback_

Geçerli nesneyle ilişkili lambda, functor veya işaretçi-işlev `Module::GenericReleaseNotifier` olay işleyicisi tutar.

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a>Modül::GenericReleaseNotifier::GenericReleaseNotifier

`Module::GenericReleaseNotifier` sınıfının yeni bir örneğini başlatır.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Parametreler

*Geri*<br/>
Parantez işlevi işleci ile çağrılabilen bir lambda, functor veya işaretçi-to-fonksiyon olay işleyicisi (`()`).

*Sürüm*<br/>
Temel `true` Modülü aramayı etkinleştirmek için [belirtin::ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) yöntemi; aksi takdirde, belirtin. `false`

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a>Modül::GenericReleaseNotifier::Invoke

Geçerli `Module::GenericReleaseNotifier` nesneyle ilişkili olay işleyicisini çağırır.

```cpp
void Invoke();
```
