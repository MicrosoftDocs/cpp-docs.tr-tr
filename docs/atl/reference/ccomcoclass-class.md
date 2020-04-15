---
title: Ccomcoclass Sınıfı
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
ms.openlocfilehash: 11e724a982f3a2f404473dbdd34d848842cc8e14
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320835"
---
# <a name="ccomcoclass-class"></a>Ccomcoclass Sınıfı

Bu sınıf, bir sınıfın örneklerini oluşturmak ve özelliklerini elde etmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CComCoClass`türetilmiştir.

*pclsid*<br/>
Nesnenin CLSID için bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomcoClass::CreateInstance](#createinstance)|(Statik) Sınıfın bir örneğini ve arabirim sorgularını oluşturur.|
|[CcomcoClass::Hata](#error)|(Statik) İstemciye zengin hata bilgilerini verir.|
|[CcomcoClass::GetObjectCLSID](#getobjectclsid)|(Statik) Nesnenin sınıf tanımlayıcısını döndürür.|
|[CcomcoClass::GetObjectDescription](#getobjectdescription)|(Statik) Nesnenin açıklamasını döndürmek için geçersiz kılın.|

## <a name="remarks"></a>Açıklamalar

`CComCoClass`nesnenin CLSID'sini almak, hata bilgilerini ayarlamak ve sınıfın örneklerini oluşturmak için yöntemler sağlar. Nesne eşlemi'nde kayıtlı herhangi `CComCoClass`bir sınıf.

`CComCoClass`nesneniz için varsayılan sınıf fabrika sını ve toplama modelini de tanımlar. `CComCoClass`aşağıdaki iki makroyu kullanır:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) Sınıf fabrikasını [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)olarak bildirir.

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) Nesnenizin toklanınabileceğini bildirir.

Sınıf tanımınızda başka bir makro belirterek bu varsayılanlardan birini geçersiz kılabilirsiniz. Örneğin, [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) yerine kullanmak `CComClassFactory`için, [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makro belirtin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomcoclasscreateinstance"></a><a name="createinstance"></a>CcomcoClass::CreateInstance

Com `CreateInstance` nesnesinin bir örneğini oluşturmak ve COM API'sini kullanmadan bir arabirim işaretçisi almak için bu işlevleri kullanın.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Parametreler

*S*<br/>
*pp*üzerinden döndürülmesi gereken COM arabirimi .

*punkOuter*<br/>
[içinde] Dış bilinmeyen veya toplam bilinmeyen kontrol.

*S*<br/>
[çıkış] Oluşturma başarılı olursa istenen arabirim işaretçisi alan bir işaretçi değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri. Olası iade değerlerinin açıklaması için Windows SDK'daki [CoCreateInstance'a](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) bakın.

### <a name="remarks"></a>Açıklamalar

Tipik nesne oluşturma için bu işlevin ilk aşırı yükünü kullanın; oluşturulan nesneyi toplamanız gerektiğinde ikinci aşırı yüklemeyi kullanın.

Gerekli COM nesnesini (diğer bir deyişle [CComCoClass'ın](../../atl/reference/ccomcoclass-class.md)ilk şablon parametresi olarak kullanılan sınıf) uygulayan ATL sınıfı, arama koduyla aynı projede olmalıdır. COM nesnesinin oluşturulması, bu ATL sınıfı için kayıtlı sınıf fabrikası tarafından gerçekleştirilir.

Bu işlevler, [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO makroyu](object-map-macros.md#object_entry_non_createable_ex_auto) kullanarak harici olarak gıyatılabilir olmasını engellediğiniz nesneleri oluşturmak için yararlıdır. Bunlar, verimlilik nedenleriyle COM API'den kaçınmak istediğiniz durumlarda da yararlıdır.

*Q* arabiriminin [__uuidof](../../cpp/uuidof-operator.md) işleci kullanılarak alınabilecek bir IID'si olması gerektiğini unutmayın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CDocument` `IDocument` arabirimi uygulayan sihirbaz tarafından `CComCoClass` oluşturulan BirTL sınıfı türetilmiştir. Sınıf, OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO makrosuyla nesne eşlemi içinde kayıtlıdır, bu nedenle istemciler [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)kullanarak belgenin örneklerini oluşturamaz. `CApplication`belge sınıfının örneklerini oluşturmak için kendi COM arabirimlerinden birinde bir yöntem sağlayan bir CoClass'tır. Aşağıdaki kod, taban sınıftan devralınan `CreateInstance` üyeyi kullanarak belge sınıfının `CComCoClass` örneklerini oluşturmanın ne kadar kolay olduğunu gösterir.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

