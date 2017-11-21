---
title: "ComPtrRefBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs: C++
helpviewer_keywords: ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c010b85095da67a91c0b4c1df6f3da7a4f677dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[ComPtrRefBase::operator Iınspectable ** işleci](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-pointer-Iınspectable arabirimi.|  
|[ComPtrRefBase::operator IUnknown ** işleci](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-pointer-IUnknown arabirimi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_ veri üyesi](../windows/comptrrefbase-ptr-data-member.md)|Geçerli şablon parametresi tarafından belirtilen tür için işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)