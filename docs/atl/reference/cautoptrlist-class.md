---
title: "CAutoPtrList sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0887b0fdaeeaf498bacdc5eec66981656f34fed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cautoptrlist-class"></a>CAutoPtrList sınıfı
Bu sınıf, akıllı işaretçiler listesi oluşturulurken, kullanışlı yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename E>  
class CAutoPtrList : 
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `E`  
 İşaretçi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf bir oluşturucu sağlar ve yöntemleri türetilen [CAtlList](../../atl/reference/catllist-class.md) ve [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) akıllı işaretçiler depolama bir liste nesnesi oluşturulmasını yardımcı olmak için. Sınıf [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) benzer bir işlevi için bir dizi nesnesi sağlar.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList  
 Oluşturucu.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Varsayılan değer 10 blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Blok boyutu, yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlList sınıfı](../../atl/reference/catllist-class.md)   
 [CAutoPtrElementTraits sınıfı](../../atl/reference/cautoptrelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
