---
title: "CComClassFactory sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs: C++
helpviewer_keywords: CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2af57c666cf2ee452d2707045d259ada695a2848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomclassfactory-class"></a>CComClassFactory sınıfı
Bu sınıf uygulayan [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) arabirimi.  
  
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
|[CComClassFactory::CreateInstance](#createinstance)|Belirtilen CLSID bir nesne oluşturur.|  
|[CComClassFactory::LockServer](#lockserver)|Bellek sınıfı fabrikada kilitler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComClassFactory`uygulayan [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) daha hızlı oluşturulacak yeni nesneler izin vermek için bellek sınıfı fabrikada kilitleme yanı sıra belirli CLSID bir nesne oluşturmak için kullanılan yöntemler içerir arabirimi. **IClassFactory** sistem kayıt defterinde ve CLSID atamak için kayıt her sınıf için uygulanması gerekir.  
  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir `CComClassFactory` varsayılan üreteci olarak. Bu varsayılanı geçersiz kılmak için aşağıdakilerden birini belirtin `DECLARE_CLASSFACTORY` *XXX* Sınıf tanımınız makrolarındaki. Örneğin, [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) makrosu üreteci için belirtilen sınıf kullanır:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 Yukarıdaki sınıf tanımını belirleyen **CMyClassFactory** nesnenin varsayılan üreteci kullanılır. **CMyClassFactory** öğesinden türetilmelidir `CComClassFactory` ve geçersiz kılma `CreateInstance`.  
  
 ATL bir üreteci bildirme üç makroları sağlar:  
  
- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) kullanan [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), bir lisans ile oluşturma denetler.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) kullanan [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), birden çok grupların nesneler oluşturur.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) kullanan [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), tek bir yapıları [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory::CreateInstance  
 Belirtilen CLSID bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
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
  
##  <a name="lockserver"></a>CComClassFactory::LockServer  
 Artırır ve modül kilit sayısı çağırarak azaltır **_Module::Lock** ve **_Module::Unlock**sırasıyla.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Parametreler  
 `fLock`  
 [in] Varsa **TRUE**kilit sayısı artırılır; Aksi takdirde, kilit sayısı düşülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 **_Module** genel örneğine başvurur [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.  
  
 Çağırma `LockServer` böylece birden fazla nesne hızlı oluşturulabilir üreteci tutmak bir istemcinin sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
