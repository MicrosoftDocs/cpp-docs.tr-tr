---
description: 'Daha fazla bilgi edinin: CComClassFactory sınıfı'
title: CComClassFactory sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 36233abf13c6ff6963d02bc5431286ca6c783235
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152301"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory sınıfı

Bu sınıf [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular.

## <a name="syntax"></a>Syntax

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactory:: CreateInstance](#createinstance)|Belirtilen CLSID 'nin bir nesnesini oluşturur.|
|[CComClassFactory:: LockServer](#lockserver)|Bellek içinde sınıf fabrikasını kilitler.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactory` belirli bir CLSID 'nin bir nesnesi oluşturmak için gereken ve yeni nesnelerin daha hızlı oluşturulmasına izin vermek için bellekte sınıf fabrikasını kilitleyen [ıssfactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimini uygular. `IClassFactory` , sistem kayıt defterine kaydettiğinizde ve bir CLSID atadığınız her sınıf için uygulanmalıdır.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [](aggregation-and-class-factory-macros.md#declare_classfactory) `CComClassFactory` varsayılan sınıf fabrikası olarak bildiren DECLARE_CLASSFACTORY makro içerir. Bu varsayılanı geçersiz kılmak için, `DECLARE_CLASSFACTORY` sınıf tanımınızda *XXX* makrolarından birini belirtin. Örneğin, [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) makro sınıf fabrikası için belirtilen sınıfı kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Yukarıdaki sınıf tanımı `CMyClassFactory` , nesnenin varsayılan sınıf fabrikası olarak kullanılacağını belirtir. `CMyClassFactory` türevi `CComClassFactory` ve override olmalıdır `CreateInstance` .

ATL, bir sınıf fabrikası bildiren üç farklı makro sağlar:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) , Bir lisans aracılığıyla oluşturmayı denetleyen [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)kullanır.

- [declare_classfactory_auto_thread](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Birden çok apartmanlarda nesneler oluşturan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)kullanır.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Tek bir [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi oluşturan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)kullanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomclassfactorycreateinstance"></a><a name="createinstance"></a> CComClassFactory:: CreateInstance

Belirtilen CLSID 'nin bir nesnesini oluşturur ve bu nesneye bir arabirim işaretçisi alır.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
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

## <a name="ccomclassfactorylockserver"></a><a name="lockserver"></a> CComClassFactory:: LockServer

Sırasıyla ve çağırarak modül kilit sayısını artırır ve azaltır `_Module::Lock` `_Module::Unlock` .

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
'ndaki TRUE ise kilit sayısı artırılır; Aksi takdirde kilit sayısı azaltılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`_Module`[CComModule](../../atl/reference/ccommodule-class.md) 'un genel örneğine veya ondan türetilmiş bir sınıfa başvurur.

Çağırma `LockServer` , bir istemcinin birden fazla nesnenin hızla oluşturulabilmesi için bir sınıf fabrikasına sahip olmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
