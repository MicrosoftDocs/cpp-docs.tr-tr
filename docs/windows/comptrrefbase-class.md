---
title: "ComPtrRefBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 071598c83086afe12e1d19ef541dbfb3d0dbc55a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 A [ComPtr\<T >](../windows/comptr-class.md) türü veya bir türü türetilen onu kesmenin ComPtr tarafından temsil edilen arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin temel sınıfı temsil eder [ComPtrRef](../windows/comptrref-class.md) sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`InterfaceType`|Şablon parametresinin türü için eş anlamlı `T`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable** İşleci](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-pointer-Iınspectable arabirimi.|  
|[ComPtrRefBase::operator IUnknown** İşleci](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-pointer-IUnknown arabirimi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_ Veri Üyesi](../windows/comptrrefbase-ptr-data-member.md)|Geçerli şablon parametresi tarafından belirtilen tür için işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)