---
title: "CComContainedObject sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
dev_langs: C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3579d4080b4dba130b58592fa47efd636805ed1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcontainedobject-class"></a>CComContainedObject sınıfı
Bu sınıf uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) sahip nesne için temsilci seçme tarafından **IUnknown**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Oluşturucu. Üye işaretçisi sahibi nesnenin başlatır `IUnknown`.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|Sahip nesne üzerinde başvurusu sayısını artırır.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Sahibi nesnenin alır `IUnknown`.|  
|[CComContainedObject::QueryInterface](#queryinterface)|Sahip nesne üzerinde istenen arabirimi için bir işaretçi alır.|  
|[CComContainedObject::Release](#release)|Başvuru sayım sahibi nesnesinde azaltır.|  
  
## <a name="remarks"></a>Açıklamalar  
 ATL kullanan `CComContainedObject` sınıflardaki [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), ve [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) sahip nesne için temsilci seçme tarafından **IUnknown**. (Dış nesne bir toplama veya etiketleri arabirimi oluşturulmaktadır nesne sahibi değil.) `CComContainedObject` çağrıları `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`, ve `OuterRelease`, aracılığıyla devralınan tüm `Base`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="addref"></a>CComContainedObject::AddRef  
 Sahip nesne üzerinde başvurusu sayısını artırır.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
##  <a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject  
 Oluşturucu.  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 [in] Sahibi nesnenin **IUnknown**.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlar `m_pOuterUnknown` üye işaretçisi (aracılığıyla devralınan `Base` sınıfı) için `pv`.  
  
##  <a name="dtor"></a>CComContainedObject:: ~ CComContainedObject  
 Yok Edicisi.  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 Döndürür `m_pOuterUnknown` üye işaretçisi (aracılığıyla devralınan *temel* sınıfı) sahibi nesnenin tutan **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sahibi nesnenin **IUnknown**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sanal varsa `Base` belirtmiş [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) makrosu.  
  
##  <a name="queryinterface"></a>CComContainedObject::QueryInterface  
 Sahip nesne üzerinde istenen arabirimi için bir işaretçi alır.  
  
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
  
##  <a name="release"></a>CComContainedObject::Release  
 Başvuru sayım sahibi nesnesinde azaltır.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde, **sürüm** tanılama için kullanışlı veya test bir değer döndürür. Olmayan hata ayıklama derlemelerinde, **sürüm** her zaman 0 döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
