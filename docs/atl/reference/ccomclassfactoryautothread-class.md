---
title: CComClassFactoryAutoThread Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: e997d92adfa9df46c82dacbd297db495b037c6e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320914"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread Sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve nesnelerin birden çok dairede oluşturulmasına izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomclassFactoryAutoThread::CreateInstance](#createinstance)|Belirtilen CLSID bir nesne oluşturur.|
|[CcomclassFactoryAutoThread::LockServer](#lockserver)|Sınıf fabrikasını hafızaya kilitler.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)benzer, ancak nesnelerin birden çok daire de oluşturulmasını sağlar. Bu destekten yararlanmak için EXE modülünüzü [CComAutoThreadModule'den](../../atl/reference/ccomautothreadmodule-class.md)türetin.

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak bildiren makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)içerir. Kullanmak `CComClassFactoryAutoThread`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makro belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a>CcomclassFactoryAutoThread::CreateInstance

Belirtilen CLSID bir nesne oluşturur ve bu nesneye bir arabirim işaretçisi alır.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

### <a name="remarks"></a>Açıklamalar

Modülünüz [CComAutoThreadModule'den](../../atl/reference/ccomautothreadmodule-class.md)türetilmiştirse, `CreateInstance` önce ilişkili dairede nesne oluşturmak için bir iş parçacığı seçer.

## <a name="ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a>CcomclassFactoryAutoThread::LockServer

Modül kilidi sayısısırasıyla arayarak `_Module::Lock` ve sırasıyla `_Module::Unlock`artışlar ve kararnameler.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*Sürü*<br/>
[içinde] DOĞRUysa, kilit sayısı artımlı; aksi takdirde, kilit sayısı bozulür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread`Kullanırken, `_Module` genellikle [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)küresel örnek anlamına gelir.

Arama, `LockServer` istemcinin bir sınıf fabrikasını tutmasına izin verir, böylece birden çok nesne hızla oluşturulabilir.

## <a name="see-also"></a>Ayrıca bkz.

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 Sınıfı](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton Sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Ccomglobalsthreadmodel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
