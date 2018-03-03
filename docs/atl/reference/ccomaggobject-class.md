---
title: "CComAggObject sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd06518978b37705a98e4d8b7212b8dd03a2d7b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomaggobject-class"></a>CComAggObject sınıfı
Bu sınıf uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplanmış bir nesne için arabirim. Tanımı gereği, toplanan nesneyi bir dış nesne içinde yer alır. `CComAggObject` Sınıfı benzer [CComObject sınıfı](../../atl/reference/ccomobject-class.md), dış istemcilere doğrudan erişilebilir bir arabirimi kullanıma sunan dışında.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parametreler  
 `contained`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimleri uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Oluşturucu.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Toplanan nesnesinde başvurusu sayısını artırır.|  
|[CComAggObject::CreateInstance](#createinstance)|Bu statik işlev yeni oluşturmanıza olanak tanıyan **CComAggObject <** `contained`  **>**  nesne yükü olmadan [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Öğesinin son başlatılmasını gerçekleştirir `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Son yok etme gerçekleştirir `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComAggObject::Release](#release)|Başvuru sayım toplanmış nesnesinde azaltır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Temsilciler `IUnknown` dış bilinmeyen çağrıları.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComAggObject`uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplanmış bir nesne için. `CComAggObject`kendi **IUnknown** arabirimi, dış nesnenin ayrı **IUnknown** arabirim ve kendi başvuru sayımı tutar.  
  
 Toplama hakkında daha fazla bilgi için bkz: [ATL COM nesneleri Temelleri](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 [İn uygulamasına](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>CComAggObject::AddRef  
 Toplanan nesnesinde başvurusu sayısını artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
##  <a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 Oluşturucu.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 [in] Dış bilinmiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır `CComContainedObject` üyesi [m_contained](#m_contained)ve modül kilit sayısı artırır.  
  
 Yok Edicisi azaltır modülü kilit sayısı.  
  
##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject  
 Yok Edicisi.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları ayrılan tüm kaynakları serbest bırakır [FinalRelease](#finalrelease), ve azaltır modülü kilit sayısı.  
  
##  <a name="createinstance"></a>CComAggObject::CreateInstance  
 Bu statik işlev yeni oluşturmanıza olanak tanıyan **CComAggObject <** `contained`  **>**  nesne yükü olmadan [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pp`  
 [out] Bir işaretçi bir **CComAggObject\<***bulunan*  **>**  işaretçi. Varsa `CreateInstance` başarısızsa, `pp` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen nesne başvuru sayısı sıfır sahipse, bu nedenle çağrısı `AddRef` hemen sonra kullanın **sürüm** tamamladığınızda nesne işaretçisi üzerinde başvuru boşaltılacak.  
  
 Nesneye doğrudan erişim değildir, ancak hala yükü olmadan yeni bir nesne oluşturmak istediğiniz `CoCreateInstance`, kullanın [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.  
  
##  <a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 Nesne oluşturması son aşamaları sırasında çağrılır, bu yöntem herhangi son başlatma gerçekleştirir [m_contained](#m_contained) üyesi.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="finalrelease"></a>CComAggObject::FinalRelease  
 Nesne yok etme sırasında çağrılır, bu yöntem boşaltır [m_contained](#m_contained) üyesi.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComAggObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) nesnesi, sınıfından türetilmiş.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Parametreler  
 `contained`  
 [in] Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimleri uğradıysa gibi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm **IUnknown** aracılığıyla çağırır `m_contained` dış bilinmeyen temsilcisi.  
  
##  <a name="queryinterface"></a>CComAggObject::QueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İstenen arabirimi tanımlayıcısı.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`. Nesne bu arabirim desteklemiyorsa `ppvObject` ayarlanır **NULL**.  
  
 `pp`  
 [out] Türe göre belirlenen arabirim işaretçisi gösteren bir işaretçi `Q`. Nesne bu arabirim desteklemiyorsa `pp` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İstenen arabirimi ise **IUnknown**, `QueryInterface` toplanmış nesnenin için kendi işaretçi döndüren **IUnknown** ve başvuru sayısını artırır. Aksi takdirde, bu yöntem arabirimi aracılığıyla sorgular `CComContainedObject` üyesi [m_contained](#m_contained).  
  
##  <a name="release"></a>CComAggObject::Release  
 Başvuru sayım toplanmış nesnesinde azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde, **sürüm** tanılama için kullanışlı veya test bir değer döndürür. Olmayan hata ayıklama derlemelerinde, **sürüm** her zaman 0 döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComObject sınıfı](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
