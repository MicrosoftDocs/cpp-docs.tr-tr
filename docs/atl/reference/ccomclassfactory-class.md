---
title: CComClassFactory Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 041575339906b83488697f1db5a7f8b08b53070e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321029"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory Sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomclassFactory::CreateInstance](#createinstance)|Belirtilen CLSID bir nesne oluşturur.|
|[CcomclassFactory::LockServer](#lockserver)|Sınıf fabrikasını hafızaya kilitler.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactory`belirli bir CLSID nesnesi oluşturmak için yöntemler içeren [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular ve yeni nesnelerin daha hızlı oluşturulmasına izin vermek için sınıf fabrikasını bellekte kilitler. `IClassFactory`sistem kayıt defterine kaydettiğiniz ve clsid atadığınız her sınıf için uygulanmalıdır.

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)varsayılan sınıf fabrikası `CComClassFactory` olarak bildiren makro DECLARE_CLASSFACTORY içerir. Bu varsayılanı geçersiz kılmak için `DECLARE_CLASSFACTORY`sınıf tanımınızdaki *XXX* makrolarından birini belirtin. Örneğin, [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) makro sınıf fabrikası için belirtilen sınıfı kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Yukarıdaki sınıf tanımı, nesnenin varsayılan sınıf fabrikası olarak kullanılacak belirtir. `CMyClassFactory` `CMyClassFactory`türetin `CComClassFactory` ve geçersiz `CreateInstance`kılmalıdır.

ATL, sınıf fabrikası nı bildiren diğer üç makro sağlar:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Bir lisans aracılığıyla oluşturma yı kontrol eden [CComClassFactory2'yi](../../atl/reference/ccomclassfactory2-class.md)kullanır.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Birden çok dairenesneleri oluşturur [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)kullanır.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Tek bir [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi oluşturan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)kullanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomclassfactorycreateinstance"></a><a name="createinstance"></a>CcomclassFactory::CreateInstance

Belirtilen CLSID bir nesne oluşturur ve bu nesneye bir arabirim işaretçisi alır.

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

## <a name="ccomclassfactorylockserver"></a><a name="lockserver"></a>CcomclassFactory::LockServer

Modül kilidi sayısısırasıyla arayarak `_Module::Lock` ve sırasıyla `_Module::Unlock`artışlar ve kararnameler.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*Sürü*<br/>
[içinde] DOĞRUysa, kilit sayısı artımlı; aksi takdirde, kilit sayısı bozulür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`_Module`[CComModule'in](../../atl/reference/ccommodule-class.md) veya ondan türetilen bir sınıfın genel örneğini ifade eder.

Arama, `LockServer` istemcinin bir sınıf fabrikasını tutmasına izin verir, böylece birden çok nesne hızlı bir şekilde oluşturulabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Ccomglobalsthreadmodel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
