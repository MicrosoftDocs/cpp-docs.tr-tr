---
title: "Removeıunknown sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b62362004f0528b16ef3dac7cbe601b8b85ce3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="removeiunknown-class"></a>RemoveIUnknown Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde olmayan `QueryInterface`, `AddRef`, ve `Release` üye işlevleri.  
  
 Varsayılan olarak, COM yöntemleri sanal sağlamak `QueryInterface`, `AddRef`ve yayın yöntemleri. Ancak, `ComPtr` sanal yöntemler yükü gerektirmez. `RemoveIUnknown`özel, sanal olmayan sağlayarak bu ek yükü ortadan kaldırır `QueryInterface`, `AddRef`, ve `Release` yöntemleri.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ReturnType`|Şablon parametresi için eşdeğer bir gruba bir tür için eş anlamlı `T` ancak sanal olmayan IUnknown üyeler içeriyor.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)