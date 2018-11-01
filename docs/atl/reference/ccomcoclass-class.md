---
title: CComCoClass sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: 51da70cc1972e6a69e28d7699703f803b6fa8701
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630704"
---
# <a name="ccomcoclass-class"></a>CComCoClass sınıfı

Bu sınıf, bir sınıfın örneklerini oluşturmak ve özelliklerini almak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `CComCoClass`.

*pclsid*<br/>
CLSID nesnenin bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCoClass::CreateInstance](#createinstance)|(Statik) Bir arabirim için sorgular ve sınıfı bir örneğini oluşturur.|
|[CComCoClass::Error](#error)|(Statik) Zengin hata bilgileri istemciye döndürür.|
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Statik) Nesne sınıfı tanımlayıcısı döndürür.|
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Statik) Nesnenin açıklamasını döndürmek için geçersiz kılın.|

## <a name="remarks"></a>Açıklamalar

`CComCoClass` bir nesnenin CLSID alma, hata bilgilerini ayarlama ve sınıfın örnekleri oluşturmak için yöntemleri sağlar. Nesne eşlemesindeki kayıtlı herhangi bir sınıf nesnesinden türetilmesi `CComCoClass`.

`CComCoClass` Ayrıca, nesneniz için varsayılan sınıf üreteci ve toplama modelini tanımlar. `CComCoClass` Aşağıdaki iki makro kullanır:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) olmasını sınıf üreteci bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) nesnenizin toplanabilir bildirir.

Başka bir makro, sınıf tanımında belirterek ya da bu varsayılan geçersiz kılabilirsiniz. Örneğin, kullanılacak [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) yerine `CComClassFactory`, belirtin [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="createinstance"></a>  CComCoClass::CreateInstance

Bu `CreateInstance` işlevleri bir COM bir örneğini oluşturmak için nesne ve COM API'ı kullanmadan bir arabirim işaretçisi alır.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Parametreler

*Q*<br/>
Aracılığıyla döndürülmesi gereken bir COM arabirimi *pp*.

*punkOuter*<br/>
[in] Dış bilinmeyen veya toplamanın kontrol eden bilinmeyen.

*PP*<br/>
[out] Oluşturma başarılı olursa, istenen arabirim işaretçisi alır bir işaretçi değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini. Bkz: [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) olası dönüş değerlerinin bir açıklaması için Windows SDK.

### <a name="remarks"></a>Açıklamalar

Bu işlevin ilk aşırı yükleme, tipik bir nesne oluşturmak için kullanın. İkinci aşırı yükleme, oluşturulan nesne toplamak, ihtiyacınız olduğunda kullanın.

Gerekli COM nesnesi uygulayan ATL sınıfı (diğer bir deyişle, ilk şablon parametresi olarak kullanılan sınıf [CComCoClass](../../atl/reference/ccomcoclass-class.md)) çağırma kodu aynı projede olmalıdır. COM nesnesinin oluşturulmasını kayıtlı bu ATL sınıfı için sınıf üreteci tarafından gerçekleştirilir.

Bu işlevler kullanarak harici olarak oluşturulabilir yüklenmesini önleyen nesneleri oluşturmak için yararlıdır [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) makrosu. Bunlar, aynı zamanda COM API verimliliği nedeniyle kaçınmak istediğiniz durumlarda da kullanışlıdır.

Unutmayın arabirimi *Q* kullanarak alınabilmesi için bir IID ilişkili olmalıdır [__uuidof](../../cpp/uuidof-operator.md) işleci.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CDocument` ATL Sihirbazı tarafından oluşturulan sınıf türetilir `CComCoClass` uygulayan `IDocument` arabirimi. İstemcileri kullanarak belge örnekleri oluşturmasının OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO makro nesne eşlemesindeki sınıf kaydettirildikten [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance). `CApplication` bir yöntem bir belge sınıfı örneğini oluşturmak için kendi COM arabirimleri sağlar. bir CoClass ' dir. Ne kadar kolay olduğunu gösterir aşağıdaki kod örnekleri kullanarak belge sınıfı oluşturmak için `CreateInstance` öğesinden devralınan üye `CComCoClass` temel sınıfı.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

##  <a name="error"></a>  CComCoClass::Error

Bu statik işlev ayarlar `IErrorInfo` arabirimi istemciye hata bilgilerini sağlar.

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

*lpszDesc*<br/>
[in] Hatayı açıklayan bir dize. Unicode sürümü `Error` belirten *lpszDesc* değil LPCOLESTR türü; ANSI sürümü LPCSTR türünü belirtir.

*IID*<br/>
[in] Hata işletim sistemi tarafından tanımlanmış olması durumunda hata veya GUID_NULL (varsayılan değer) tanımlama arabirimi Laboratuvardaki.

*Xact_s_lastresourcemanager*<br/>
[in] İstediğiniz HRESULT arayana döndürülür. Varsayılan değer 0’dır. Hakkında daha fazla ayrıntı için *Xact_s_lastresourcemanager*, açıklamalara bakın.

*nID*<br/>
[in] Hata açıklaması dizesi depolandığı kaynak tanımlayıcısı. Bu değer 0x0200 ile 0xFFFF arasında aralığında yer alan. Hata ayıklama yapılarında, bir **ASSERT** neden olur *nID* geçerli bir dize dizinini oluşturmaz. Sürüm yapılarında hata açıklama dizesi "İçin bilinmeyen hata." ayarlanır.

*dwHelpID*<br/>
[in] Hata için Yardım içeriği tanımlayıcı.

*lpszHelpFile*<br/>
[in] Hatayı açıklayan Yardım dosyasının adı ve yolu.

*hInst*<br/>
[in] Kaynağı için tanıtıcı. Varsayılan olarak, bu parametredir `_AtlModule::GetResourceInstance`burada `_AtlModule` genel örneğinin [CAtlModule](../../atl/reference/catlmodule-class.md).

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Çağrılacak `Error`, nesnenizin uygulamalıdır `ISupportErrorInfo Interface` arabirimi.

Varsa *Xact_s_lastresourcemanager* parametresi, sıfır olmayan, ardından `Error` değerini döndürür *Xact_s_lastresourcemanager*. Varsa *Xact_s_lastresourcemanager* sıfır sonra ilk dört sürümleri `Error` DISP_E_EXCEPTION döndürür. Son iki sürüm makronun sonucu döndürür **MAKE_HRESULT (1, FACILITY_ITF,** *nID* **)**.

##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID

Nesnenin CLSID'si alma tutarlı bir yol sağlar.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne sınıf tanımlayıcısı.

##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription

Bu statik işlev sınıfı nesnenizin metin açıklamasını alır.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfı nesne açıklaması.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, NULL döndürür. Bu yöntem ile geçersiz kılabilirsiniz [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) makrosu. Örneğin:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription` çağıran `IComponentRegistrar::GetComponents`. `IComponentRegistrar` kaydolun ve bileşenleri tek tek bir DLL kaydını olanak tanıyan bir Otomasyon arabirimidir. ATL projesi Sihirbazı'yla bir bileşeni kayıt şirketi nesnesi oluşturduğunuzda, sihirbaz otomatik olarak Uygula `IComponentRegistrar` arabirimi. `IComponentRegistrar` genellikle Microsoft işlem sunucusu tarafından kullanılır.

ATL projesi Sihirbazı hakkında daha fazla bilgi için bkz [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
