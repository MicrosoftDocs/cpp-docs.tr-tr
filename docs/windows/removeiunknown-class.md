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
ms.openlocfilehash: dd52dcdc5fed543d65311aaa7e8a61a9d2019b8a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020297"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Bir sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde sanal olmayan `QueryInterface`, `AddRef`, ve `Release` üye işlevleri.  
  
 Varsayılan olarak, COM yöntemleri sanal sağlamak `QueryInterface`, `AddRef`, ve `Release` yöntemleri. Ancak, `ComPtr` sanal yöntemler getirdiği ek yüke gerek kalmaz. `RemoveIUnknown` özel, sanal olmayan sağlayarak bu ek yükü ortadan kalkar `QueryInterface`, `AddRef`, ve `Release` yöntemleri.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ReturnType`|Şablon parametresine eşdeğerdir bir türe ilişkin bir eşanlam *T* ancak sanal olmayan `IUnknown` üyeleri.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)