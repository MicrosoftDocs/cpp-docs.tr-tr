---
title: "CComQIPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs: C++
helpviewer_keywords: CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6240b779977f99d362f7fd37ef5526ce08e89bd0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomqiptr-class"></a>CComQIPtr sınıfı
COM arabirimi işaretçileri yönetmek için bir akıllı işaretçi sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Depolanacak işaretçi türünü belirleyen bir COM arabirimi.  
  
 `piid`  
 Bir işaretçi IID `T`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Oluşturucu.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|Bir işaretçi üye işaretçiyi atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 ATL kullanan `CComQIPtr` ve [CComPtr](../../atl/reference/ccomptr-class.md) COM arabirim işaretçileri yönetmek için her ikisi de öğesinden türetilen [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Her iki sınıfları otomatik başvuru çağrıları aracılığıyla sayım gerçekleştirin `AddRef` ve **sürüm**. Aşırı yüklenmiş işleçler işaretçi işlemleri işleyin.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  
  
##  <a name="ccomqiptr"></a>CComQIPtr::CComQIPtr  
 Oluşturucu.  
  
```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lp`  
 Arabirim işaretçisi başlatmak için kullanılır.  
  
 `T`  
 COM arabirimi.  
  
 `piid`  
 Bir işaretçi IID `T`.  
  
##  <a name="operator_eq"></a>CComQIPtr::operator =  
 Atama işleci.  
  
```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lp`  
 Arabirim işaretçisi başlatmak için kullanılır.  
  
 `T`  
 COM arabirimi.  
  
 `piid`  
 Bir işaretçi IID `T`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi güncelleştirilmiş döndüren `CComQIPtr` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [CComPtrBase sınıfı](../../atl/reference/ccomptrbase-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)
