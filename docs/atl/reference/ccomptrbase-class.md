---
title: CComPtrBase Sınıfı
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
ms.openlocfilehash: 9c62cc912b3fea3ea68390882bdda37cbfb25a7e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747766"
---
# <a name="ccomptrbase-class"></a>CComPtrBase Sınıfı

Bu sınıf, COM tabanlı bellek yordamları kullanarak akıllı işaretçi sınıfları için bir temel sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Akıllı işaretçi tarafından başvurulacak nesne türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComPtrBase::~CComPtrBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComPtrBase::Tavsiye](#advise)|'Bağlantı noktası ve istemcinin `CComPtrBase`lavabosu arasında bir bağlantı oluşturmak için bu yöntemi arayın.|
|[CComPtrBase::Ekle](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Belirtilen sınıf kimliği veya Program Kimliği ile ilişkili sınıfın bir nesnesini oluşturmak için bu yöntemi çağırın.|
|[CComPtrBase::CopyTo](#copyto)|İşaretçiyi başka `CComPtrBase` bir işaretçi değişkenine kopyalamak için bu yöntemi çağırın.|
|[CComPtrBase::Detach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CComPtrBase::Eşit Nesne](#isequalobject)|Belirtilen `IUnknown` `CComPtrBase` noktalarınesneyle ilişkili aynı nesneye işaret edip etmeyin denetlemek için bu yöntemi çağırın.|
|[CComPtrBase::QueryInterface](#queryinterface)|İşaretçiyi belirli bir arabirime döndürmek için bu yöntemi çağırın.|
|[CComPtrBase::Yayın](#release)|Arabirimi serbest bırakmak için bu yöntemi arayın.|
|[CComPtrBase::SetSite](#setsite)|`CComPtrBase` Nesnenin sitesini ana nesnenin nesnesine `IUnknown` ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComPtrBase::operatör T*](#operator_t_star)|Döküm operatörü.|
|[CComPtrBase::operatör !](#operator_not)|NOT işleci.|
|[CComPtrBase::operatör &](#operator_amp)|& operatörü.|
|[CComPtrBase::operatör *](#operator_star)|\* işleci.|
|[CComPtrBase::operatör <](#ccomptrbase__operator lt)|Operatörden daha az.|
|[CComPtrBase::operatör ==](#operator_eq_eq)|Eşitlik operatörü.|
|[CComPtrBase::operatör ->](#operator_ptr)|Üye işaretçisi işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComPtrBase::p](#p)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [CComQIPtr](../../atl/reference/ccomqiptr-class.md) ve [CComPtr](../../atl/reference/ccomptr-class.md)gibi COM bellek yönetimi yordamları kullanan diğer akıllı işaretçiler için temel sağlar. Türetilen sınıflar kendi oluşturucularını ve işleçlerini ekler, `CComPtrBase`ancak '.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomcli.h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a>CComPtrBase::Tavsiye

'Bağlantı noktası ve istemcinin `CComPtrBase`lavabosu arasında bir bağlantı oluşturmak için bu yöntemi arayın.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
İstemci için bir `IUnknown`işaretçi .

*ııd*<br/>
Bağlantı noktasının GUID'i. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirim aynıdır.

*Pdw*<br/>
Bağlantıyı benzersiz olarak tanımlayan çerez için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [AtlAdvise'a](connection-point-global-functions.md#atladvise) bakın.

## <a name="ccomptrbaseattach"></a><a name="attach"></a>CComPtrBase::Ekle

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parametreler

*p2*<br/>
Nesne `CComPtrBase` bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

`Attach`[CComPtrBase çağırır::Mevcut](#release) [CComPtrBase::p](#p) üye değişkenini serbest bırakın `CComPtrBase::p`ve sonra *p2'yi* . Bir `CComPtrBase` nesne bir işaretçinin sahipliğini aldığında, nesneüzerindeki başvuru sayısı 0'a giderse işaretçiyi ve ayrılan verileri silecek olan işaretçiyi otomatik olarak çağırır. `Release`

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a>CComPtrBase::~CComPtrBase

Yıkıcı.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Tarafından işaret edilen `CComPtrBase`arabirimi serbest bırakır.

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a>CComPtrBase::CoCreateInstance

Belirtilen sınıf kimliği veya Program Kimliği ile ilişkili sınıfın bir nesnesini oluşturmak için bu yöntemi çağırın.

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

*szProgID*<br/>
CLSID'yi kurtarmak için kullanılan progID işaretçisi.

*pUnkOuter*<br/>
NULL ise, nesnenin bir agreganın parçası olarak oluşturulmadığını gösterir. NULL yoksa, toplam nesnenin `IUnknown` arabirimine (denetleme) işaretçidir. `IUnknown`

*dwClsBağlam*<br/>
Yeni oluşturulan nesneyi yöneten kodun çalışacağı bağlam.

*rclsid*<br/>
CLSID, nesneyi oluşturmak için kullanılacak veri ve kodla ilişkilidir.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING veya başarısızlık E_NOINTERFACE S_OK verir. Bu hataların açıklaması için [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) ve [CLSIDFromProgID'e](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) bakın.

### <a name="remarks"></a>Açıklamalar

Yöntemin ilk formu çağrılırsa, CLSID kurtarmak için [CLSIDFromProgID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) kullanılır. Her iki form da [cocreateclassinstance'ı arayarak.](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)

Hata ayıklama oluştururda, [CComPtrBase::p](#p) NULL'a eşit değilse bir tasnif hatası oluşur.

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a>CComPtrBase::CopyTo

İşaretçiyi başka `CComPtrBase` bir işaretçi değişkenine kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parametreler

*Ppt*<br/>
İşaretçiyi alacak değişkenin `CComPtrBase` adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK, başarısızlık E_POINTER döndürür.

### <a name="remarks"></a>Açıklamalar

İşaretçiyi `CComPtrBase` *ppT'ye kopyalar.* [CComPtrBase::p](#p) üye değişkenindeki başvuru sayısı artmıştır.

*ppT* NULL'a eşitse bir hata HRESULT döndürülür. Hata ayıklama oluştururda, *ppT* NULL'a eşitse bir tasnif hatası oluşur.

## <a name="ccomptrbasedetach"></a><a name="detach"></a>CComPtrBase::Detach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CComPtrBase::p](#p) veri üye değişkenini NULL olarak ayarlar ve işaretçinin bir kopyasını döndürür.

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a>CComPtrBase::Eşit Nesne

Belirtilen `IUnknown` `CComPtrBase` noktalarınesneyle ilişkili aynı nesneye işaret edip etmeyin denetlemek için bu yöntemi çağırın.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parametreler

*pDiğer*<br/>
Karşılaştırmak `IUnknown *` için.

### <a name="return-value"></a>Dönüş Değeri

Nesneler aynıysa doğru döndürür, aksi takdirde yanlış.

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a>CComPtrBase::operatör !

NOT işleci.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi NULL'a eşitse `CComHeapPtr` doğru, aksi takdirde yanlış döndürür.

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a>CComPtrBase::operatör&amp;

& operatörü.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComPtrBase` Nesne tarafından işaret edilen nesnenin adresini döndürür.

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a>CComPtrBase::operatör\*

\* işleci.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComPtrBase değerini verir::p;](#p) diğer bir de, `CComPtrBase` nesne tarafından başvurulan nesneye işaretçi.

Hata ayıklama oluşturursa, [CComPtrBase::p](#p) NULL'a eşit değilse bir tasnif hatası oluşur.

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a>CComPtrBase::operatör ==

Eşitlik operatörü.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Eğer `CComPtrBase` doğru döndürür ve *pT* aynı nesneye işaret ederse, aksi takdirde yanlış.

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a>CComPtrBase::operatör -&gt;

İşaretçiden üyeye işleç.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComPtrBase::p](#p) veri üyesi değişkeninin değerini verir.

### <a name="remarks"></a>Açıklamalar

`CComPtrBase` Nesne tarafından işaret edilen bir sınıftabir yöntem çağırmak için bu işleci kullanın. Hata ayıklama oluştururda, `CComPtrBase` veri üyesi NULL'u işaret ederse bir tasnif hatası oluşur.

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a>CComPtrBase::operatör&lt;

Operatörden daha az.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesne tarafından yönetilen işaretçi, karşılaştırıldığı işaretçiden daha azsa doğru döndürür.

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a>CComPtrBase::operatör T\*

Döküm operatörü.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

## <a name="ccomptrbasep"></a><a name="p"></a>CComPtrBase::p

İşaretçi veri üye değişkeni.

```
T* p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişken işaretçi bilgilerini tutar.

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a>CComPtrBase::QueryInterface

İşaretçiyi belirli bir arabirime döndürmek için bu yöntemi çağırın.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*S*<br/>
Arabirim işaretçisi gereken nesne türü.

*S*<br/>
İstenen arabirim işaretçisini alan çıktı değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya başarısızlık E_NOINTERFACE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu [yöntemi IUnknown çağırır::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)).

Hata ayıklama oluşturur, *pp* NULL eşit değilse bir iddia hatası oluşur.

## <a name="ccomptrbaserelease"></a><a name="release"></a>CComPtrBase::Yayın

Arabirimi serbest bırakmak için bu yöntemi arayın.

```cpp
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Arabirim serbest bırakılır ve [CComPtrBase::p](#p) NULL olarak ayarlanır.

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a>CComPtrBase::SetSite

`CComPtrBase` Nesnenin sitesini ana nesnenin nesnesine `IUnknown` ayarlamak için bu yöntemi çağırın.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parametreler

*punkEbeveyn*<br/>
Üst arabirimine `IUnknown` bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu [yöntema AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite)diyor.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
