---
title: Removeıunknown sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb005bc3cbf411a7d5b5ddbfa44cd6aecf802105
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
  
 Varsayılan olarak, COM yöntemleri sanal sağlamak `QueryInterface`, `AddRef`ve yayın yöntemleri. Ancak, `ComPtr` sanal yöntemler yükü gerektirmez. `RemoveIUnknown` özel, sanal olmayan sağlayarak bu ek yükü ortadan kaldırır `QueryInterface`, `AddRef`, ve `Release` yöntemleri.  
  
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