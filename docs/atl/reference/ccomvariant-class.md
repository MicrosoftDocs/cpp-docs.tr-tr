---
title: CComVariant sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: 6a6ad49533028dbcb8c45b63c55a51090533137e
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522499"
---
# <a name="ccomvariant-class"></a>CComVariant sınıfı

Bu sınıf, depolanan veri türünü gösteren bir üye sağlama VARIANT türü sarmalar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|Oluşturucu.|
|[CComVariant:: ~ CComVariant](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComVariant::Attach](#attach)|Bir değişken için ekler `CComVariant` nesne.|
|[CComVariant::ChangeType](#changetype)|Dönüştürür `CComVariant` nesnesine yeni bir tür.|
|[CComVariant::Clear](#clear)|Temizler `CComVariant` nesne.|
|[CComVariant::Copy](#copy)|Bir değişken için kopyalar `CComVariant` nesne.|
|[CComVariant::CopyTo](#copyto)|İçeriğini kopyalar `CComVariant` nesne.|
|[CComVariant::Detach](#detach)|Temel alınan DEĞİŞKENDEN ayırır `CComVariant` nesne.|
|[CComVariant::GetSize](#getsize)|İçeriğinin bayt cinsinden boyutunu döndürür `CComVariant` nesne.|
|[CComVariant::ReadFromStream](#readfromstream)|Bir değişken bir akışından yükler.|
|[CComVariant::SetByRef](#setbyref)|Başlatır `CComVariant` nesne ve ayarlar `vt` VT_BYREF üye.|
|[CComVariant::WriteToStream](#writetostream)|Temel alınan değişken bir akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|||
|-|-|
|[CComVariant::operator <](#operator_lt)|Belirtir olup olmadığını `CComVariant` nesne belirtilen değişken azdır.|
|[CComVariant::operator >](#operator_gt)|Belirtir olup olmadığını `CComVariant` nesne, belirtilen değişken büyüktür.|
|[işleç! =](#operator_neq)|Belirtir olup olmadığını `CComVariant` nesne belirtilen değişken eşit değil.|
|[işleç =](#operator_eq)|Bir değer atar `CComVariant` nesne.|
|[işleç ==](#operator_eq_eq)|Belirtir olup olmadığını `CComVariant` nesne belirtilen değişken eşittir.|

## <a name="remarks"></a>Açıklamalar

`CComVariant` bir birleşim ve birleşimde depolanan verilerin türünü belirten bir üye oluşan değişken ve VARIANTARG türü sarmalar. Çeşitleri genellikle Otomasyon kullanılır.

`CComVariant` bir değişken kullanılabildiği yerlerde kullanılabilmesi için değişken türünden türetilir. Örneğin, V_VT makrosu türü ayıklamak için kullanabileceğiniz bir `CComVariant` veya erişebilirsiniz `vt` bir değişken ile yapabilecekleriniz doğrudan yalnızca üye.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcomcli.h

##  <a name="attach"></a>  CComVariant::Attach

Geçerli içeriği güvenli bir şekilde temizler `CComVariant` nesnesi, içeriğini kopyalar *pSrc* bu nesnede sonra değişken türünü ayarlar *pSrc* VT_EMPTY için.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
[in] İşaret [değişken](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) nesnesine eklenecek.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Tutulan verileri sahipliğini *pSrc* aktarılır `CComVariant` nesne.

##  <a name="ccomvariant"></a>  CComVariant::CComVariant

Her Oluşturucu güvenli olarak başlatılması işler `CComVariant` çağırarak `VariantInit` Win32 işlevini veya bir nesnenin değerine ve türüne göre geçirilen parametreler ayarlayarak.

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
[in] `CComVariant` Veya TÜREVLERİ başlatmak için kullanılan `CComVariant` nesne. Kaynak değişken içeriğini hedef dönüştürme olmadan kopyalanır.

*lpszSrc*<br/>
[in] Başlatmak için kullanılan karakter dizesi `CComVariant` nesne. Geniş (Unicode) karakter sıfır ile sonlandırılmış dize oluşturucu veya bir ANSI dizesine LPCSTR sürüme LPCOLESTR sürümüne geçirebilirsiniz. Her iki durumda da, bir Unicode kullanılarak ayrılmış BSTR dizeye dönüştürülür `SysAllocString`. Türünü `CComVariant` nesne VT_BSTR olacaktır.

*bSrc*<br/>
[in] **Bool** başlatmak için kullanılan `CComVariant` nesne. **Bool** depolanmadan önce bağımsız değişkeni için bir varıant_bool dönüştürülür. Türünü `CComVariant` nesne VT_BOOL olacaktır.

*nSrc*<br/>
[in] **İnt**, **bayt**, **kısa**, **uzun**, LONGLONG, ULONGLONG, **işaretsiz**, **işaretsiz uzun**, veya **işaretsiz int** başlatmak için kullanılan `CComVariant` nesne. Türünü `CComVariant` nesne olacak VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4, sırasıyla.

*vtSrc*<br/>
[in] Değişken türü. İlk parametre olduğunda **int**, geçerli türler: VT_I4 ve VT_INT. İlk parametre olduğunda **uzun**, geçerli türler: VT_I4 ve VT_ERROR. İlk parametre olduğunda **çift**, geçerli türler: VT_R8 ve VT_DATE. İlk parametre olduğunda **işaretsiz int**, geçerli türler: VT_UI4 ve VT_UINT.

*fltsrc &*<br/>
[in] **Float** başlatmak için kullanılan `CComVariant` nesne. Türünü `CComVariant` nesne VT_R4 olacaktır.

*dblsrc &*<br/>
[in] **Çift** başlatmak için kullanılan `CComVariant` nesne. Türünü `CComVariant` nesne VT_R8 olacaktır.

*cysrc &*<br/>
[in] `CY` Başlatmak için kullanılan `CComVariant` nesne. Türünü `CComVariant` nesne VT_CY olacaktır.

*pSrc*<br/>
[in] `IDispatch` Veya `IUnknown` işaretçi başlatmak için kullanılan `CComVariant` nesne. `AddRef` arabirim işaretçisi üzerinde çağrılır. Türünü `CComVariant` nesne olacak gt; vt_dıspatch & veya VT_UNKNOWN, sırasıyla.

Veya, başlatmak için kullanılan SAFERRAY işaretçi `CComVariant` nesne. SAFEARRAY bir kopyasını depolanan `CComVariant` nesne. Türünü `CComVariant` nesne, özgün türü SAFEARRAY'i ve VT_ARRAY birleşimi olacaktır.

*cSrc*<br/>
[in] **Char** başlatmak için kullanılan `CComVariant` nesne. Türünü `CComVariant` nesne VT_I1 olacaktır.

*bstrSrc*<br/>
[in] BSTR başlatmak için kullanılan `CComVariant` nesne. Türünü `CComVariant` nesne VT_BSTR olacaktır.

### <a name="remarks"></a>Açıklamalar

Yok edici çağırarak temizleme yönetir [CComVariant::Clear](#clear).

##  <a name="dtor"></a>  CComVariant:: ~ CComVariant

Yıkıcı.

```
~CComVariant() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırarak temizleme yönetir [CComVariant::Clear](#clear).

##  <a name="changetype"></a>  CComVariant::ChangeType

Dönüştürür `CComVariant` nesnesine yeni bir tür.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*vtNew*<br/>
[in] Yeni türü için `CComVariant` nesne.

*pSrc*<br/>
[in] Değeri yeni türe dönüştürülüp dönüştürülmeyeceğini değişken bir işaretçi. Varsayılan değer NULL ise anlamı `CComVariant` nesne yerinde dönüştürülür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bir değer geçirmek, *pSrc*, `ChangeType` bu dönüştürme için kaynak olarak kullanır. Aksi takdirde, `CComVariant` nesne kaynak olacaktır.

##  <a name="clear"></a>  CComVariant::Clear

Temizler `CComVariant` çağırarak `VariantClear` Win32 işlevi.

```
HRESULT Clear();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Yıkıcı otomatik olarak çağırır `Clear`.

##  <a name="copy"></a>  CComVariant::Copy

Serbest bırakma `CComVariant` nesnesi ve ardından belirtilen değişken bir kopyasını atar.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
[in] Bir işaretçi [değişken](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) kopyalanacak.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="copyto"></a>  CComVariant::CopyTo

İçeriğini kopyalar `CComVariant` nesne.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Parametreler

*pstrDest*<br/>
İşaret içeriğini bir kopyasını alacak bir BSTR `CComVariant` nesne.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`CComVariant` Nesne VT_BSTR türde olması gerekir.

##  <a name="detach"></a>  CComVariant::Detach

Temel alınan DEĞİŞKENDEN ayırır `CComVariant` nesne ve VT_EMPTY için nesnenin türünü ayarlar.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
[out] Temel alınan nesnenin değişken değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

DEĞİŞKEN içeriğini tarafından başvurulan Not *pDest* çağırma bir tür ve değer atanmadan önce otomatik olarak temizlenir `CComVariant` nesne.

##  <a name="getsize"></a>  CComVariant::GetSize

Basit sabit boyutu çeşitleri için bu yöntemi döndürür **sizeof** artı temel alınan veri türü **sizeof(VARTYPE)**.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli içeriğinin bayt cinsinden boyut `CComVariant` nesne.

### <a name="remarks"></a>Açıklamalar

DEĞİŞKEN bir arabirim işaretçisi içeriyorsa `GetSize` sorgular `IPersistStream` veya `IPersistStreamInit`. Başarılı, dönüş değeri tarafından döndürülen değerin alt sıra 32 bit ise `GetSizeMax` artı **sizeof** CLSID'ini ve **sizeof(VARTYPE)**. Arabirim işaretçisi, NULL ise `GetSize` döndürür **sizeof** artı CLSID **sizeof(VARTYPE)**. Toplam boyutu ULONG_MAX büyük olması durumunda `GetSize` döndürür **sizeof(VARTYPE)** bir hata gösterir.

Diğer durumlarda, geçici bir değişken türü VT_BSTR geçerli DEĞİŞKENDEN durumunda bırakılması. Bu BSTR uzunluğunu boyutu dize uzunluğu artı dize uzunluğu artı artı boş karakter boyutunu olarak hesaplanır **sizeof(VARTYPE)**. DEĞİŞKEN VT_BSTR, türünde bir değişken için zorlanamayan varsa `GetSize` döndürür **sizeof(VARTYPE)**.

Bu yöntem tarafından döndürülen boyutla tarafından kullanılan bayt sayısı ile eşleşen [CComVariant::WriteToStream](#writetostream) başarılı koşullar altında.

##  <a name="operator_eq"></a>  CComVariant::operator =

Bir değer ve karşılık gelen tür atar `CComVariant` nesne.

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
[in] `CComVariant` Veya [değişken](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) atanacak `CComVariant` nesne. Kaynak değişken içeriğini hedef dönüştürme olmadan kopyalanır.

*bstrSrc*<br/>
[in] Atanacak BSTR `CComVariant` nesne. Türünü `CComVariant` nesne VT_BSTR olacaktır.

*lpszSrc*<br/>
[in] Atanacak karakter dizesi `CComVariant` nesne. Geniş (Unicode) karakter sıfır ile sonlandırılmış dize, işleci veya bir ANSI dizesine LPCSTR sürüme LPCOLESTR sürümüne geçirebilirsiniz. Her iki durumda da, bir Unicode kullanılarak ayrılmış BSTR dizeye dönüştürülür `SysAllocString`. Türünü `CComVariant` nesne VT_BSTR olacaktır.

*bSrc*<br/>
[in] **Bool** atanacak `CComVariant` nesne. **Bool** depolanmadan önce bağımsız değişkeni için bir varıant_bool dönüştürülür. Türünü `CComVariant` nesne VT_BOOL olacaktır.

*nSrc*<br/>
[in] **İnt**, BYTE, **kısa**, **uzun**, LONGLONG, ULONGLONG, **işaretsiz**, **işaretsiz uzun**, veya **işaretsiz int** atanacak `CComVariant` nesne. Türünü `CComVariant` nesne olacak VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4, sırasıyla.

*fltsrc &*<br/>
[in] **Float** atanacak `CComVariant` nesne. Türünü `CComVariant` nesne VT_R4 olacaktır.

*dblsrc &*<br/>
[in] **Çift** atanacak `CComVariant` nesne. Türünü `CComVariant` nesne VT_R8 olacaktır.

*cysrc &*<br/>
[in] `CY` Atanacak `CComVariant` nesne. Türünü `CComVariant` nesne VT_CY olacaktır.

*pSrc*<br/>
[in] `IDispatch` Veya `IUnknown` atanacak işaretçi `CComVariant` nesne. `AddRef` arabirim işaretçisi üzerinde çağrılır. Türünü `CComVariant` nesne olacak gt; vt_dıspatch & veya VT_UNKNOWN, sırasıyla.

Veya, atanacak SAFEARRAY'i işaretçi `CComVariant` nesne. SAFEARRAY bir kopyasını depolanan `CComVariant` nesne. Türünü `CComVariant` nesne, özgün türü SAFEARRAY'i ve VT_ARRAY birleşimi olacaktır.

*cSrc*<br/>
[in] Atanacak char `CComVariant` nesne. Türünü `CComVariant` nesne VT_I1 olacaktır.

##  <a name="operator_eq_eq"></a>  CComVariant::operator ==

Belirtir olup olmadığını `CComVariant` nesne belirtilen değişken eşittir.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

Gerekirse TRUE döndürür değerine ve türüne *varSrc* türü ve değeri eşitse, sırasıyla `CComVariant` nesne. Aksi takdirde FALSE. İşleci, karşılaştırma yapmak için kullanıcının varsayılan yerel ayarı kullanır.

İşleci, yalnızca değişken türleri değerini karşılaştırır. Dize, tamsayı ve kayan nokta ancak diziler veya kayıt ile karşılaştırır.

##  <a name="operator_neq"></a>  CComVariant::operator! =

Belirtir olup olmadığını `CComVariant` nesne belirtilen değişken eşit değil.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

Gerekirse TRUE döndürür değer veya tür *varSrc* değer veya tür, eşit değil, sırasıyla `CComVariant` nesne. Aksi takdirde FALSE. İşleci, karşılaştırma yapmak için kullanıcının varsayılan yerel ayarı kullanır.

İşleci, yalnızca değişken türleri değerini karşılaştırır. Dize, tamsayı ve kayan nokta ancak diziler veya kayıt ile karşılaştırır.

##  <a name="operator_lt"></a>  CComVariant::operator &lt;

Belirtir olup olmadığını `CComVariant` nesne belirtilen değişken azdır.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

Gerekirse TRUE döndürür değerini `CComVariant` nesne değerini azdır *varSrc*. Aksi takdirde FALSE. İşleci, karşılaştırma yapmak için kullanıcının varsayılan yerel ayarı kullanır.

##  <a name="operator_gt"></a>  CComVariant::operator &gt;

Belirtir olup olmadığını `CComVariant` nesne, belirtilen değişken büyüktür.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

Gerekirse TRUE döndürür değerini `CComVariant` nesnedir değerinden daha büyük *varSrc*. Aksi takdirde FALSE. İşleci, karşılaştırma yapmak için kullanıcının varsayılan yerel ayarı kullanır.

##  <a name="readfromstream"></a>  CComVariant::ReadFromStream

Belirtilen akış içinde yer alan değişken için temel alınan değişken ayarlar.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[in] Bir işaretçi [IStream](/windows/desktop/api/objidl/nn-objidl-istream) akış verilerini içeren bir arabirimdeki.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`ReadToStream` önceki bir çağrı gerektirir [WriteToStream](#writetostream).

##  <a name="setbyref"></a>  CComVariant::SetByRef

Başlatır `CComVariant` nesne ve ayarlar `vt` VT_BYREF üye.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir değişken, örneğin, BSTR türünde **int**, veya **char**.

*PT*<br/>
İşaretçiyi başlatmak için kullanılan `CComVariant` nesne.

### <a name="remarks"></a>Açıklamalar

`SetByRef` başlatan bir işlevi şablonu olarak `CComVariant` işaretçiyi nesneye *pT* ve ayarlar `vt` VT_BYREF üye. Örneğin:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>  CComVariant::WriteToStream

Temel alınan değişken bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[in] Bir işaretçi [IStream](/windows/desktop/api/objidl/nn-objidl-istream) arabirimdeki bir akış.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)