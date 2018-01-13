---
title: "CComObject sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs: C++
helpviewer_keywords: CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27da00e09ca88cc06b8bafed8f8601dac756fd34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobject-class"></a>CComObject sınıfı
Bu sınıf uygulayan **IUnknown** toplanmayan bir nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md)nesnede desteklemek istediğiniz iyi herhangi diğer arabirimleri uğradıysa gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Oluşturucu.|  
|[CComObject:: ~ CComObject](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Nesne üzerinde başvurusu sayısını artırır.|  
|[CComObject::CreateInstance](#createinstance)|(Statik) Yeni bir `CComObject` nesnesi.|  
|[CComObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComObject::Release](#release)|Başvuru sayım nesnede azaltır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObject`uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplanmayan bir nesne. Ancak, çağrılar `QueryInterface`, `AddRef`, ve **sürüm** için temsilci `CComObjectRootEx`.  
  
 Kullanma hakkında daha fazla bilgi için `CComObject`, makaleye bakın [ATL COM nesneleri Temelleri](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>CComObject::AddRef  
 Nesne üzerinde başvurusu sayısını artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işlev bir nesne üzerinde yeni artırılır başvuru sayımını döndürür. Bu değer, tanılama veya sınama için yararlı olabilir.  
  
##  <a name="ccomobject"></a>CComObject::CComObject  
 Oluşturucu modülü kilit sayısını artırır.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 **void\***  
 [in] Bu adlandırılmamış parametre kullanılmaz. Diğer simetrisi için mevcut **CCom***XXX*`Object`*XXX* oluşturucular.  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi azaltır.  
  
 Varsa bir `CComObject`-türetilen nesne, kullanarak başarılı bir şekilde yapılandırılmıştır **yeni** işleci, ilk başvuru sayısı: 0. Başvuru sayısı (1) doğru değerine ayarlamak için çağırmaya [AddRef](#addref) işlevi.  
  
##  <a name="dtor"></a>CComObject:: ~ CComObject  
 Yok Edicisi.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları ayrılan tüm kaynakları serbest bırakır [FinalRelease](ccomobjectrootex-class.md#finalrelease), ve azaltır modülü kilit sayısı.  

  
##  <a name="createinstance"></a>CComObject::CreateInstance  
 Bu statik işlev yeni oluşturmanıza olanak tanıyan **CComObject <** `Base`  **>**  yükü olmadan nesne [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pp`  
 [out] Bir işaretçi bir **CComObject <** `Base`  **>**  işaretçi. Varsa `CreateInstance` başarısızsa, `pp` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen nesne başvuru sayısı sıfır sahipse, bu nedenle çağrısı `AddRef` hemen sonra kullanın **sürüm** tamamladığınızda nesne işaretçisi üzerinde başvuru boşaltılacak.  
  
 Nesneye doğrudan erişim değildir, ancak hala yükü olmadan yeni bir nesne oluşturmak istediğiniz `CoCreateInstance`, kullanın [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="release"></a>CComObject::Release  
 Başvuru sayım nesnede azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işlev bir nesne üzerinde yeni indirildiği başvuru sayımını döndürür. Hata ayıklama derlemelerinde, tanılama için kullanışlı veya test dönüş değeri olabilir. Olmayan hata ayıklama derlemelerinde, **sürüm** her zaman 0 döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
