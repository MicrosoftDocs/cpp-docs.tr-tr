---
title: CComClassFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf6f830441482e17bd45c331f4281cb49312337
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765105"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory sınıfı

Bu sınıfın uyguladığı [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimi.

## <a name="syntax"></a>Sözdizimi

```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactory::CreateInstance](#createinstance)|Belirtilen CLSID'yi bir nesne oluşturur.|
|[CComClassFactory::LockServer](#lockserver)|Sınıf üreteci bellekte kilitler.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactory` uygulayan [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimi, yeni nesneler daha hızlı bir şekilde oluşturulmasına izin vermek için bellekte sınıf üreteci kilitleme yanı sıra belirli bir CLSID bir nesne oluşturmak için yöntemleri içerir. `IClassFactory` Sistem kayıt defterinde ve CLSID atamak için kaydettiğiniz her sınıf için uygulanmalıdır.

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir `CComClassFactory` olarak varsayılan sınıf üreteci. Bu varsayılanı geçersiz kılmak için aşağıdakilerden birini belirtin `DECLARE_CLASSFACTORY` *XXX* sınıf tanımına makrolarındaki. Örneğin, [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) makrosu belirtilen sınıfı için sınıf üreteci kullanır:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Yukarıdaki sınıf tanımı belirten `CMyClassFactory` nesnenin varsayılan sınıf üreteci kullanılır. `CMyClassFactory` öğesinden türetilmelidir `CComClassFactory` ve geçersiz kılma `CreateInstance`.

ATL bir sınıf üreteci bildirmek üç makroları sağlar:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) kullanan [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), bir lisans ile oluşturma denetler.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) kullanan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), içinde birden çok apartmanlar nesneleri oluşturur.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) kullanan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), tek bir yapıları [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory::CreateInstance

Belirtilen CLSID'yi bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*  
[in] Nesne bir toplamanın parçası olarak ardından oluşturuluyorsa *pUnkOuter* dış bilinmeyen olması gerekir. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*riid*  
[in] İstenen arabirim Laboratuvardaki. Varsa *pUnkOuter* kullanmaktan, *riid* olmalıdır `IID_IUnknown`.

*ppvObj*  
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppvObj* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="lockserver"></a>  CComClassFactory::LockServer

Artırır ve azaltır modülün kilit sayacını çağırarak `_Module::Lock` ve `_Module::Unlock`sırasıyla.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*  
[in] TRUE ise kilit sayacını artırılır; Aksi takdirde, kilit sayısı azaltılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`_Module` global örneğine başvurur [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.

Çağırma `LockServer` bir istemci birden çok nesne hızla oluşturulabilen bir sınıf üreteci tutacak sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
