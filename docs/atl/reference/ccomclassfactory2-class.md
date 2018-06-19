---
title: CComClassFactory2 sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da2b47290d3d0be525ca65b16733c9f42835d24e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363522"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 sınıfı
Bu sınıf uygulayan [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>Parametreler  
 *Lisans*  
 Aşağıdaki statik işlevler uygulayan bir sınıf:  
  
- **statik BOOL VerifyLicenseKey (BSTR** `bstr` **);**  
  
- **statik BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **statik BOOL IsLicenseValid ();**  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Belirtilen CLSID bir nesne oluşturur.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Bir lisans anahtarı belirtilen CLSID bir nesne oluşturur.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Bu sınıf üreticisi lisans özelliklerini açıklayan bilgileri alır.|  
|[CComClassFactory2::LockServer](#lockserver)|Bellek sınıfı fabrikada kilitler.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Oluşturur ve bir lisans anahtarı döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComClassFactory2` uygulayan [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) uzantısıdır arabirimi, [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** denetimleri nesne bir lisans ile oluşturma. Bir sınıf Fabrika lisanslı bir makinede yürütülen bir çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı tam makine lisans yoksa nesneleri örneği oluşturmak bir uygulama sağlar.  
  
 ATL nesneleri normalde türetme tarafından bir üreteci elde [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makrosu içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) varsayılan üreteci olarak. Kullanılacak `CComClassFactory2`, belirtin [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu, nesnenin sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, şablon parametresi `CComClassFactory2`, statik işlevler uygulamalıdır `VerifyLicenseKey`, `GetLicenseKey`, ve `IsLicenseValid`. Bir basit lisans sınıfın bir örnek verilmiştir:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2` hem türetilen **CComClassFactory2Base** ve *lisans*. **CComClassFactory2Base**, buna karşılık, türetilen **IClassFactory2** ve **in uygulamasına\< CComGlobalsThreadModel >**.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance  
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
  
### <a name="remarks"></a>Açıklamalar  
 Makine tam olarak lisansına sahip olması gerekir. Tam makine lisans mevcut değilse çağrı [CreateInstanceLic](#createinstancelic).  
  
##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic  
 Benzer şekilde [CreateInstance](#createinstance)dışında `CreateInstanceLic` bir lisans anahtarı gerektirir.  
  
```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
 */,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkOuter`  
 [in] Nesne bir toplama bir parçası olarak sonra oluşturuldu, `pUnkOuter` dış bilinmeyen olması gerekir. Aksi takdirde, `pUnkOuter` olmalıdır **NULL**.  
  
 *pUnkReserved*  
 [in] Kullanılmıyor. Olmalıdır **NULL**.  
  
 `riid`  
 [in] İstenen arabirim IID. Varsa `pUnkOuter` olan olmayan **NULL**, `riid` olmalıdır **IID_IUnknown**.  
  
 `bstrKey`  
 [in] Çalışma zamanı lisans anahtarı daha önce edindiğiniz çağrısından `RequestLicKey`. Bu anahtar nesnesi oluşturmak için gereklidir.  
  
 `ppvObject`  
 [out] Arabirim işaretçisi tarafından belirtilen bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppvObject` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanarak bir lisans anahtarı edinebilirsiniz [RequestLicKey](#requestlickey). Bir nesne üzerinde lisanssız bir makine oluşturmak için çağırmalısınız `CreateInstanceLic`.  
  
##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo  
 Doldurur bir [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) üreteci açıklayan bilgileri yapısıyla yetenekleri lisans.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *pLicInfo*  
 [out] İşaretçi bir **LICINFO** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `fRuntimeKeyAvail` Bir lisans anahtarı verildiğinde, üreteci lisanssız bir makineye oluşturulmasını nesnelere izin verip vermediğini, bu yapı üyesi gösterir. *FLicVerified* üye tam makine lisans var olup olmadığını gösterir.  
  
##  <a name="lockserver"></a>  CComClassFactory2::LockServer  
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
  
##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey  
 Oluşturup, sağlanan bir lisans anahtarı döndürür `fRuntimeKeyAvail` üyesi [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) yapısı **doğru**.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwReserved`  
 [in] Kullanılmıyor. Sıfır olmalıdır.  
  
 `pbstrKey`  
 [out] Lisans anahtarı işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama için gerekli lisans anahtarıdır [CreateInstanceLic](#createinstancelic) lisanssız bir makinede nesne oluşturmak için. Varsa `fRuntimeKeyAvail` olan **yanlış**, sonra da tam lisanslı bir makinede nesneleri yalnızca oluşturulabilir.  
  
 Çağrı [GetLicInfo](#getlicinfo) değerini almak için `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComClassFactoryAutoThread sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
