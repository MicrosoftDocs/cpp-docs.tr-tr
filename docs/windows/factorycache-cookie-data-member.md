---
title: FactoryCache::cookie veri üyesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache::cookie
dev_langs:
- C++
helpviewer_keywords:
- cookie data member
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6dba6e5d7fd478d198e48e9d8517d34e13b43484
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613672"
---
# <a name="factorycachecookie-data-member"></a>FactoryCache::cookie Veri Üyesi

Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

## <a name="remarks"></a>Açıklamalar

Kayıtlı bir Windows çalışma zamanı veya COM sınıfı nesnesini tanımlayan ve daha sonra nesnenin kaydını silmek için kullanılan bir değer içerir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[FactoryCache Yapısı](../windows/factorycache-structure.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)