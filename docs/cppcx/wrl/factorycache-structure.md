---
description: 'Daha fazla bilgi edinin: FactoryCache yapısı'
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
ms.openlocfilehash: 3e9ee084a063eb8094c309dee412a8793801921b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198563"
---
# <a name="factorycache-structure"></a>FactoryCache Yapısı

Windows Çalışma Zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Açıklamalar

Bir sınıf fabrikası konumunu ve kayıtlı bir WRT ya da COM sınıfı nesnesini tanımlayan bir değeri içerir.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                              | Açıklama
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache:: Cookie](#cookie)   | Kayıtlı bir Windows Çalışma Zamanı veya COM sınıfı nesnesini tanımlayan bir değer içerir ve daha sonra nesnenin kaydını silmek için kullanılır.
[FactoryCache:: Factory](#factory) | Windows Çalışma Zamanı veya COM sınıfı fabrikasına işaret eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FactoryCache`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="factorycachecookie"></a><a name="cookie"></a> FactoryCache:: Cookie

Windows Çalışma Zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Açıklamalar

Kayıtlı bir Windows Çalışma Zamanı veya COM sınıfı nesnesini tanımlayan bir değer içerir ve daha sonra nesnenin kaydını silmek için kullanılır.

## <a name="factorycachefactory"></a><a name="factory"></a> FactoryCache:: Factory

Windows Çalışma Zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Açıklamalar

Windows Çalışma Zamanı veya COM sınıfı fabrikasına işaret eder.
