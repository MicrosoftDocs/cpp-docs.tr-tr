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
ms.openlocfilehash: efaf7b51da1e4a4e744133884b92ac78db3b3f66
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017776"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown Yöntemi
Temel alınan bir işaretçi alır `IUnknown` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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