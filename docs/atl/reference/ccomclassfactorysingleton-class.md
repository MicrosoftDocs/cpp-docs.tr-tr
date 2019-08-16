---
title: CComClassFactorySingleton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: 71705d02140f0392a9ce023c64e7b4125c14443f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497398"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton sınıfı

Bu sınıf [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilir ve tek bir nesne oluşturmak Için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız.

`CComClassFactorySingleton`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'den türetilir ve tek bir nesne oluşturmak Için [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) kullanır. `CreateInstance` Yöntemine yapılan her çağrı yalnızca bir arabirim işaretçisi için bu nesneyi sorgular.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactorySingleton:: CreateInstance](#createinstance)|Arabirim `m_spObj` işaretçisi için sorgular.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactorySingleton:: m_spObj](#m_spobj)|Tarafından`CComClassFactorySingleton`oluşturulan [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi.|

## <a name="remarks"></a>Açıklamalar

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, varsayılan sınıf [](aggregation-and-class-factory-macros.md#declare_classfactory)fabrikası olarak bildiren `CComClassFactory` DECLARE_CLASSFACTORY makrosunu içerir. Kullanmak `CComClassFactorySingleton`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) makrosunu belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="createinstance"></a>CComClassFactorySingleton:: CreateInstance

M_spObj `QueryInterface` aracılığıyla [](#m_spobj) bir arabirim işaretçisi almak için çağırır.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
'ndaki Nesne bir toplamanın parçası olarak oluşturulduysa, *pUnkOuter* , bilinmeyen dıştaki olmalıdır. Aksi halde, *pUnkOuter* null olmalıdır.

*riıd*<br/>
'ndaki İstenen arabirimin IID 'si. *PUnkOuter* null değilse, *riıd* olmalıdır `IID_IUnknown`.

*ppvObj*<br/>
dışı *Riıd*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="m_spobj"></a>CComClassFactorySingleton:: m_spObj

Tarafından`CComClassFactorySingleton`oluşturulan [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Açıklamalar

[CreateInstance](#createinstance) yöntemine yapılan her çağrı yalnızca bir arabirim işaretçisi için bu nesneyi sorgular.

Geçerli formun `m_spObj` , ATL 'nin önceki sürümlerinde çalışma yoluyla bir son değişiklik olduğunu `CComClassFactorySingleton` unutmayın. Önceki sürümlerde `CComClassFactorySingleton` nesne, sunucu başlatma sırasında sınıf fabrikası ile aynı zamanda oluşturulmuştur. Visual C++.NET 2003 ve sonraki sürümlerde, nesne geç, ilk istekte oluşturulur. Bu değişiklik, erken başlatmaya dayalı programlarda hatalara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 Sınıfı](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread Sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
