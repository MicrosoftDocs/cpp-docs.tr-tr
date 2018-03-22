---
title: ArgTraitsHelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4df7e9fe3823e3dbb84b09863e6de5178ab44d18
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename TDelegateInterface>  
struct ArgTraitsHelper;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TDelegateInterface`  
 Bir temsilci arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 Yardımcı genel özelliklerini temsilci bağımsız değişkenleri tanımlayın.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`methodType`|Eşanlamlısı `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Eşanlamlısı `ArgTraits<methodType>`.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArgTraitsHelper::args Sabiti](../windows/argtraitshelper-args-constant.md)|Yardımcı [ArgTraits::args](../windows/argtraits-args-constant.md) parametreleri sayısını temsilci arabirimi Invoke yöntemi üzerinde tutun.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)