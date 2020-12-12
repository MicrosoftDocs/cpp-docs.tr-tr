---
description: 'Daha fazla bilgi edinin: CComClassFactoryAutoThread sınıfı'
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
ms.openlocfilehash: 9d25303d4d40f695c68fdf09aae7d56e6f1e5fb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152288"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread sınıfı

Bu sınıf, [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve nesnelerin birden çok apartmanlarda oluşturulmasına izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactoryAutoThread:: CreateInstance](#createinstance)|Belirtilen CLSID 'nin bir nesnesini oluşturur.|
|[CComClassFactoryAutoThread:: LockServer](#lockserver)|Bellek içinde sınıf fabrikasını kilitler.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactoryAutoThread` , [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)ile benzerdir, ancak nesnelerin birden çok apartmanlarda oluşturulmasına izin verir. Bu destekten faydalanmak için, [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)' dan exe modülünüzü türetebilirsiniz.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak bildiren [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)makro içerir. Kullanmak için `CComClassFactoryAutoThread` , nesnenizin sınıf tanımında [declare_classfactory_auto_thread](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosunu belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a> CComClassFactoryAutoThread:: CreateInstance

Belirtilen CLSID 'nin bir nesnesini oluşturur ve bu nesneye bir arabirim işaretçisi alır.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
'ndaki Nesne bir toplamanın parçası olarak oluşturulduysa, *pUnkOuter* , bilinmeyen dıştaki olmalıdır. Aksi halde, *pUnkOuter* null olmalıdır.

*riıd*<br/>
'ndaki İstenen arabirimin IID 'si. *PUnkOuter* null değilse, *riıd* olmalıdır `IID_IUnknown` .

*ppvObj*<br/>
dışı *Riıd* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Modülünüzün [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)Öğesinden türemesi durumunda, `CreateInstance` önce ilişkili grupta nesneyi oluşturmak için bir iş parçacığı seçer.

## <a name="ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a> CComClassFactoryAutoThread:: LockServer

Sırasıyla ve çağırarak modül kilit sayısını artırır ve azaltır `_Module::Lock` `_Module::Unlock` .

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
'ndaki TRUE ise kilit sayısı artırılır; Aksi takdirde kilit sayısı azaltılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Kullanırken `CComClassFactoryAutoThread` , `_Module` genellikle [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)genel örneğine başvurur.

Çağırma `LockServer` , bir istemcinin birden fazla nesnenin hızla oluşturulabilmesi için bir sınıf fabrikasına sahip olmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 sınıfı](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
