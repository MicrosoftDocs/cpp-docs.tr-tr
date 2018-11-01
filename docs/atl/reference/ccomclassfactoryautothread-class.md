---
title: CComClassFactoryAutoThread sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: 30a9d52ff661fd4fa39344382402aa6ff09d193f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574830"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread sınıfı

Bu sınıfın uyguladığı [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirim ve nesnelerin içinde birden çok apartmanlar oluşturulmasına izin verir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Belirtilen CLSID'yi bir nesne oluşturur.|
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Sınıf üreteci bellekte kilitler.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread` benzer [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ancak nesnelerin içinde birden çok apartmanlar oluşturulmasına izin verir. Bu destek avantajlarından yararlanmak için EXE modülünden türetilen [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Kullanılacak `CComClassFactoryAutoThread`, belirtin [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosu, nesnenin sınıf tanımında. Örneğin:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance

Belirtilen CLSID'yi bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

### <a name="remarks"></a>Açıklamalar

Modülünüzün türetildiği varsa [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` ilişkili grupta nesneyi oluşturmak için bir iş parçacığı ilk seçer.

##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer

Artırır ve azaltır modülün kilit sayacını çağırarak `_Module::Lock` ve `_Module::Unlock`sırasıyla.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
[in] TRUE ise kilit sayacını artırılır; Aksi takdirde, kilit sayısı azaltılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Kullanırken `CComClassFactoryAutoThread`, `_Module` genellikle global örneğine başvurur [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Çağırma `LockServer` bir istemci birden çok nesne hızla oluşturulabilen bir sınıf üreteci tutacak sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 Sınıfı](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton Sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
