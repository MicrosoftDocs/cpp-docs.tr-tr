---
title: CComPtrBase Class
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
ms.openlocfilehash: 5bb599b88671447e219421efacac7a2d8a5f7b06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246237"
---
# <a name="ccomptrbase-class"></a>CComPtrBase Class

Bu sınıf, COM tabanlı bellek yordamları kullanarak akıllı işaretçi sınıflar için temel sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Akıllı işaretçi tarafından başvurulabilmesi için nesne türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase::Advise](#advise)|Arasında bir bağlantı oluşturmak için bu yöntemi çağırın `CComPtrBase`ait bağlantı noktası ve istemcinin havuzu.|
|[CComPtrBase::Attach](#attach)|Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Belirtilen sınıf kimliği veya Program Kimliği ile ilişkili sınıfın bir nesnesi oluşturmak için bu yöntemi çağırın|
|[CComPtrBase::CopyTo](#copyto)|Kopyalamak için bu yöntemi çağırın `CComPtrBase` başka bir işaretçi değişkeninin işaretçisi.|
|[CComPtrBase::Detach](#detach)|Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.|
|[CComPtrBase::IsEqualObject](#isequalobject)|Olmadığını denetlemek için bu yöntemi çağıran belirtilen `IUnknown` ilişkili aynı nesneyi işaret `CComPtrBase` nesne.|
|[CComPtrBase::QueryInterface](#queryinterface)|Belirtilen bir arabirim bir işaretçiyi döndürmek için bu yöntemi çağırın.|
|[CComPtrBase::Release](#release)|Arabirimi serbest bırakmak için bu yöntemi çağırın.|
|[CComPtrBase::SetSite](#setsite)|Sitesini ayarlamak için bu yöntemi çağırın `CComPtrBase` nesnesini `IUnknown` üst nesnenin.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase::operator T *](#operator_t_star)|Atama işleci.|
|[CComPtrBase::operator!](#operator_not)|NOT işleci.|
|[CComPtrBase::operator &](#operator_amp)|& İşleci.|
|[CComPtrBase::operator *](#operator_star)|\* işleci.|
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|Daha az-işleci.|
|[CComPtrBase::operator ==](#operator_eq_eq)|Eşitlik işleci.|
|[CComPtrBase::operator ->](#operator_ptr)|İşaretçi-üye işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComPtrBase::p](#p)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, COM bellek yönetimi rutinleri için aşağıdaki gibi kullanan diğer akıllı işaretçiler için temelini [CComQIPtr](../../atl/reference/ccomqiptr-class.md) ve [CComPtr](../../atl/reference/ccomptr-class.md). Türetilmiş sınıfları kendi oluşturucular ve işleçleri ekleyin, ancak tarafından sağlanan yöntemleri kullanan `CComPtrBase`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcomcli.h

##  <a name="advise"></a>  CComPtrBase::Advise

Arasında bir bağlantı oluşturmak için bu yöntemi çağırın `CComPtrBase`ait bağlantı noktası ve istemcinin havuzu.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parametreler

*pUnk*<br/>
İstemcinin bir işaretçiye `IUnknown`.

*IID*<br/>
Bağlantı noktası GUİD'si. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.

*PDW*<br/>
Bağlantı benzersiz olarak tanıtan bir tanımlama bilgisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [AtlAdvise](connection-point-global-functions.md#atladvise) daha fazla bilgi için.

##  <a name="attach"></a>  CComPtrBase::Attach

Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parametreler

*P2*<br/>
`CComPtrBase` Nesne, işaretçi sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

`Attach` çağrıları [CComPtrBase::Release](#release) mevcut [CComPtrBase::p](#p) üye değişkeni ve atar *p2* için `CComPtrBase::p`. Olduğunda bir `CComPtrBase` nesne, işaretçi sahipliğini alır, otomatik olarak çağıracak `Release` nesnede başvuru sayısını 0 olursa, işaretçi ve silecek işaretçide veri ayrılmış.

##  <a name="dtor"></a>  CComPtrBase:: ~ CComPtrBase

Yıkıcı.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

İşaret ettiği arabirimini yayımlar `CComPtrBase`.

##  <a name="cocreateinstance"></a>  CComPtrBase::CoCreateInstance

Belirtilen sınıf kimliği veya Program Kimliği ile ilişkili sınıfın bir nesnesi oluşturmak için bu yöntemi çağırın

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
ProgID CLSID'si kurtarmak için kullanılan, işaretçi.

*pUnkOuter*<br/>
NULL ise, nesne bir toplamanın parçası oluşturulduğunu değil gösterir. NULL olmayan, toplam nesnenin bir işaretçi olup olmadığını `IUnknown` arabirimi (denetleme `IUnknown`).

*dwClsContext*<br/>
Yeni oluşturulan nesne yöneten kod çalıştırılacağı bağlamı.

*rclsid*<br/>
CLSID veri ve nesneyi oluşturmak için kullanılan kod ile ilişkili.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür, başarı veya REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING veya e_noınterface başarısız. Bkz: [CoCreateClassInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) ve [CLSIDFromProgID](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid) bu hataları açıklaması.

### <a name="remarks"></a>Açıklamalar

İlk formu yöntemi çağrılırsa, [CLSIDFromProgID](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid) CLSID kurtarmak için kullanılır. Her iki biçimi'ı çağırın [CoCreateClassInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir [CComPtrBase::p](#p) NULL değerine eşit değil.

##  <a name="copyto"></a>  CComPtrBase::CopyTo

Kopyalamak için bu yöntemi çağırın `CComPtrBase` başka bir işaretçi değişkeninin işaretçisi.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parametreler

*ppT*<br/>
Alacak değişkenin adresi `CComPtrBase` işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı, başarısızlık durumunda e_poınter başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Kopya `CComPtrBase` işaretçisine *ppT*. Başvuru sayma [CComPtrBase::p](#p) üye değişkeni artırılır.

Bir hata HRESULT döndürülecek *ppT* NULL değerine eşittir. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *ppT* NULL değerine eşittir.

##  <a name="detach"></a>  CComPtrBase::Detach

Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyi bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi sahipliğini bırakır, ayarlar [CComPtrBase::p](#p) veri üyesi değişkeninin NULL ve işaretçi bir kopyasını döndürür.

##  <a name="isequalobject"></a>  CComPtrBase::IsEqualObject

Olmadığını denetlemek için bu yöntemi çağıran belirtilen `IUnknown` ilişkili aynı nesneyi işaret `CComPtrBase` nesne.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parametreler

*pOther*<br/>
`IUnknown *` Karşılaştırmak için.

### <a name="return-value"></a>Dönüş Değeri

Nesneleri Aksi takdirde aynı, false ise true döndürür.

##  <a name="operator_not"></a>  CComPtrBase::operator!

NOT işleci.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Gerekirse true döndürür `CComHeapPtr` , NULL işaretçi eşittir false Aksi takdirde.

##  <a name="operator_amp"></a>  CComPtrBase::operator &amp;

& İşleci.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından işaret edilen nesnenin adresini döndürür `CComPtrBase` nesne.

##  <a name="operator_star"></a>  CComPtrBase::operator \*

\* işleci.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Değerini döndürür [CComPtrBase::p](#p); diğer bir deyişle, bir işaretçi tarafından başvurulan nesne `CComPtrBase` nesne.

Hata ayıklama derlemeleri, onaylama işlemi hatası olursa meydana gelir [CComPtrBase::p](#p) NULL değerine eşit değil.

##  <a name="operator_eq_eq"></a>  CComPtrBase::operator ==

Eşitlik işleci.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Bir nesneye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse true döndürür `CComPtrBase` ve *pT* aynı nesneye, aksi takdirde false gelin.

##  <a name="operator_ptr"></a>  CComPtrBase::operator-&gt;

İşaretçi-üye işleci.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Değerini döndürür [CComPtrBase::p](#p) veri üye değişkeni.

### <a name="remarks"></a>Açıklamalar

İşaret ettiği bir sınıftaki bir yöntemi çağırmak için bu işleci kullanın `CComPtrBase` nesne. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `CComPtrBase` veri üyesi NULL olarak işaret eder.

##  <a name="operator_lt"></a>  CComPtrBase::operator &lt;

Daha az-işleci.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Bir nesneye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi geçerli nesne tarafından yönetiliyorsa true değerini döndürür, bu karşılaştırılıyor işaretçi küçüktür.

##  <a name="operator_t_star"></a>  CComPtrBase::operator T\*

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türü bir işaretçi döndürür.

##  <a name="p"></a>  CComPtrBase::p

İşaretçi veri üye değişkeni.

```
T* p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni, işaretçi bilgileri tutar.

##  <a name="queryinterface"></a>  CComPtrBase::QueryInterface

Belirtilen bir arabirim bir işaretçiyi döndürmek için bu yöntemi çağırın.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*Q*<br/>
Nesne türü, arabirim işaretçisi gereklidir.

*PP*<br/>
Adresi çıkış değişkeninin istenen arabirim işaretçisi alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür başarı veya e_noınterface başarısız.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [IUnknown::QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pp* NULL değerine eşit değil.

##  <a name="release"></a>  CComPtrBase::Release

Arabirimi serbest bırakmak için bu yöntemi çağırın.

```
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Arabirimi yayımladı, ve [CComPtrBase::p](#p) NULL olarak ayarlandı.

##  <a name="setsite"></a>  CComPtrBase::SetSite

Sitesini ayarlamak için bu yöntemi çağırın `CComPtrBase` nesnesini `IUnknown` üst nesnenin.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parametreler

*punkParent*<br/>
Bir işaretçi `IUnknown` üst arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
