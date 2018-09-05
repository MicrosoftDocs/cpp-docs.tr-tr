---
title: CComAutoDeleteCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53078d740d1051a928b4592d275f33944685e622
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767110"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection sınıfı

Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>Açıklamalar

`CComAutoDeleteCriticalSection` sınıfından türetilen [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Ancak, `CComAutoDeleteCriticalSection` geçersiz kılmalar [terimi](ccomsafedeletecriticalsection-class.md#term) yönteme **özel** erişim, yalnızca bu sınıfın örneklerinin kapsam dışına çıkmadan veya açıkça silinir gerçekleşmesi için iç bellek temizleme zorlar bellek.  

Bu sınıf, taban sınıfı hiçbir ek yöntemleri tanıtır. Bkz: [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) ve [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

## <a name="see-also"></a>Ayrıca Bkz.

[CComSafeDeleteCriticalSection sınıfı](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
[CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
