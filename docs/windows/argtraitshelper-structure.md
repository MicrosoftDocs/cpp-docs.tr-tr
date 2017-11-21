---
title: "ArgTraitsHelper yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs: C++
helpviewer_keywords: ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e8c42db196836a4a618003bfa14cd08d53105a04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename TDelegateInterface  
>  
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
|[ArgTraitsHelper::args sabiti](../windows/argtraitshelper-args-constant.md)|Yardımcı [ArgTraits::args](../windows/argtraits-args-constant.md) parametreleri sayısını temsilci arabirimi Invoke yöntemi üzerinde tutun.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)