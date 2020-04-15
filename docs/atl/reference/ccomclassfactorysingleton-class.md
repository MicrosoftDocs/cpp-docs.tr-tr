---
title: CComClassFactorySingleton Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: ec860f7ef59b7d3289bf2e18fea0f0e064a7c8f9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320815"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton Sınıfı

Bu sınıf [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) türetilmiştir ve tek bir nesne oluşturmak için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Senin sınıfın.

`CComClassFactorySingleton`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) türetilmiştir ve tek bir nesne oluşturmak için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır. Yönteme `CreateInstance` yapılan her çağrı, bu nesneyi bir arabirim işaretçisi için sorgular.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Arabirim `m_spObj` işaretçisi için sorgular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi `CComClassFactorySingleton`tarafından oluşturulmuştur.|

## <a name="remarks"></a>Açıklamalar

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)varsayılan sınıf fabrikası `CComClassFactory` olarak bildiren makro DECLARE_CLASSFACTORY içerir. Kullanmak `CComClassFactorySingleton`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) makro belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CcomclassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a>CComClassFactorySingleton::CreateInstance

Arabirim işaretçisini almak için `QueryInterface` [m_spObj'den](#m_spobj) arama lar.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
[içinde] Nesne bir agreganın parçası olarak oluşturuluyorsa, *pUnkOuter* dış bilinmeyen olmalıdır. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*Riid*<br/>
[içinde] İstenen arabirimin IID'si. *pUnkOuter* non-NULL ise, *riid* olmalıdır. `IID_IUnknown`

*ppvObj*<br/>
[çıkış] *riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomclassfactorysingletonm_spobj"></a><a name="m_spobj"></a>CComClassFactorySingleton::m_spObj

[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi `CComClassFactorySingleton`tarafından oluşturulmuştur.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Açıklamalar

[CreateInstance](#createinstance) yöntemine yapılan her çağrı, bu nesneyi bir arabirim işaretçisi için sorgular.

Geçerli formun `m_spObj` ATL'nin önceki sürümlerinde `CComClassFactorySingleton` çalışma şeklinden bir kırılma değişikliği sunduğunu unutmayın. Önceki sürümlerde `CComClassFactorySingleton` nesne, sunucu başlatma sırasında sınıf fabrikasıyla aynı anda oluşturulmuştur. Visual C++.NET 2003 ve sonraki durumlarda nesne ilk istek üzerine tembelce oluşturulur. Bu değişiklik, erken başlatmaya dayanan programlarda hatalara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 Sınıfı](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread Sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Ccomglobalsthreadmodel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
