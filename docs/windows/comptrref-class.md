---
title: "ComPtrRef sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b1bbe134f15fdba6863f1725cbcc7effcb6d94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrref-class"></a>ComPtrRef Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 A [ComPtr\<T >](../windows/comptr-class.md) türü veya bir türü türetilen onu kesmenin ComPtr tarafından temsil edilen arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 ComPtr türünde bir nesneye başvuru temsil eden\<T >.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef Oluşturucusu](../windows/comptrref-comptrref-constructor.md)|Belirtilen işaretçi ComPtrRef sınıfından başka bir ComPtrRef nesne için yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf Metodu](../windows/comptrref-getaddressof-method.md)|Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi için bir işaretçi adresi alır.|  
|[ComPtrRef::ReleaseAndGetAddressOf Metodu](../windows/comptrref-releaseandgetaddressof-method.md)|Geçerli ComPtrRef nesneyi siler ve ComPtrRef nesnesiyle temsil arabirimine bir işaretçi bir-işaretçiye döndürür.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType** İşleci](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Geçerli ComPtrRef nesneyi siler ve ComPtrRef nesnesiyle temsil arabirimine bir işaretçi bir-işaretçiye döndürür.|  
|[ComPtrRef::operator T* İşleci](../windows/comptrref-operator-t-star-operator.md)|Değerini döndürür [ptr_](../windows/comptrrefbase-ptr-data-member.md) geçerli ComPtrRef nesnesinin veri üyesi.|  
|[ComPtrRef::operator void** İşleci](../windows/comptrref-operator-void-star-star-operator.md)|Geçerli ComPtrRef nesneyi siler, ComPtrRef nesnesiyle bir işaretçi--pointer-için temsil edilen arabirimi işaretçisine bıraktığı `void`ve atama işaretçi döndürür.|  
|[ComPtrRef::operator* İşleci](../windows/comptrref-operator-star-operator.md)|Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi işaretçisine alır.|  
|[ComPtrRef::operator== İşleci](../windows/comptrref-operator-equality-operator.md)|İki ComPtrRef nesnenin eşit olup olmadığını gösterir.|  
|[ComPtrRef::operator!= İşleci](../windows/comptrref-operator-inequality-operator.md)|İki ComPtrRef nesnenin eşit olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)