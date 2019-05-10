---
title: CComClassFactorySingleton Class
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: c415da15341f7800a706379d991cb753f5991170
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221167"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton Class

Bu sınıfın türetildiği [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturmak için.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınıza.

`CComClassFactorySingleton` öğesinden türetilen [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturmak için. Her çağrı `CreateInstance` yöntemi yalnızca bu nesne bir arabirim işaretçisi için sorgular.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Sorguları `m_spObj` için bir arabirim işaretçisi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tarafından oluşturulan nesne `CComClassFactorySingleton`.|

## <a name="remarks"></a>Açıklamalar

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir `CComClassFactory` olarak varsayılan sınıf üreteci. Kullanılacak `CComClassFactorySingleton`, belirtin [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) makrosu, nesnenin sınıf tanımında. Örneğin:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance

Çağrıları `QueryInterface` aracılığıyla [m_spObj](#m_spobj) bir arabirim işaretçisini almak için.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
[in] Nesne bir toplamanın parçası olarak ardından oluşturuluyorsa *pUnkOuter* dış bilinmeyen olması gerekir. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*riid*<br/>
[in] İstenen arabirim Laboratuvardaki. Varsa *pUnkOuter* kullanmaktan, *riid* olmalıdır `IID_IUnknown`.

*ppvObj*<br/>
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppvObj* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj

[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tarafından oluşturulan nesne `CComClassFactorySingleton`.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Açıklamalar

Her çağrı [CreateInstance](#createinstance) yöntemi yalnızca bu nesne bir arabirim işaretçisi için sorgular.

Unutmayın, geçerli form `m_spObj` sunan bir arabirimden değişiklik, `CComClassFactorySingleton` ATL önceki sürümlerinde çalışan Önceki sürümlerde `CComClassFactorySingleton` nesnenin oluşturulduğu sınıf üreteci ile aynı zamanda sunucu başlatma sırasında. Görselde C++.NET 2003 ve sonraki nesne oluşturulur gevşek, ilk isteği. Bu değişiklik, üzerinde erken başlatma kullanan programlar hatalara yol açabilir.

## <a name="see-also"></a>Ayrıca bkz.

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 Sınıfı](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread Sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
