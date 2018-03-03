---
title: "CAutoPtrArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4afb07323cdb6b25914aabd802c4df73ee1d07c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray sınıfı
Bu sınıf, akıllı işaretçiler bir dizi oluşturulurken kullanışlı yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `E`  
 İşaretçi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf bir oluşturucu sağlar ve yöntemleri türetilen [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) akıllı işaretçiler depolayan bir koleksiyon sınıfı nesnesinin oluşturulmasını yardımcı olmak için.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
 Oluşturucu.  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Akıllı işaretçi dizi başlatır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlArray sınıfı](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits sınıfı](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList sınıfı](../../atl/reference/cautoptrlist-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
