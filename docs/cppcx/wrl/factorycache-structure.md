---
title: FactoryCache Yapısı
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 507d35179b9fa86399e56b18171800f41eaf1f10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371498"
---
# <a name="factorycache-structure"></a>FactoryCache Yapısı

Windows Runtime C++ Şablon Kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Açıklamalar

Bir sınıf fabrikasının konumunu ve kayıtlı bir wrt veya COM sınıf nesnesini tanımlayan bir değeri içerir.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Adı                              | Açıklama
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache::çerez](#cookie)   | Kayıtlı bir Windows Runtime veya COM sınıf nesnesini tanımlayan ve daha sonra nesneyi çıkarmak için kullanılan bir değer içerir.
[FactoryCache::fabrika](#factory) | Windows Runtime veya COM sınıfı fabrikayı işaret edin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FactoryCache`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="factorycachecookie"></a><a name="cookie"></a>FactoryCache::çerez

Windows Runtime C++ Şablon Kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Açıklamalar

Kayıtlı bir Windows Runtime veya COM sınıf nesnesini tanımlayan ve daha sonra nesneyi çıkarmak için kullanılan bir değer içerir.

## <a name="factorycachefactory"></a><a name="factory"></a>FactoryCache::fabrika

Windows Runtime C++ Şablon Kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Açıklamalar

Windows Runtime veya COM sınıfı fabrikayı işaret edin.
