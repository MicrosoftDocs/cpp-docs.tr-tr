---
title: CComObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89a909b715633488cff37fa87ea5950681e208cd
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881847"
---
# <a name="ccomobject-class"></a>CComObject sınıfı
Bu sınıfın uyguladığı `IUnknown` toplanmayan bir nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 *temel*  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer arabirimleri uğradıysa nesnede desteklemek istediğiniz gibi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Oluşturucu.|  
|[CComObject::~CComObject](#dtor)|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Nesnede başvuru sayısını artırır.|  
|[CComObject::CreateInstance](#createinstance)|(Statik) Yeni bir oluşturur `CComObject` nesne.|  
|[CComObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComObject::Release](#release)|Nesnede başvuru sayısını azaltır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObject` uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplanmayan bir nesne. Ancak, çağrılar `QueryInterface`, `AddRef`, ve `Release` için temsilci `CComObjectRootEx`.  
  
 Kullanma hakkında daha fazla bilgi için `CComObject`, makaleye göz atın [ATL COM nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>  CComObject::AddRef  
 Nesnede başvuru sayısını artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işlev, nesne üzerinde yeni artan başvuru sayısını döndürür. Bu değer, tanılama veya sınama için yararlı olabilir.  
  
##  <a name="ccomobject"></a>  CComObject::CComObject  
 Oluşturucu, modülün kilit sayacını artırır.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 **Geçersiz kılma\***  
 [in] Bu adlandırılmamış parametre kullanılmaz. Simetri diğer için mevcut **CCom *** XXX*`Object`*XXX* oluşturucular.  
  
### <a name="remarks"></a>Açıklamalar  
 Yıkıcı azaltır.  
  
 Varsa bir `CComObject`-türetilmiş nesnesi, kullanarak başarıyla oluşturulduğunda **yeni** işleci, ilk başvuru sayısı: 0. Başvuru sayısı (1) doğru değerine ayarlamak için çağrı yapmak [AddRef](#addref) işlevi.  
  
##  <a name="dtor"></a>  CComObject::~CComObject  
 Yıkıcı.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları ayrılan tüm kaynakları serbest bırakan [FinalRelease](ccomobjectrootex-class.md#finalrelease), ve modül kilit sayısını azaltır.  

  
##  <a name="createinstance"></a>  CComObject::CreateInstance  
 Bu statik işlev yeni bir oluşturmanıza olanak tanır **CComObject <** `Base` **>** yükü olmadan nesne [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 *PP*  
 [out] Bir işaretçi bir **CComObject <** `Base` **>** işaretçi. Varsa `CreateInstance` başarısız, *pp* NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen nesne başvuru sayısı sıfır sahiptir, bu nedenle çağrı `AddRef` hemen sonra kullanın `Release` işiniz bittiğinde, nesne işaretçinin başvurusu boşaltılacak.  
  
 Nesneye doğrudan erişim değildir, ancak yükü olmadan yeni bir nesne oluşturmak hala istiyorsanız `CoCreateInstance`, kullanın [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>  CComObject::QueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 *IID*  
 [in] İstenen arabirim tanımlayıcısı.  
  
 *ppvObject*  
 [out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*. Nesne bu arabirimi desteklemiyorsa *ppvObject* NULL olarak ayarlandı.  
  
 *PP*  
 [out] Türe göre belirlenen arabirim işaretçisi için bir işaretçi `Q`. Nesne bu arabirimi desteklemiyorsa *pp* NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
##  <a name="release"></a>  CComObject::Release  
 Nesnede başvuru sayısını azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işlev, nesne üzerinde yeni indirildiği başvuru sayısını döndürür. Hata ayıklama yapılarında, dönüş değeri, tanılama için kullanışlı veya test olabilir. Hata ayıklama olmayan yapılarında `Release` her zaman 0 değerini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
