---
title: CComPtrBase sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 740920225fc513a869b4a92344f87004831e4768
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298624"
---
# <a name="ccomptrbase-class"></a>CComPtrBase sınıfı

Bu sınıf, COM tabanlı bellek yordamlarını kullanan akıllı işaretçi sınıfları için temel sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Akıllı işaretçinin başvurduğu nesne türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Genel Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CComPtrBase:: Advise](#advise)|`CComPtrBase`bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturmak için bu yöntemi çağırın.|
|[CComPtrBase:: Attach](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CComPtrBase:: CoCreateInstance](#cocreateinstance)|Belirtilen sınıf KIMLIĞI veya program KIMLIĞIYLE ilişkili sınıfın bir nesnesini oluşturmak için bu yöntemi çağırın.|
|[CComPtrBase:: CopyTo](#copyto)|`CComPtrBase` işaretçisini başka bir işaretçi değişkenine kopyalamak için bu yöntemi çağırın.|
|[CComPtrBase::D etach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CComPtrBase:: ısequalobject](#isequalobject)|Belirtilen `IUnknown` `CComPtrBase` nesnesiyle ilişkili aynı nesneyi işaret edip ettiğini denetlemek için bu yöntemi çağırın.|
|[CComPtrBase:: QueryInterface](#queryinterface)|Belirtilen arabirime bir işaretçi döndürmek için bu yöntemi çağırın.|
|[CComPtrBase:: Release](#release)|Arabirimi yayınlamak için bu yöntemi çağırın.|
|[CComPtrBase:: SetSite](#setsite)|`CComPtrBase` nesnesinin sitesini üst nesnenin `IUnknown` ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Genel İşleçler

|Name|Açıklama|
|----------|-----------------|
|[CComPtrBase:: operator T *](#operator_t_star)|Atama işleci.|
|[CComPtrBase:: işleci!](#operator_not)|NOT işleci.|
|[CComPtrBase:: operator &](#operator_amp)|& İşleci.|
|[CComPtrBase:: operator *](#operator_star)|\* işleci.|
|[CComPtrBase:: operator <](#ccomptrbase__operator lt)|Küçüktür işleci.|
|[CComPtrBase:: operator = =](#operator_eq_eq)|Eşitlik işleci.|
|[CComPtrBase:: operator->](#operator_ptr)|Üye işaretçisi operatörü.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[CComPtrBase::p](#p)|İşaretçi verisi üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [CComQIPtr](../../atl/reference/ccomqiptr-class.md) ve [CCOMPTR](../../atl/reference/ccomptr-class.md)gibi com bellek yönetimi yordamlarını kullanan diğer akıllı işaretçiler için temel sağlar. Türetilmiş sınıflar kendi oluşturucularını ve işleçlerini ekler, ancak `CComPtrBase`tarafından sunulan yöntemleri kullanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

##  <a name="advise"></a>CComPtrBase:: Advise

`CComPtrBase`bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturmak için bu yöntemi çağırın.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
İstemcinin `IUnknown`bir işaretçisi.

*'si*<br/>
Bağlantı noktasının GUID 'SI. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimle aynıdır.

*PDW*<br/>
Bağlantıyı benzersiz bir şekilde tanımlayan tanımlama bilgisine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [AtlAdvise](connection-point-global-functions.md#atladvise) .

##  <a name="attach"></a>CComPtrBase:: Attach

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parametreler

*P2*<br/>
`CComPtrBase` nesne Bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

`Attach` var olan [CComPtrBase::p](#p) üye değişkeninde [CComPtrBase:: Release](#release) öğesini çağırır ve sonra da `CComPtrBase::p`*P2* atar. Bir `CComPtrBase` nesnesi bir işaretçinin sahipliğini aldığında, nesnedeki başvuru sayısı 0 ' a gittiğinde işaretçiyi ve ayrılan tüm verileri silecek işaretçi üzerinde `Release` otomatik olarak çağırır.

##  <a name="dtor"></a>CComPtrBase:: ~ CComPtrBase

Yok edicisi.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

`CComPtrBase`tarafından işaret edilen arabirimi yayınlar.

##  <a name="cocreateinstance"></a>CComPtrBase:: CoCreateInstance

Belirtilen sınıf KIMLIĞI veya program KIMLIĞIYLE ilişkili sınıfın bir nesnesini oluşturmak için bu yöntemi çağırın.

```
HRESULT CoCreateInstance(
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>Parametreler

*Szprogıd*<br/>
CLSID 'yi kurtarmak için kullanılan bir ProgID 'nin işaretçisi.

*pUnkOuter*<br/>
NULL ise, nesnenin bir toplama kapsamında oluşturulmadığını gösterir. NULL olmayan ise, toplama nesnesinin `IUnknown` arabirimine yönelik bir işaretçidir (denetim `IUnknown`).

*dwClsContext*<br/>
Yeni oluşturulan nesneyi yöneten kodun çalışacağı bağlam.

*rclsıd*<br/>
Nesneyi oluşturmak için kullanılacak veriler ve kodla ilişkili CLSID.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı veya REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING veya E_NOINTERFACE hata durumunda döndürür. Bu hataların açıklaması için bkz. [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) and [Clsidfromprogıd](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) .

### <a name="remarks"></a>Açıklamalar

Yöntemin ilk formu çağrılırsa, CLSID 'yi kurtarmak için [Clsidfromprogıd](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) kullanılır. Her iki form da [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)öğesini çağırır.

Hata ayıklama yapılarında, [CComPtrBase::P](#p) null değerine eşit değilse bir onaylama hatası oluşur.

##  <a name="copyto"></a>CComPtrBase:: CopyTo

`CComPtrBase` işaretçisini başka bir işaretçi değişkenine kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parametreler

*ppT*<br/>
`CComPtrBase` işaretçisini alacak değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda E_POINTER başarılı S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

`CComPtrBase` işaretçisini *PPT*'ye kopyalar. [CComPtrBase::p](#p) üye değişkeninde başvuru sayısı artırılır.

*PPT* , null DEĞERINE eşitse HRESULT döndürülür. Hata ayıklama yapılarında, *PPT* null değerine eşitse bir onaylama hatası oluşur.

##  <a name="detach"></a>CComPtrBase::D etach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CComPtrBase::p](#p) veri ÜYESI değişkenini null olarak ayarlar ve işaretçinin bir kopyasını döndürür.

##  <a name="isequalobject"></a>CComPtrBase:: ısequalobject

Belirtilen `IUnknown` `CComPtrBase` nesnesiyle ilişkili aynı nesneyi işaret edip ettiğini denetlemek için bu yöntemi çağırın.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parametreler

*pOther*<br/>
Karşılaştırılacak `IUnknown *`.

### <a name="return-value"></a>Dönüş Değeri

Nesneler aynıysa true, değilse false döndürür.

##  <a name="operator_not"></a>CComPtrBase:: işleci!

NOT işleci.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComHeapPtr` işaretçi NULL değerine eşitse true, değilse false döndürür.

##  <a name="operator_amp"></a>CComPtrBase:: operator &amp;

& İşleci.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComPtrBase` nesnesi tarafından işaret edilen nesnenin adresini döndürür.

##  <a name="operator_star"></a>CComPtrBase:: operator \*

\* işleci.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComPtrBase](#p)'in değerini döndürür::p; diğer bir deyişle, `CComPtrBase` nesnesi tarafından başvurulan nesneye yönelik bir işaretçidir.

Hata ayıklama derlemelerse, [CComPtrBase::P](#p) null değerine eşit değilse bir onaylama hatası oluşur.

##  <a name="operator_eq_eq"></a>CComPtrBase:: operator = =

Eşitlik işleci.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
Bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CComPtrBase` ve *PT* aynı nesneye işaret gösteriyorsa true, aksi takdirde false döndürür.

##  <a name="operator_ptr"></a>CComPtrBase:: operator-&gt;

Üye işaretçisi işleci.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComPtrBase::p](#p) Data üye değişkeninin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`CComPtrBase` nesnesi tarafından işaret edilen bir sınıftaki yöntemi çağırmak için bu işleci kullanın. Hata ayıklama yapılarında, `CComPtrBase` veri üyesi NULL değerini gösteriyorsa bir onaylama hatası oluşur.

##  <a name="operator_lt"></a>CComPtrBase:: operator &lt;

Küçüktür işleci.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
Bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesne tarafından yönetilen işaretçi karşılaştırılan işaretçisinden küçükse true döndürür.

##  <a name="operator_t_star"></a>CComPtrBase:: operator T\*

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

##  <a name="p"></a>CComPtrBase::p

İşaretçi verisi üye değişkeni.

```
T* p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni işaretçi bilgisini tutar.

##  <a name="queryinterface"></a>CComPtrBase:: QueryInterface

Belirtilen arabirime bir işaretçi döndürmek için bu yöntemi çağırın.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*Q*<br/>
Arabirim işaretçisi gerekli olan nesne türü.

*Sy*<br/>
İstenen arabirim işaretçisini alan çıkış değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya hatalı E_NOINTERFACE S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))' i çağırır.

Hata ayıklama yapılarında, *PP* null değerine eşit değilse bir onaylama hatası oluşur.

##  <a name="release"></a>CComPtrBase:: Release

Arabirimi yayınlamak için bu yöntemi çağırın.

```
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Arabirim serbest bırakılır ve [CComPtrBase::P](#p) null olarak ayarlanır.

##  <a name="setsite"></a>CComPtrBase:: SetSite

`CComPtrBase` nesnesinin sitesini üst nesnenin `IUnknown` ayarlamak için bu yöntemi çağırın.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parametreler

*punkParent*<br/>
Üst öğenin `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite)'ı çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
