---
title: CComCoClass sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
dev_langs:
- C++
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 738d7e937acf2d3299be97b4f091c698582911d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365468"
---
# <a name="ccomcoclass-class"></a>CComCoClass sınıfı
Bu sınıf, bir sınıfın örneklerini oluşturmak ve özelliklerini almak için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `CComCoClass`.  
  
 *pclsid*  
 Nesne CLSID gösteren bir işaretçi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](#createinstance)|(Statik) Bir arabirim için sorgular ve sınıfı örneği oluşturur.|  
|[CComCoClass::Error](#error)|(Statik) Zengin hata bilgilerini istemciye döndürür.|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Statik) Nesne sınıfı tanımlayıcısı döndürür.|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Statik) Nesnenin açıklamasını döndürmek için geçersiz kılın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComCoClass` bir nesnenin CLSID alma, hata bilgilerini ayarlama ve sınıf örneklerini oluşturma yöntemleri sağlar. Herhangi bir sınıf kayıtlı [nesne eşlemesi](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f) türetilmiş `CComCoClass`.  
  
 `CComCoClass` Ayrıca, nesne için varsayılan sınıf Fabrika ve toplama modeli tanımlar. `CComCoClass` Aşağıdaki iki makroları kullanır:  
  
- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) olmasını üreteci bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) nesnenizin kümelenebilir bildirir.  
  
 Bu varsayılan birini Sınıf tanımınız içinde başka bir makrosu belirterek geçersiz kılabilirsiniz. Örneğin, kullanılacak [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) yerine `CComClassFactory`, belirtin [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="createinstance"></a>  CComCoClass::CreateInstance  
 Bunlar kullanmak `CreateInstance` işlevlerinin bir COM örneğini oluşturmak için nesne ve COM API kullanmadan bir arabirim işaretçisi almak.  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `Q`  
 Aracılığıyla döndürülmelidir COM arabirimi `pp`.  
  
 *punkOuter*  
 [in] Dış bilinmeyen veya toplama denetleme bilinmiyor.  
  
 `pp`  
 [out] Oluşturma işlemi başarılı olursa, istenen arabirim işaretçisi aldığı işaretçi değişkeninin adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri. Bkz: [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) olası dönüş değerleri bir açıklaması için Windows SDK.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin ilk tipik nesne oluşturmak için kullanın; oluşturulan nesne toplamak gerektiğinde ikinci aşırı yüklemesini kullanın.  
  
 Gerekli COM Nesne uygulama ATL sınıfı (diğer bir deyişle, ilk şablon parametresi olarak kullanılan sınıf [CComCoClass](../../atl/reference/ccomcoclass-class.md)) çağıran kodu aynı projede olmalıdır. COM nesnesinin oluşturulmasını bu ATL sınıfı için kayıtlı sınıf üreticisi tarafından gerçekleştirilir.  
  
 Bu işlevler kullanarak dışarıdan creatable yüklenmesini engelledi nesneleri oluşturmak için yararlı olan [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) makrosu. Bunlar, aynı zamanda verimlilik, nedeniyle COM API önlemek istediğiniz durumlarda da kullanışlıdır.  
  
 Unutmayın arabirimi `Q` kullanılarak alınabilir kendisiyle ilişkili bir IID olmalıdır [__uuidof](../../cpp/uuidof-operator.md) işleci.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `CDocument` bir sihirbaz tarafından oluşturulan ATL sınıfın türetildiği `CComCoClass` uygulayan **IDocument** arabirimi. Sınıf ile nesne eşlemesindeki kayıtlı `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` istemcileri belge kullanma örnekleri oluşturamıyor makrosu [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615). `CApplication` belge sınıfının örnekleri oluşturmak için kendi COM arabirimleri birinde bir yöntem sağlar CoClass ' dir. Ne kadar kolay gösterir aşağıdaki kodu kullanarak belge sınıf örnekleri oluşturmak için `CreateInstance` üye devralınan `CComCoClass` temel sınıfı.  
  
 [!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>  CComCoClass::Error  
 Bu statik işlev ayarlayan `IErrorInfo` istemciye hata bilgileri sağlamak için arabirim.  
  
```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszDesc`  
 [in] Hatayı açıklayan dize. Unicode sürümünü `Error` belirtir `lpszDesc` türü **LPCOLESTR**; ANSI sürümü türünü `LPCSTR`.  
  
 `iid`  
 [in] Hata tanımlayan arabirim IID veya `GUID_NULL` (varsayılan değer) hata işletim sistemi tarafından tanımlanmış olması durumunda.  
  
 `hRes`  
 [in] `HRESULT` İstediğiniz çağırana döndürülen. Varsayılan değer 0’dır. Hakkında daha fazla ayrıntı için `hRes`, açıklamalar'a bakın.  
  
 `nID`  
 [in] Hata açıklama dizesi depolandığı kaynak tanımlayıcısı. Bu değer 0x0200 arasında 0xFFFF, ikisi de dahil olmak kalan. Hata ayıklama derlemelerinde, bir **ASSERT** neden olur `nID` geçerli bir dize dizin kullanılamıyor. Yayın derlemelerde "İçin bilinmeyen hata." hatası açıklama dizesi ayarlanacak  
  
 `dwHelpID`  
 [in] Hata için Yardım içeriği tanımlayıcı.  
  
 `lpszHelpFile`  
 [in] Hatayı açıklayan Yardım dosyasının adını ve yolunu.  
  
 `hInst`  
 [in] Kaynağı için tanıtıcı. Varsayılan olarak, bu parametredir **_AtlModule::GetResourceInstance**, burada **_AtlModule** genel örneğinin [CAtlModule](../../atl/reference/catlmodule-class.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrılacak `Error`, nesnenizin uygulamalıdır `ISupportErrorInfo Interface` arabirimi.  
  
 Varsa `hRes` parametredir sıfır olmayan, ardından `Error` değerini döndürür `hRes`. Varsa `hRes` sıfır sonra ilk dört sürümleri olan `Error` iade `DISP_E_EXCEPTION`. Son iki sürüm makrosu sonuç **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID  
 Nesnenin CLSID alma tutarlı bir yol sağlar.  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne sınıfı tanımlayıcısı.  
  
##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription  
 Bu statik işlev sınıfı nesnenizin metin açıklamasını alır.  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınıf nesnenin açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama döndürür **NULL**. Bu yöntemle kılabilirsiniz [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) makrosu. Örneğin:  
  
 [!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription` tarafından çağrılır **IComponentRegistrar::GetComponents**. **IComponentRegistrar** kaydolun ve DLL bileşenleri tek tek kaydı olanak tanıyan bir Otomasyon arabirimdir. ATL Proje Sihirbazı'yla bir bileşen Kaydedicisi nesne oluşturduğunuzda, sihirbaz otomatik olarak uygulaması **IComponentRegistrar** arabirimi. **IComponentRegistrar** genellikle Microsoft işlem sunucusu tarafından kullanılır.  
  
 ATL Proje Sihirbazı hakkında daha fazla bilgi için bkz: [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
