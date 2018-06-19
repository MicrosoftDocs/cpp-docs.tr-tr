---
title: CComCachedTearOffObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1072faed01033bec9fec127318334f8a61ac29e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362888"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject sınıfı
Bu sınıf uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) etiketleri arabirimi için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parametreler  
 `contained`  
 Etiketleri sınıfınızı türetilen `CComTearOffObjectBase` ve arabirimler desteklemek için etiketleri nesnenizin istiyor.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Oluşturucu.|  
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|İçin başvuru sayısını artırır bir `CComCachedTearOffObject` nesnesi.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Çağrıları `m_contained::FinalConstruct` (etiketleri olan sınıfı yöntemi).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Çağrıları `m_contained::FinalRelease` (etiketleri olan sınıfı yöntemi).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Bir işaretçi döndürür `IUnknown` , `CComCachedTearOffObject` nesnesi veya etiketleri sınıfınız istenen Arabirimi'ne (sınıfı `contained`).|  
|[CComCachedTearOffObject::Release](#release)|Başvuru sayım azaltır bir `CComCachedTearOffObject` nesne ve başvuru sayısı 0 ise yok eder.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|A `CComContainedObject` , etiketleri sınıfından türetilen nesnesini (sınıfı `contained`).|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComCachedTearOffObject` uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) etiketleri arabirimi için. Bu sınıf farklıdır `CComTearOffObject` bakımından `CComCachedTearOffObject` kendi **IUnknown**, sahibi nesnenin ayrı **IUnknown** (sahibi için etiketleri oluşturulmakta nesnesidir). `CComCachedTearOffObject` kendi tutar başvuru sayısı, **IUnknown** ve başvuru sayısı sıfır olduğunda kendisini siler. Ancak, herhangi birini kapatmayı dışı Query arabirimleri, sahibi nesnenin başvuru sayısı **IUnknown** arttırılır.  
  
 Varsa `CComCachedTearOffObject` etiketleri uygulama zaten örneği ve etiketleri arabirimi yeniden için aynı sorgulanan nesne `CComCachedTearOffObject` nesne yeniden kullanılabilir. Buna karşılık, etiketleri arabirimi tarafından uygulanırsa bir `CComTearOffObject` yeniden için sahip nesne sorgulanan başka bir `CComTearOffObject` örneğinin oluşturulması.  
  
 Sahip sınıf uygulamalıdır `FinalRelease` ve çağrı **sürüm** önbelleğe alınan üzerinde **IUnknown** için `CComCachedTearOffObject`, hangi, başvuru sayımı azaltma. Bu neden olacak `CComCachedTearOffObject`'s `FinalRelease` çağrılması ve etiketleri silin.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>  CComCachedTearOffObject::AddRef  
 Başvuru sayısını artırır `CComCachedTearOffObject` 1 nesne.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı ve test olabilir bir değer.  
  
##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject  
 Oluşturucu.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 [in] İşaretçi **IUnknown** , `CComCachedTearOffObject`.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır `CComContainedObject` üyesi [m_contained](#m_contained).  
  
##  <a name="dtor"></a>  CComCachedTearOffObject:: ~ CComCachedTearOffObject  
 Yok Edicisi.  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları ve çağrıları boşaltır [FinalRelease](#finalrelease).  
  
##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct  
 Çağrıları **m_contained::FinalConstruct** oluşturmak için `m_contained`, `CComContainedObject` <  `contained`> etiketleri sınıfınız tarafından uygulanan arabirimi erişmek için kullanılan nesne.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease  
 Çağrıları **m_contained::FinalRelease** boşaltmak için `m_contained`, `CComContainedObject` <  `contained`> nesne.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) , etiketleri sınıfından türetilen nesne.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>Parametreler  
 `contained`  
 [in] Etiketleri sınıfınızı türetilen `CComTearOffObjectBase` ve arabirimler desteklemek için etiketleri nesnenizin istiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemleri `m_contained` devralır etiketleri sınıfınız etiketleri arabiriminde önbelleğe alınmış etiketleri nesnenin erişmek için kullanılan `QueryInterface`, `FinalConstruct`, ve `FinalRelease`.  
  
##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi GUID.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`, veya **NULL** arabirimi bulunmazsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İstenen arabirimi ise **IUnknown**, bir işaretçi döndürür `CComCachedTearOffObject`'s kendi **IUnknown** ve başvuru sayısını artırır. Aksi takdirde, etiketleri sınıfı kullanma arabirimi için sorgular [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yöntemi devralınan `CComObjectRootEx`.  

  
##  <a name="release"></a>  CComCachedTearOffObject::Release  
 Başvuru sayısı 1 ile azaltır ve başvuru sayısı 0 ise, siler `CComCachedTearOffObject` nesnesi.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olmayan hata ayıklama derlemelerinde, her zaman 0 döndürür. Hata ayıklama derlemelerinde tanılama için kullanışlı veya test bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComTearOffObject sınıfı](../../atl/reference/ccomtearoffobject-class.md)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
