---
description: 'Daha fazla bilgi edinin: CComPtrBase sınıfı'
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
ms.openlocfilehash: 34f197904775bc15366f412e629ef81b26dde74e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142395"
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

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase:: Advise](#advise)|Bağlantı noktası ve istemcinin havuzu arasında bağlantı oluşturmak için bu yöntemi çağırın `CComPtrBase` .|
|[CComPtrBase:: Attach](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CComPtrBase:: CoCreateInstance](#cocreateinstance)|Belirtilen sınıf KIMLIĞI veya program KIMLIĞIYLE ilişkili sınıfın bir nesnesini oluşturmak için bu yöntemi çağırın.|
|[CComPtrBase:: CopyTo](#copyto)|`CComPtrBase`İşaretçiyi başka bir işaretçi değişkenine kopyalamak için bu yöntemi çağırın.|
|[CComPtrBase::D etach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CComPtrBase:: ısequalobject](#isequalobject)|Belirtilen nesnenin `IUnknown` nesneyle ilişkili aynı nesneye işaret edip ettiğini denetlemek için bu yöntemi çağırın `CComPtrBase` .|
|[CComPtrBase:: QueryInterface](#queryinterface)|Belirtilen arabirime bir işaretçi döndürmek için bu yöntemi çağırın.|
|[CComPtrBase:: Release](#release)|Arabirimi yayınlamak için bu yöntemi çağırın.|
|[CComPtrBase:: SetSite](#setsite)|`CComPtrBase`Nesnenin sitesini üst nesnenin öğesine ayarlamak için bu yöntemi çağırın `IUnknown` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase:: operator T *](#operator_t_star)|Atama işleci.|
|[CComPtrBase:: işleci!](#operator_not)|NOT işleci.|
|[CComPtrBase:: operator &](#operator_amp)|& işleci.|
|[CComPtrBase:: operator *](#operator_star)|\* işleci.|
|[CComPtrBase:: operator <](#ccomptrbase__operator lt)|Küçüktür işleci.|
|[CComPtrBase:: operator = =](#operator_eq_eq)|Eşitlik işleci.|
|[CComPtrBase:: operator->](#operator_ptr)|Üye işaretçisi operatörü.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase::p](#p)|İşaretçi verisi üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [CComQIPtr](../../atl/reference/ccomqiptr-class.md) ve [CCOMPTR](../../atl/reference/ccomptr-class.md)gibi com bellek yönetimi yordamlarını kullanan diğer akıllı işaretçiler için temel sağlar. Türetilmiş sınıflar kendi oluşturucularını ve işleçlerini ekler, ancak tarafından sunulan yöntemleri kullanır `CComPtrBase` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a> CComPtrBase:: Advise

Bağlantı noktası ve istemcinin havuzu arasında bağlantı oluşturmak için bu yöntemi çağırın `CComPtrBase` .

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
İstemci için bir işaretçi `IUnknown` .

*'si*<br/>
Bağlantı noktasının GUID 'SI. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimle aynıdır.

*PDW*<br/>
Bağlantıyı benzersiz bir şekilde tanımlayan tanımlama bilgisine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [AtlAdvise](connection-point-global-functions.md#atladvise) .

## <a name="ccomptrbaseattach"></a><a name="attach"></a> CComPtrBase:: Attach

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parametreler

*P2*<br/>
`CComPtrBase`Nesne Bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

`Attach`var olan [CComPtrBase::p](#p) üye değişkeninde [CComPtrBase:: Release](#release) öğesini çağırır ve sonra *P2* öğesine atar `CComPtrBase::p` . Bir `CComPtrBase` nesne bir işaretçinin sahipliğini aldığında, `Release` nesne üzerindeki başvuru sayısı 0 ' a gittiğinde işaretçiyi ve ayrılan verileri silecek olan işaretçiye otomatik olarak çağrı yapılır.

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a> CComPtrBase:: ~ CComPtrBase

Yok edicisi.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Tarafından işaret edilen arabirimi yayınlar `CComPtrBase` .

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a> CComPtrBase:: CoCreateInstance

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
NULL ise, nesnenin bir toplama kapsamında oluşturulmadığını gösterir. NULL olmayan ise, toplama nesnesinin arabirimine yönelik bir işaretçidir `IUnknown` (Denetim `IUnknown` ).

*dwClsContext*<br/>
Yeni oluşturulan nesneyi yöneten kodun çalışacağı bağlam.

*rclsıd*<br/>
Nesneyi oluşturmak için kullanılacak veriler ve kodla ilişkili CLSID.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı veya REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING veya E_NOINTERFACE hata durumunda döndürür. Bu hataların açıklaması için bkz. [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) and [Clsidfromprogıd](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) .

### <a name="remarks"></a>Açıklamalar

Yöntemin ilk formu çağrılırsa, CLSID 'yi kurtarmak için [Clsidfromprogıd](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) kullanılır. Her iki form da [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)öğesini çağırır.

Hata ayıklama yapılarında, [CComPtrBase::P](#p) null değerine eşit değilse bir onaylama hatası oluşur.

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a> CComPtrBase:: CopyTo

`CComPtrBase`İşaretçiyi başka bir işaretçi değişkenine kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parametreler

*ppT*<br/>
İşaretçiyi alacak değişkenin adresi `CComPtrBase` .

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda E_POINTER başarılı S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

`CComPtrBase`Işaretçiyi *PPT*'ye kopyalar. [CComPtrBase::p](#p) üye değişkeninde başvuru sayısı artırılır.

*PPT* , null DEĞERINE eşitse HRESULT döndürülür. Hata ayıklama yapılarında, *PPT* null değerine eşitse bir onaylama hatası oluşur.

## <a name="ccomptrbasedetach"></a><a name="detach"></a> CComPtrBase::D etach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CComPtrBase::p](#p) veri ÜYESI değişkenini null olarak ayarlar ve işaretçinin bir kopyasını döndürür.

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a> CComPtrBase:: ısequalobject

Belirtilen nesnenin `IUnknown` nesneyle ilişkili aynı nesneye işaret edip ettiğini denetlemek için bu yöntemi çağırın `CComPtrBase` .

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parametreler

*pOther*<br/>
`IUnknown *`Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Nesneler aynıysa true, değilse false döndürür.

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a> CComPtrBase:: işleci!

NOT işleci.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComHeapPtr`IŞARETÇI null değerine eşitse true, değilse false döndürür.

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a> CComPtrBase:: işleci &amp;

& işleci.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne tarafından işaret edilen nesnenin adresini döndürür `CComPtrBase` .

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a> CComPtrBase:: işleci \*

\* işleci.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComPtrBase](#p)'in değerini döndürür::p; diğer bir deyişle, nesne tarafından başvurulan nesneye yönelik bir işaretçidir `CComPtrBase` .

Hata ayıklama derlemelerse, [CComPtrBase::P](#p) null değerine eşit değilse bir onaylama hatası oluşur.

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a> CComPtrBase:: operator = =

Eşitlik işleci.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
Bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CComPtrBase`Ve *PT* aynı nesneye işaret gösteriyorsa true, değilse false döndürür.

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a> CComPtrBase:: operator-&gt;

Üye işaretçisi işleci.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComPtrBase::p](#p) Data üye değişkeninin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret edilen bir sınıftaki yöntemi çağırmak için bu işleci kullanın `CComPtrBase` . Hata ayıklama yapılarında, `CComPtrBase` veri üyesi NULL değerini gösteriyorsa bir onaylama hatası oluşur.

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a> CComPtrBase:: işleci &lt;

Küçüktür işleci.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
Bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesne tarafından yönetilen işaretçi karşılaştırılan işaretçisinden küçükse true döndürür.

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a> CComPtrBase:: operator T\*

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

## <a name="ccomptrbasep"></a><a name="p"></a> CComPtrBase::p

İşaretçi verisi üye değişkeni.

```
T* p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni işaretçi bilgisini tutar.

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a> CComPtrBase:: QueryInterface

Belirtilen arabirime bir işaretçi döndürmek için bu yöntemi çağırın.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*Ç*<br/>
Arabirim işaretçisi gerekli olan nesne türü.

*Sy*<br/>
İstenen arabirim işaretçisini alan çıkış değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya hatalı E_NOINTERFACE S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))' i çağırır.

Hata ayıklama yapılarında, *PP* null değerine eşit değilse bir onaylama hatası oluşur.

## <a name="ccomptrbaserelease"></a><a name="release"></a> CComPtrBase:: Release

Arabirimi yayınlamak için bu yöntemi çağırın.

```cpp
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Arabirim serbest bırakılır ve [CComPtrBase::P](#p) null olarak ayarlanır.

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a> CComPtrBase:: SetSite

`CComPtrBase`Nesnenin sitesini üst nesnenin öğesine ayarlamak için bu yöntemi çağırın `IUnknown` .

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parametreler

*punkParent*<br/>
Üst öğenin arabirimine yönelik bir işaretçi `IUnknown` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite)'ı çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
