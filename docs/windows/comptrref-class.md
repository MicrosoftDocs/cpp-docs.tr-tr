---
title: "ComPtrRef sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef
dev_langs: C++
helpviewer_keywords: ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 34368322da73e7bd0f9e01152fd24fdac52528a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[ComPtrRef::GetAddressOf yöntemi](../windows/comptrref-getaddressof-method.md)|Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi için bir işaretçi adresi alır.|  
|[ComPtrRef::ReleaseAndGetAddressOf yöntemi](../windows/comptrref-releaseandgetaddressof-method.md)|Geçerli ComPtrRef nesneyi siler ve ComPtrRef nesnesiyle temsil arabirimine bir işaretçi bir-işaretçiye döndürür.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType ** işleci](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Geçerli ComPtrRef nesneyi siler ve ComPtrRef nesnesiyle temsil arabirimine bir işaretçi bir-işaretçiye döndürür.|  
|[ComPtrRef::operator T * işleci](../windows/comptrref-operator-t-star-operator.md)|Değerini döndürür [ptr_](../windows/comptrrefbase-ptr-data-member.md) geçerli ComPtrRef nesnesinin veri üyesi.|  
|[ComPtrRef::operator void ** işleci](../windows/comptrref-operator-void-star-star-operator.md)|Geçerli ComPtrRef nesneyi siler, ComPtrRef nesnesiyle bir işaretçi--pointer-için temsil edilen arabirimi işaretçisine bıraktığı `void`ve atama işaretçi döndürür.|  
|[ComPtrRef::operator * işleci](../windows/comptrref-operator-star-operator.md)|Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi işaretçisine alır.|  
|[ComPtrRef::operator == işleci](../windows/comptrref-operator-equality-operator.md)|İki ComPtrRef nesnenin eşit olup olmadığını gösterir.|  
|[ComPtrRef::operator! = işleci](../windows/comptrref-operator-inequality-operator.md)|İki ComPtrRef nesnenin eşit olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)