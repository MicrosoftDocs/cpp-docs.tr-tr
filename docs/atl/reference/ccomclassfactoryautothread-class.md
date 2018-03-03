---
title: "CComClassFactoryAutoThread sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 916bd22a982e70a7acb50793723be23416516d04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread sınıfı
Bu sınıf uygulayan [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) arabirim ve nesnelerin içinde birden çok grupların oluşturulmasına izin verir.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Belirtilen CLSID bir nesne oluşturur.|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Bellek sınıfı fabrikada kilitler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComClassFactoryAutoThread`benzer [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ancak nesnelerin içinde birden çok grupların oluşturulmasına izin verir. Bu destek yararlanmak için EXE modülünden türetin [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Kullanılacak `CComClassFactoryAutoThread`, belirtin [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosu, nesnenin sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 [İn uygulamasına](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance  
 Belirtilen CLSID bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkOuter`  
 [in] Nesne bir toplama bir parçası olarak sonra oluşturuldu, `pUnkOuter` dış bilinmeyen olması gerekir. Aksi takdirde, `pUnkOuter` olmalıdır **NULL**.  
  
 `riid`  
 [in] İstenen arabirim IID. Varsa `pUnkOuter` olan olmayan **NULL**, `riid` olmalıdır **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppvObj` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Modülünüzün türetilen varsa [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` ilk ilişkili grupta nesnesi oluşturmak için bir iş parçacığı seçer.  
  
##  <a name="lockserver"></a>CComClassFactoryAutoThread::LockServer  
 Artırır ve modül kilit sayısı çağırarak azaltır **_Module::Lock** ve **_Module::Unlock**sırasıyla.  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>Parametreler  
 `fLock`  
 [in] Varsa **TRUE**kilit sayısı artırılır; Aksi takdirde, kilit sayısı düşülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanırken `CComClassFactoryAutoThread`, **_Module** genellikle genel örneğine başvurur [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Çağırma `LockServer` böylece birden fazla nesne hızlı oluşturulabilir üreteci tutmak bir istemcinin sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 sınıfı](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
