---
title: ComPtrRefBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18f7f08362c14ab0d09019a5b9348750c96ddbd7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643416"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 A [ComPtr\<T >](../windows/comptr-class.md) türü veya tür, kesmenin tarafından temsil edilen arabirim sınıfından türetilen **ComPtr**.  
  
## <a name="remarks"></a>Açıklamalar  
 Temel sınıfı temsil eder [ComPtrRef](../windows/comptrref-class.md) sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`InterfaceType`|Şablon parametresinin türü için bir eşanlamlı *T*.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable** İşleci](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-işaretçi- `IInspectable` arabirimi.|  
|[ComPtrRefBase::operator IUnknown** İşleci](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-işaretçi- `IUnknown` arabirimi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_ Veri Üyesi](../windows/comptrrefbase-ptr-data-member.md)|Geçerli bir şablon parametresi tarafından belirtilen tür işaretçisi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)