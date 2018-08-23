---
title: FactoryCache yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df2335a49d2d5daf862db7cea7eb413c01164bee
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609034"
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

|Ad|Açıklama|
|----------|-----------------|
|[FactoryCache::cookie Veri Üyesi](../windows/factorycache-cookie-data-member.md)|Kayıtlı bir Windows çalışma zamanı veya COM sınıfı nesnesini tanımlayan ve daha sonra nesnenin kaydını silmek için kullanılan bir değer içerir.|
|[FactoryCache::factory Veri Üyesi](../windows/factorycache-factory-data-member.md)|Bir Windows çalışma zamanı veya COM sınıf üreteci işaret eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FactoryCache`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)