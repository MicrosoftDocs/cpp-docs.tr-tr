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
ms.openlocfilehash: 7196363567dffa43844bbbd1de76934a317302d1
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787756"
---
# <a name="factorycache-structure"></a>FactoryCache Yapısı

Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Açıklamalar

Bir sınıf üreteci ve wrt kayıtlı tanımlayan değer veya COM sınıfı nesne konumunu içerir.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                              | Açıklama
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache::cookie](#cookie)   | Kayıtlı bir Windows çalışma zamanı veya COM sınıfı nesnesini tanımlayan ve daha sonra nesnenin kaydını silmek için kullanılan bir değer içerir.
[FactoryCache::factory](#factory) | Bir Windows çalışma zamanı veya COM sınıf üreteci işaret eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FactoryCache`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="cookie"></a>FactoryCache::cookie

Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Açıklamalar

Kayıtlı bir Windows çalışma zamanı veya COM sınıfı nesnesini tanımlayan ve daha sonra nesnenin kaydını silmek için kullanılan bir değer içerir.

## <a name="factory"></a>FactoryCache::factory

Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Açıklamalar

Bir Windows çalışma zamanı veya COM sınıf üreteci işaret eder.