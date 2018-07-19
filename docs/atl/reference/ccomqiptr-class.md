---
title: CComQIPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e480fe81f8a6181aa8543710d050f0f20f288681
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884837"
---
# <a name="ccomqiptr-class"></a>CComQIPtr sınıfı
COM arabirim işaretçilerini yönetmek için bir akıllı işaretçi sınıfının.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Depolanacak işaretçi türü belirten bir COM arabirimi.  
  
 *piid*  
 Laboratuvardaki işaretçisi *T*.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Oluşturucu.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|Bir işaretçi, üye işaretçisi atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 ATL kullanan `CComQIPtr` ve [CComPtr](../../atl/reference/ccomptr-class.md) COM arabirim işaretçilerini yönetmek için ikisi için de öğesinden türetilen [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Her iki sınıfları otomatik başvuru yapılan çağrılar aracılığıyla sayımı gerçekleştirmek `AddRef` ve `Release`. Aşırı yüklenmiş işleçler, işaretçi işlemleri işleyin.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  
  
##  <a name="ccomqiptr"></a>  CComQIPtr::CComQIPtr  
 Oluşturucu.  
  
```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *LP*  
 Arabirim işaretçisi başlatmak için kullanılır.  
  
 *T*  
 Bir COM arabirimi.  
  
 *piid*  
 Laboratuvardaki işaretçisi *T*.  
  
##  <a name="operator_eq"></a>  CComQIPtr::operator =  
 Atama işleci.  
  
```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *LP*  
 Arabirim işaretçisi başlatmak için kullanılır.  
  
 *T*  
 Bir COM arabirimi.  
  
 *piid*  
 Laboratuvardaki işaretçisi *T*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir işaretçi döndürür `CComQIPtr` nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [CComPtrBase sınıfı](../../atl/reference/ccomptrbase-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)
