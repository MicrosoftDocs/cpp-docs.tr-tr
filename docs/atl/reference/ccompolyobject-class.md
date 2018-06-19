---
title: CComPolyObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383a83a2e2b09c9652e7185592a5891179416e0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364108"
---
# <a name="ccompolyobject-class"></a>CComPolyObject sınıfı
Bu sınıf uygulayan **IUnknown** bir toplanmış veya toplanmayan nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class contained>  
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parametreler  
 `contained`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimleri uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Oluşturucu.|  
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPolyObject::AddRef](#addref)|Nesne başvurusu sayısını artırır.|  
|[CComPolyObject::CreateInstance](#createinstance)|(Statik) Yeni bir oluşturmanıza olanak tanıyan **CComPolyObject <** `contained` **>** nesne yükü olmadan [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](#finalconstruct)|Öğesinin son başlatılmasını gerçekleştirir `m_contained`.|  
|[CComPolyObject::FinalRelease](#finalrelease)|Son yok etme gerçekleştirir `m_contained`.|  
|[CComPolyObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComPolyObject::Release](#release)|Azaltır nesnenin başvuru sayısı.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPolyObject::m_contained](#m_contained)|Temsilciler **IUnknown** nesne toplanır mı yoksa için dış bilinmeyen çağırır **IUnknown** nesne değil toplanır, nesnenin.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComPolyObject` uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) bir toplanmış veya toplanmayan nesnesi.  
  
 Bir örneği olduğunda `CComPolyObject` oluşturulur, dış değeri bilinmeyen denetlenir. Eğer öyleyse **NULL**, **IUnknown** toplanmayan bir nesne için uygulanır. Dış bilinmeyen değilse **NULL**, **IUnknown** toplanmış olan bir nesne için uygulanır.  
  
 Kullanmanın avantajı `CComPolyObject` her ikisi de zorunda kalmamak olan [CComAggObject](../../atl/reference/ccomaggobject-class.md) ve [CComObject](../../atl/reference/ccomobject-class.md) toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesini işleme her iki durumda. Bu, yalnızca bir kopyasını vtable ve işlevlerin bir kopya, modülünde mevcut anlamına gelir. Vtable büyükse, bu modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesne için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.  
  
 Varsa `DECLARE_POLY_AGGREGATABLE` makrosu, nesnenin sınıf tanımında belirtilen `CComPolyObject` , nesneyi oluşturmak için kullanılan. `DECLARE_POLY_AGGREGATABLE` otomatik olarak bir tam denetim veya Internet Explorer denetimi oluşturmak için ATL Proje Sihirbazı'nı kullanırsanız bildirilir.  
  
 Toplanan, `CComPolyObject` nesne sahip kendi **IUnknown**, dış nesnenin ayrı **IUnknown**ve kendi başvuru sayımı tutar. `CComPolyObject` kullanan [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) dış bilinmeyen yetki vermek için.  
  
 Toplama hakkında daha fazla bilgi için bkz: [ATL COM nesneleri Temelleri](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>  CComPolyObject::AddRef  
 Nesne üzerinde başvurusu sayısını artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject  
 Oluşturucu.  
  
```
CComPolyObject(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 [in] Nesne toplanacak, ise dış bilinmeyen bir işaretçi veya **NULL** , nesne nesne değil toplanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır `CComContainedObject` veri üyesi [m_contained](#m_contained)ve modül kilit sayısı artırır.  
  
 Yok Edicisi azaltır modülü kilit sayısı.  
  
##  <a name="dtor"></a>  CComPolyObject:: ~ CComPolyObject  
 Yok Edicisi.  
  
```
~CComPolyObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları ayrılan tüm kaynakları serbest bırakır [FinalRelease](#finalrelease), ve azaltır modülü kilit sayısı.  
  
##  <a name="createinstance"></a>  CComPolyObject::CreateInstance  
 Yeni bir oluşturmanıza olanak tanıyan **CComPolyObject <** `contained` **>** nesne yükü olmadan [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pp`  
 [out] Bir işaretçi bir **CComPolyObject <** `contained` **>** işaretçi. Varsa `CreateInstance` başarısızsa, `pp` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen nesne başvuru sayısı sıfır sahipse, bu nedenle çağrısı `AddRef` hemen sonra kullanın **sürüm** tamamladığınızda nesne işaretçisi üzerinde başvuru boşaltılacak.  
  
 Nesneye erişim doğrudan yoktur, ancak hala yükü olmadan yeni bir nesne oluşturmak istediğiniz `CoCreateInstance`, kullanın [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.  
  
##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct  
 Nesne oluşturması son aşamaları sırasında çağrılır, bu yöntem herhangi son başlatma gerçekleştirir [m_contained](#m_contained) veri üyesi.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease  
 Nesne yok etme sırasında çağrılır, bu yöntem boşaltır [m_contained](#m_contained) veri üyesi.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComPolyObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) nesnesi, sınıfından türetilmiş.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Parametreler  
 `contained`  
 [in] Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimleri uğradıysa gibi.  
  
### <a name="remarks"></a>Açıklamalar  
 **IUnknown** aracılığıyla çağırır `m_contained` dış bilinmeyen nesne toplanır mi yoksa için temsilci **IUnknown** nesne değil toplanır varsa, bu nesnenin.  
  
##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `Q`  
 COM arabirimi.  
  
 `iid`  
 [in] İstenen arabirimi tanımlayıcısı.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`. Nesne bu arabirim desteklemiyorsa `ppvObject` ayarlanır **NULL**.  
  
 `pp`  
 [out] Tarafından tanımlanan arayüzü için bir işaretçi **__uuidof(Q)**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İstenen arabirimi ise, birleşik bir nesne için **IUnknown**, `QueryInterface` toplanmış nesnenin için kendi işaretçi döndüren **IUnknown** ve başvuru sayısını artırır. Aksi takdirde, bu yöntem arabirimi aracılığıyla sorgular `CComContainedObject` veri üyesi [m_contained](#m_contained).  
  
##  <a name="release"></a>  CComPolyObject::Release  
 Başvuru sayım nesnede azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde, **sürüm** tanılama için kullanışlı veya test bir değer döndürür. Nondebug derlemelerde **sürüm** her zaman 0 döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
