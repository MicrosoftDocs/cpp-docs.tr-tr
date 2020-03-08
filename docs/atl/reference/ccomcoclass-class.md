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
ms.openlocfilehash: 5b4e39fa4d93893d288bb8de03d8a71b671be087
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78863255"
---
# <a name="ccomcoclass-class"></a>CComCoClass sınıfı

Bu sınıf, bir sınıfın örneklerini oluşturmak ve özelliklerini almak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `CComCoClass`türetilir.

*pCLSID*<br/>
Nesnenin CLSID 'sine yönelik bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComCoClass:: CreateInstance](#createinstance)|Se Bir arabirim için sınıf ve sorgular örneği oluşturur.|
|[CComCoClass:: Error](#error)|Se İstemciye zengin hata bilgileri döndürür.|
|[CComCoClass:: GetObjectCLSID](#getobjectclsid)|Se Nesnenin sınıf tanımlayıcısını döndürür.|
|[CComCoClass:: GetObjectDescription](#getobjectdescription)|Se Nesnenin açıklamasını döndürmek için geçersiz kılın.|

## <a name="remarks"></a>Açıklamalar

`CComCoClass`, bir nesnenin CLSID 'SINI alma, hata bilgilerini ayarlama ve sınıfının örneklerini oluşturma yöntemlerini sağlar. Nesne haritasında kayıtlı olan herhangi bir sınıf `CComCoClass`türetilmelidir.

`CComCoClass` Ayrıca nesneniz için varsayılan sınıf fabrikası ve toplama modelini tanımlar. `CComCoClass` aşağıdaki iki makroyu kullanır:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) Sınıf fabrikasını [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)olarak bildirir.

- [declare_aggregatable](aggregation-and-class-factory-macros.md#declare_aggregatable) Nesnenizin toplanabilecek olduğunu bildirir.

Sınıf tanımınızda başka bir makro belirterek, bu varsayılandan birini geçersiz kılabilirsiniz. Örneğin, `CComClassFactory`yerine [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) kullanmak için [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makrosunu belirtin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="createinstance"></a>CComCoClass:: CreateInstance

Com API 'SI kullanmadan bir COM nesnesi örneği oluşturmak ve bir arabirim işaretçisi almak için bu `CreateInstance` işlevleri kullanın.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Parametreler

*Ç*<br/>
*PP*aracılığıyla DÖNDÜRÜLMESI gereken com arabirimi.

*punkOuter*<br/>
'ndaki Toplam bilinmiyor veya bilinmeyen denetim.

*Sy*<br/>
dışı Oluşturma başarılı olursa istenen arabirim işaretçisini alan bir işaretçi değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri. Olası dönüş değerlerinin bir açıklaması için Windows SDK 'de [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) ' a bakın.

### <a name="remarks"></a>Açıklamalar

Normal nesne oluşturma için bu işlevin ilk tekrar yüklemesini kullanın; oluşturulan nesneyi toplamanız gerektiğinde ikinci aşırı yüklemeyi kullanın.

Gerekli COM nesnesini uygulayan ATL sınıfı (yani, [CComCoClass](../../atl/reference/ccomcoclass-class.md)için ilk şablon parametresi olarak kullanılan sınıf), çağıran kodla aynı projede olmalıdır. COM nesnesinin oluşturulması, bu ATL sınıfı için kaydedilen sınıf fabrikası tarafından yürütülür.

Bu işlevler, [object_entry_non_createable_ex_auto](object-map-macros.md#object_entry_non_createable_ex_auto) makrosunu kullanarak dışarıdan oluşturulaönleyen nesneleri oluşturmak için faydalıdır. Bu durumlar Ayrıca, verimlilik açısından COM API 'sinden kaçınmak istediğiniz durumlarda faydalıdır.

*Q* arabiriminin, [__uuidof](../../cpp/uuidof-operator.md) işleci kullanılarak ALıNABILECEK kendisiyle ilişkili bir IID 'ye sahip olması gerektiğini unutmayın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte `CDocument`, `IDocument` arabirimini uygulayan `CComCoClass` türetilmiş, sihirbaz tarafından oluşturulan ATL sınıfıdır. Bu sınıf, OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO makrosuna sahip nesne haritasına kaydedilir, böylelikle istemciler [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)kullanarak belge örnekleri oluşturamaz. `CApplication`, kendi COM arabirimlerinden birine belge sınıfının örneklerini oluşturmak için bir yöntem sağlayan bir CoClass ' dır. Aşağıdaki kod, `CComCoClass` temel sınıfından devralınan `CreateInstance` üyesini kullanarak belge sınıfının örneklerinin ne kadar kolay oluşturulduğunu gösterir.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

##  <a name="error"></a>CComCoClass:: Error

Bu statik işlev, istemciye hata bilgilerini sağlamak için `IErrorInfo` arabirimini ayarlar.

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
'ndaki Hatayı açıklayan dize. `Error` Unicode sürümü, *lpszDesc* 'ın LPCOTASTR; türünde olduğunu belirtir ANSI sürümü bir LPCSTR türü belirtir.

*'si*<br/>
'ndaki Hata veya GUID_NULL tanımlayan arabirimin IID 'si (varsayılan değer) işletim sistemi tarafından tanımlanmışsa.

*hRes*<br/>
'ndaki Çağırana geri dönmek istediğiniz HRESULT. Varsayılan değer 0’dır. *HRes*hakkında daha fazla bilgi için bkz. açıklamalar.

*NID*<br/>
'ndaki Hata açıklaması dizesinin depolandığı kaynak tanımlayıcısı. Bu değer, ikisi de dahil olmak üzere 0x0200 ile 0xFFFF arasında olmalıdır. Hata ayıklama yapılarında, *NID* geçerli bir dizeye Dizin oluşturmadığı takdirde bir **onaylama** sonucu olur. Yayın derlemeleri ' nde hata açıklaması dizesi "Bilinmeyen hata" olarak ayarlanır.

*dwHelpID*<br/>
'ndaki Hatanın yardım bağlamı tanımlayıcısı.

*lpszHelpFile*<br/>
'ndaki Hatayı açıklayan Yardım dosyasının yolu ve adı.

*hInst*<br/>
'ndaki Kaynağın tanıtıcısı. Varsayılan olarak, bu parametre `_AtlModule::GetResourceInstance`, burada `_AtlModule` [CAtlModule](../../atl/reference/catlmodule-class.md)'un genel örneğidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

`Error`çağırmak için, nesnenizin `ISupportErrorInfo Interface` arabirimini uygulaması gerekir.

*HRes* parametresi sıfır değilse `Error`, *hRes*'nin değerini döndürür. *HRes* sıfırsa, `Error` ilk dört sürümü DISP_E_EXCEPTION döndürür. Son iki sürüm MAKE_HRESULT makro sonucunu döndürür **(1, FACILITY_ITF,** *NID* **)** .

##  <a name="getobjectclsid"></a>CComCoClass:: GetObjectCLSID

Nesnenin CLSID 'sini almak için tutarlı bir yol sağlar.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin sınıf tanımlayıcısı.

##  <a name="getobjectdescription"></a>CComCoClass:: GetObjectDescription

Bu statik işlev, sınıf nesnenizin metin açıklamasını alır.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Dönüş Değeri

Sınıf nesnesinin açıklaması.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama NULL değerini döndürür. Bu yöntemi [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) makroyla geçersiz kılabilirsiniz. Örnek:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription`, `IComponentRegistrar::GetComponents`tarafından çağrılır. `IComponentRegistrar`, bir DLL 'deki tek tek bileşenleri kaydetmenize ve kaydını kaldırmanıza olanak tanıyan bir Otomasyon arabirimidir. ATL Proje sihirbazıyla bir bileşen kaydedici nesnesi oluşturduğunuzda, sihirbaz `IComponentRegistrar` arabirimini otomatik olarak uygular. `IComponentRegistrar` genellikle Microsoft Transaction Server tarafından kullanılır.

ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
