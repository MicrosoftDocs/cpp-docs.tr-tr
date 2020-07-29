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
ms.openlocfilehash: 7437f4e1f6874d4c708780a146e1761ac6d98305
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225741"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier Sınıfı

Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi, bir lambda, functor veya işlev işaretçisi üzerinde tarafından belirtilir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Olay işleyicisinin konumunu içeren veri üyesinin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                                                     | Açıklama
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: GenericReleaseNotifier](#genericreleasenotifier-genericreleasenotifier) | `Module::GenericReleaseNotifier` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                                     | Açıklama
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: Invoke](#genericreleasenotifier-invoke) | Geçerli nesneyle ilişkili olay işleyicisini çağırır `Module::GenericReleaseNotifier` .

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                                                                          | Açıklama
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: callback_](#genericreleasenotifier-callback) | Geçerli nesneyle ilişkili lambda, functor veya işlev işaretçisi olay işleyicisini barındırır `Module::GenericReleaseNotifier` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a>Module:: GenericReleaseNotifier:: callback_

Geçerli nesneyle ilişkili lambda, functor veya işlev işaretçisi olay işleyicisini barındırır `Module::GenericReleaseNotifier` .

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a>Module:: GenericReleaseNotifier:: GenericReleaseNotifier

`Module::GenericReleaseNotifier` sınıfının yeni bir örneğini başlatır.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Parametreler

*callback*<br/>
Parantez işlev işleci () ile çağrılabilen lambda, functor veya işaretçiden işleve olay işleyicisi `()` .

*Yayın*<br/>
**`true`** Temeldeki modülün çağrılmasını etkinleştirmek için belirtin [:: ReleaseNotifier:: Release ()](module-releasenotifier-class.md#releasenotifier-release) yöntemi; aksi takdirde, belirtin **`false`** .

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a>Module:: GenericReleaseNotifier:: Invoke

Geçerli nesneyle ilişkili olay işleyicisini çağırır `Module::GenericReleaseNotifier` .

```cpp
void Invoke();
```
