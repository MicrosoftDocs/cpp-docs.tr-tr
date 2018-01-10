---
title: "CComPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
dev_langs: C++
helpviewer_keywords: CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ef8c49b04a769fd6202aa58324f20216948cf3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomptr-class"></a>CComPtr sınıfı
COM arabirimi işaretçileri yönetmek için bir akıllı işaretçi sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Depolanacak işaretçi türünü belirleyen bir COM arabirimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|Oluşturucu.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|Bir işaretçi üye işaretçiyi atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 ATL kullanan `CComPtr` ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM arabirim işaretçileri yönetmek için. Her ikisi de türetilmiş [CComPtrBase](../../atl/reference/ccomptrbase-class.md), ve her ikisi de otomatik başvuru sayım gerçekleştirin.  
  
 **CComPtr** ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) sınıfları otomatik başvuru sayım gerçekleştirerek bellek sızıntıları ortadan kaldırmanıza yardımcı olabilir.  Aşağıdaki işlevleri hem mantıksal işlemlerin aynısını gerçekleştirir; Ancak, nasıl ikinci sürümü kullanarak hataya daha az olabileceğine dikkat edin **CComPtr** sınıfı:  
  
 [!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 Hata ayıklama derlemelerinde kod izleme için atlsd.lib bağlayın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="ccomptr"></a>CComPtr::CComPtr  
 Oluşturucu.  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 `lp`  
 Arabirim işaretçisi başlatmak için kullanılır.  
  
 `T`  
 COM arabirimi.  
  
##  <a name="operator_eq"></a>CComPtr::operator =  
 Atama işleci.  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi güncelleştirilmiş döndüren `CComPtr` nesnesi  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlemi AddRefs yeni bir nesne ve sürümler varolan nesne yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
