---
title: ArgTraitsHelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6205d69962d70d9da76c932fdd8b3f66f491ebc9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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