## <a name="ccomcoclasserror"></a><a name="error"></a>CcomcoClass::Hata

Bu statik işlev `IErrorInfo` istemciye hata bilgisi sağlamak için arabirimi ayarlar.

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
[içinde] Hatayı açıklayan dize. `Error` *LpszDesc'in* Unicode sürümü LPCOLESTR tipi olduğunu belirtir; ANSI sürümü bir LPCSTR türünü belirtir.

*ııd*<br/>
[içinde] Hata işletim sistemi tarafından tanımlanırsa, hatayı tanımlayan arabirimin ikimliği veya GUID_NULL (varsayılan değer).

*hRes*<br/>
[içinde] Arayana döndürülmek istediğiniz HRESULT. Varsayılan değer 0’dır. *hRes*hakkında daha fazla bilgi için, Açıklamalar'a bakın.

*Nıd*<br/>
[içinde] Hata açıklaması dizesinin depolandığı kaynak tanımlayıcısı. Bu değer 0x0200 ile 0xFFFF arasında olmalıdır. Hata ayıklama yapılarında, *nID* geçerli bir dize ekizin vermezse bir **Assert** ortaya çıkacaktır. Sürüm yapılarında, hata açıklaması dizesi "Bilinmeyen Hata" olarak ayarlanır.

*dwHelpID*<br/>
[içinde] Hata için yardım bağlamı tanımlayıcısı.

*lpszHelpFile*<br/>
[içinde] Hatayı açıklayan yardım dosyasının yolu ve adı.

*hInst*<br/>
[içinde] Kaynağa tanıtıcı. Varsayılan olarak, bu `_AtlModule::GetResourceInstance`parametre `_AtlModule` , [CAtlModule'in](../../atl/reference/catlmodule-class.md)genel örneğidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Aramak `Error`için nesnenizin `ISupportErrorInfo Interface` arabirimi uygulaması gerekir.

*hRes* parametresi sıfır değilse, `Error` *hRes*değerini döndürür. *HRes* sıfır ise, `Error` daha sonra DISP_E_EXCEPTION dönmek ilk dört sürümü. Son iki sürüm makro MAKE_HRESULT **(1, FACILITY_ITF,** *nID)* **)** sonucunu döndürer.

## <a name="ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a>CcomcoClass::GetObjectCLSID

Nesnenin CLSID'sini almak için tutarlı bir yol sağlar.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin sınıf tanımlayıcısı.

## <a name="ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a>CcomcoClass::GetObjectDescription

Bu statik işlev, sınıf nesnenizin metin açıklamasını alır.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Dönüş Değeri

Sınıf nesnesinin açıklaması.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama NULL döndürür. Bu yöntemi [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) makrosuyla geçersiz kılabilirsiniz. Örneğin:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription`tarafından `IComponentRegistrar::GetComponents`çağrılır. `IComponentRegistrar`bir DLL'de tek tek bileşenleri kaydetmenize ve kaydetmenize olanak tanıyan bir Otomasyon arabirimidir. ATL Project Sihirbazı ile bir Bileşen Kayıt Defteri nesnesi `IComponentRegistrar` oluşturduğunuzda, sihirbaz arabirimi otomatik olarak uygular. `IComponentRegistrar`genellikle Microsoft Transaction Server tarafından kullanılır.

ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
