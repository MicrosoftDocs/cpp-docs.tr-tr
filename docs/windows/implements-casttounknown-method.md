---
title: Implements::casttounknown yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a490e3b8dc620cb3f0f440b2e28cce1f2e69c76d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607254"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown Yöntemi
Temel alınan bir işaretçi alır `IUnknown` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlem, her zaman başarılı olur ve döndürür `IUnknown` işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 İç yardımcı işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implements Yapısı](../windows/implements-structure.md)