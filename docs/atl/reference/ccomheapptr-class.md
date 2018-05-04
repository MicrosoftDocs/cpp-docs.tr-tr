---
title: CComHeapPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1937bb96cabfd1a42650e2a27fd04c11aa648f2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomheapptr-class"></a>CComHeapPtr sınıfı
Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öbek üzerinde depolanması için nesne türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComHeapPtr` türetilen `CHeapPtr`, ancak kullanır [CComAllocator](../../atl/reference/ccomallocator-class.md) COM yordamları kullanarak bellek ayıramadı. Bkz: [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) kullanılabilir yöntemleri için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="ccomheapptr"></a>  CComHeapPtr::CComHeapPtr  
 Oluşturucu.  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pData`  
 Varolan bir `CComHeapPtr` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yığın işaretçisi isteğe bağlı olarak var olan kullanılarak oluşturulabilir `CComHeapPtr` nesnesi. Bu durumda, yeni `CComHeapPtr` nesne yeni işaretçi ve kaynakları yönetmek için sorumluluk varsayar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase sınıfı](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator sınıfı](../../atl/reference/ccomallocator-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
