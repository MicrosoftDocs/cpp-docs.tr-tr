---
title: CComTearOffObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be47c9525098cb3bd444cefff39dbbf25b88d396
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject sınıfı
Bu sınıf bir etiketleri arabirimini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Etiketleri sınıfınızı türetilen `CComTearOffObjectBase` ve arabirimler desteklemek için etiketleri nesnenizin istiyor.  
  
 ATL uygulayan etiketleri arabirimlerinden iki aşamada — `CComTearOffObjectBase` yöntemlerini işlemek başvuru sayısı ve `QueryInterface`, sırada `CComTearOffObject` uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Oluşturucu.|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|İçin başvuru sayısını artırır bir `CComTearOffObject` nesnesi.|  
|[CComTearOffObject::QueryInterface](#queryinterface)|Bir işaretçi istenen arabirimi etiketleri sınıfınız ya da sahibi sınıf döndürür.|  
|[CComTearOffObject::Release](#release)|Başvuru sayım azaltır bir `CComTearOffObject` nesne ve yok eder.|  
  
### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase yöntemleri  
  
|||  
|-|-|  
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Oluşturucu.|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase veri üyeleri  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|Bir işaretçi bir `CComObject` sahibi sınıfından türetilen.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComTearOffObject` Bu arabirim için sorgulandığında, örneği ayrı bir nesne olarak etiketleri arabirimi uygular. Başvuru sayısı sıfır olduğunda etiketleri silinir. Genellikle, bir etiketleri arabirimi bir etiketleri kullanarak vtable işaretçi ana nesnenizin tüm örneklerinin kaydeder olduğundan, nadiren kullanılır bir arabirim için oluşturun.  
  
 Etiketleri gelen uygulayan sınıfa türetilmelidir `CComTearOffObjectBase` ve hangi arabirimleri desteklemek için etiketleri nesnenizin istiyor. `CComTearOffObjectBase` sahip sınıf ve iş parçacığı modeli şablonlaştırılmış. Kendisi için bir etiketleri uygulanan nesne sınıfı sahibi sınıfıdır. Bir iş parçacığı modeli belirtmezseniz, varsayılan iş parçacığı modeli kullanılır.  
  
 Etiketleri sınıfınız için bir COM eşlemesi oluşturmanız gerekir. ATL etiketleri başlattığında oluşturacak **CComTearOffObject\<CYourTearOffClass >** veya **CComCachedTearOffObject\<CYourTearOffClass >**.  
  
 Örneğin, sesli İKAZ örnekteki `CBeeper2` sınıftır etiketleri ve `CBeeper` sınıftır sahibi:  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>  CComTearOffObject::AddRef  
 Başvuru sayısını artırır `CComTearOffObject` bir nesne.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı ve test olabilir bir değer.  
  
##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject  
 Oluşturucu.  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 [in] Bir işaretçi dönüştürülecek işaretçi bir **CComObject\<sahibi >** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sahibin başvurusu sayısını bire artırır.  
  
##  <a name="dtor"></a>  CComTearOffObject:: ~ CComTearOffObject  
 Yok Edicisi.  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır, FinalRelease ve azaltır modülü çağırır kilit sayısı.  
  
##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase  
 Oluşturucu.  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır [m_pOwner](#m_powner) üyesine **NULL**.  
  
##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner  
 Bir işaretçi bir [CComObject](../../atl/reference/ccomobject-class.md) nesne türetilen *sahibi*.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>Parametreler  
 *Sahibi*  
 [in] Kendisi için bir etiketleri uygulanan sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçinin başlatılıp başlatılmadığı **NULL** oluşturma sırasında.  
  
##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi IID.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`, veya **NULL** arabirimi bulunmazsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Etiketleri sınıfınızın arabirimleri için ilk sorgular. Arabirim, sahip nesne arabirimde sorgularında yoksa. İstenen arabirimi ise **IUnknown**, döndürür **IUnknown** sahibinin.  
  
##  <a name="release"></a>  CComTearOffObject::Release  
 Başvuru sayım birer birer azaltır ve başvuru sayısı sıfırsa siler `CComTearOffObject`.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olmayan hata ayıklama derlemelerinde, her zaman sıfır verir. Hata ayıklama derlemelerinde tanılama için kullanışlı veya test bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComCachedTearOffObject sınıfı](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
