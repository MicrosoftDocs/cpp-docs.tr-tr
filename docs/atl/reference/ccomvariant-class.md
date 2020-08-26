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
ms.openlocfilehash: 40315077ceba3d87e12c8ab426560deef4928793
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833614"
---
# <a name="ccomvariant-class"></a>CComVariant sınıfı

Bu sınıf, depolanan veri türünü gösteren bir üye sağlayan DEĞIŞKEN türünü sarmalanmış.

## <a name="syntax"></a>Syntax

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ccomvarıant:: CComVariant](#ccomvariant)|Oluşturucu.|
|[Ccomvarıant:: ~ CComVariant](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomvarıant:: Attach](#attach)|Nesneye bir DEĞIŞKEN ekler `CComVariant` .|
|[CComVariant:: ChangeType](#changetype)|`CComVariant`Nesneyi yeni bir türe dönüştürür.|
|[Ccomvarıant:: Clear](#clear)|Nesneyi temizler `CComVariant` .|
|[Ccomvarıant:: Copy](#copy)|Bir VARYANTı `CComVariant` nesnesine kopyalar.|
|[CComVariant:: CopyTo](#copyto)|Nesnesinin içeriğini kopyalar `CComVariant` .|
|[CComVariant::D etach](#detach)|Temel varyansı `CComVariant` nesneden ayırır.|
|[Ccomvarıant:: GetSize](#getsize)|Nesnenin içeriğinin bayt cinsinden boyutunu döndürür `CComVariant` .|
|[CComVariant:: ReadFromStream](#readfromstream)|Akıştan bir DEĞIŞKEN yükler.|
|[CComVariant:: SetByRef](#setbyref)|Nesnesini başlatır `CComVariant` ve `vt` üyeyi VT_BYREF olarak ayarlar.|
|[CComVariant:: WriteToStream](#writetostream)|Temel varyansı bir akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|İşleç|Açıklama|
|-|-|
|[Ccomvarıant:: operator <](#operator_lt)|`CComVariant`Nesnenin BELIRTILEN VARIANT 'tan daha az olup olmadığını gösterir.|
|[Ccomvarıant:: operator >](#operator_gt)|`CComVariant`Nesnenin BELIRTILEN değişkenden daha büyük olup olmadığını gösterir.|
|[işleç! =](#operator_neq)|`CComVariant`Nesnenin BELIRTILEN varyanta eşit olup olmadığını gösterir.|
|[işleç =](#operator_eq)|Nesnesine bir değer atar `CComVariant` .|
|[işleç = =](#operator_eq_eq)|`CComVariant`Nesnenin BELIRTILEN varyanta eşit olup olmadığını gösterir.|

## <a name="remarks"></a>Açıklamalar

`CComVariant` birleşim ve birleşim içinde depolanan verilerin türünü gösteren bir üyenin yer aldığı varyant ve VARIANTARG türünü sarmalanmış. Çeşitler genellikle Otomasyonda kullanılır.

`CComVariant` değişken türünden türeyebilir, bu nedenle bir VARYANTıN kullanılabileceği her yerde kullanılabilir. Örneğin, bir türü ayıklamak için V_VT makrosunu kullanabilir `CComVariant` veya `vt` yalnızca bir değişkenle yaptığınız gibi, üyeye doğrudan erişebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

## <a name="ccomvariantattach"></a><a name="attach"></a> Ccomvarıant:: Attach

Nesnenin geçerli içeriğini güvenli bir şekilde temizler `CComVariant` , *pSrc* içeriğini bu nesneye kopyalar ve ardından *psrc* 'nin varyant türünü VT_EMPTY olarak ayarlar.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
'ndaki Nesneye eklenecek [varyanta](/windows/win32/api/oaidl/ns-oaidl-variant) işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PSrc* tarafından tutulan verilerin sahipliği `CComVariant` nesnesine aktarılır.

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a> Ccomvarıant:: CComVariant

Her Oluşturucu `CComVariant` `VariantInit` Win32 işlevini çağırarak veya geçirilen parametrelere göre nesnenin değerini ve türünü ayarlayarak nesnenin güvenli bir şekilde başlatılmasını işler.

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
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan veya değişkeni `CComVariant` . Kaynak varyantın içeriği, dönüştürme yapılmadan hedefe kopyalanır.

*lpszSrc*<br/>
'ndaki Nesneyi başlatmak için kullanılan karakter dizesi `CComVariant` . Sıfır ile sonlandırılmış geniş (Unicode) bir karakter dizesini oluşturucunun LPCOTASTR sürümüne veya bir ANSI dizesinin LPCSTR sürümüne geçirebilirsiniz. Her iki durumda da, dize kullanılarak ayrılmış bir Unicode BSTR 'e dönüştürülür `SysAllocString` . Nesne türü VT_BSTR olacaktır `CComVariant` .

*bSrc*<br/>
'ndaki **`bool`** Nesneyi başlatmak için kullanılır `CComVariant` . **`bool`** Bağımsız değişken depolanmadan önce VARIANT_BOOL dönüştürülür. Nesne türü VT_BOOL olacaktır `CComVariant` .

*nSrc*<br/>
'ndaki **`int`** Nesneyi başlatmak için, **byte**, **`short`** , **`long`** , longlong, ULONGLONG, **`unsigned short`** , **`unsigned long`** veya **`unsigned int`** kullanılır `CComVariant` . `CComVariant`Nesnenin türü, sırasıyla VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4 olacaktır.

*vtSrc*<br/>
'ndaki Varyantın türü. İlk parametre olduğunda **`int`** Geçerli türler VT_I4 ve VT_INT. İlk parametre olduğunda **`long`** Geçerli türler VT_I4 ve VT_ERROR. İlk parametre olduğunda **`double`** Geçerli türler VT_R8 ve VT_DATE. İlk parametre olduğunda **`unsigned int`** Geçerli türler VT_UI4 ve VT_UINT.

*fltSrc*<br/>
'ndaki **`float`** Nesneyi başlatmak için kullanılır `CComVariant` . Nesne türü VT_R4 olacaktır `CComVariant` .

*dblSrc*<br/>
'ndaki **`double`** Nesneyi başlatmak için kullanılır `CComVariant` . Nesne türü VT_R8 olacaktır `CComVariant` .

*cySrc*<br/>
'ndaki `CY` Nesneyi başlatmak için kullanılır `CComVariant` . Nesne türü VT_CY olacaktır `CComVariant` .

*pSrc*<br/>
'ndaki `IDispatch` `IUnknown` Nesneyi başlatmak için kullanılan veya işaretçisi `CComVariant` . `AddRef` , arabirim işaretçisi üzerinde çağrılır. `CComVariant`Nesnenin türü sırasıyla VT_DISPATCH veya VT_UNKNOWN olacaktır.

Ya da, nesneyi başlatmak için kullanılan SAFERRAY işaretçisi `CComVariant` . SAFEARRAY 'in bir kopyası `CComVariant` nesnesinde depolanır. Nesnenin türü, `CComVariant` SafeArray ve vt_array orijinal türünün bir birleşimi olacaktır.

*cSrc*<br/>
'ndaki **`char`** Nesneyi başlatmak için kullanılır `CComVariant` . Nesne türü VT_I1 olacaktır `CComVariant` .

*bstrSrc*<br/>
'ndaki Nesneyi başlatmak için kullanılan BSTR `CComVariant` . Nesne türü VT_BSTR olacaktır `CComVariant` .

### <a name="remarks"></a>Açıklamalar

Yıkıcı, [Ccomvarıant:: Clear](#clear)öğesini çağırarak Temizleme işlemini yönetir.

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a> Ccomvarıant:: ~ CComVariant

Yok edicisi.

```
~CComVariant() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [Ccomvarıant:: Clear](#clear)öğesini çağırarak Temizleme işlemini yönetir.

## <a name="ccomvariantchangetype"></a><a name="changetype"></a> CComVariant:: ChangeType

`CComVariant`Nesneyi yeni bir türe dönüştürür.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*Yeni VT*<br/>
'ndaki Nesnenin yeni türü `CComVariant` .

*pSrc*<br/>
'ndaki DEĞIŞKEN için değeri yeni türe dönüştürülecek olan bir işaretçi. Varsayılan değer NULL, yani `CComVariant` nesnenin yerinde dönüştürülecektir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PSrc*için bir değer geçirirseniz, `ChangeType` Bu değişkeni dönüştürmenin kaynağı olarak kullanır. Aksi takdirde, `CComVariant` nesne kaynak olur.

## <a name="ccomvariantclear"></a><a name="clear"></a> Ccomvarıant:: Clear

`CComVariant`Win32 işlevini çağırarak nesneyi temizler `VariantClear` .

```
HRESULT Clear();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yıkıcı otomatik olarak çağırır `Clear` .

## <a name="ccomvariantcopy"></a><a name="copy"></a> Ccomvarıant:: Copy

Nesneyi serbest bırakır `CComVariant` ve sonra belirtilen varyantın bir kopyasını atar.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
'ndaki Kopyalanacak [varyanta](/windows/win32/api/oaidl/ns-oaidl-variant) yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomvariantcopyto"></a><a name="copyto"></a> CComVariant:: CopyTo

Nesnesinin içeriğini kopyalar `CComVariant` .

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Parametreler

*pstrDest*<br/>
Nesnenin içeriğinin bir kopyasını alacak bir BSTR 'ye işaret eder `CComVariant` .

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`CComVariant`Nesne VT_BSTR türünde olmalıdır.

## <a name="ccomvariantdetach"></a><a name="detach"></a> CComVariant::D etach

Nesneden temel varyansı ayırır `CComVariant` ve nesnenin türünü VT_EMPTY olarak ayarlar.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
dışı Nesnenin temel varyant değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PDest* tarafından başvurulan değişkenin içeriğinin, nesne değeri ve türü atanmadan önce otomatik olarak temizlendiğini unutmayın `CComVariant` .

## <a name="ccomvariantgetsize"></a><a name="getsize"></a> Ccomvarıant:: GetSize

Basit sabit boyutlu çeşitler için bu yöntem, **`sizeof`** temel alınan veri türü ve **SIZEOF (VARTYPE)** için değer döndürür.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin geçerli içeriğinin bayt cinsinden boyutu `CComVariant` .

### <a name="remarks"></a>Açıklamalar

DEĞIŞKEN bir arabirim işaretçisi içeriyorsa, `GetSize` veya için sorgular `IPersistStream` `IPersistStreamInit` . Başarılı olursa, dönüş değeri artı ve ile döndürülen değerin düşük sıralı 32 bittir `GetSizeMax` `sizeof(CLSID)` `sizeof(VARTYPE)` . Arabirim işaretçisi NULL ise, `GetSize` `sizeof(CLSID)` artı döndürür `sizeof(VARTYPE)` . Toplam boyut ULONG_MAX büyükse, `GetSize` `sizeof(VARTYPE)` bir hatayı gösteren döndürür.

Diğer tüm durumlarda, VT_BSTR türünde geçici bir DEĞIŞKEN geçerli VARIANT 'tan zorlandır. Bu BSTR 'nin uzunluğu, dizenin uzunluğu artı dize uzunluğu ve null karakter artı **sizeof (VARTYPE)** boyutu olarak hesaplanır. DEĞIŞKEN VT_BSTR türünde bir DEĞIŞKENLE zorlanamadığında, `GetSize` **SIZEOF (VARTYPE)** döndürür.

Bu yöntem tarafından döndürülen boyut, başarılı koşullar altında [CComVariant:: WriteToStream](#writetostream) tarafından kullanılan bayt sayısıyla eşleşir.

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a> Ccomvarıant:: operator =

Nesneye bir değer ve karşılık gelen tür atar `CComVariant` .

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
'ndaki `CComVariant` Nesneye atanacak veya [değişken](/windows/win32/api/oaidl/ns-oaidl-variant) `CComVariant` . Kaynak varyantın içeriği, dönüştürme yapılmadan hedefe kopyalanır.

*bstrSrc*<br/>
'ndaki Nesneye atanacak BSTR `CComVariant` . Nesne türü VT_BSTR olacaktır `CComVariant` .

*lpszSrc*<br/>
'ndaki Nesneye atanacak karakter dizesi `CComVariant` . Sıfır ile sonlandırılmış geniş (Unicode) bir karakter dizesini işlecin LPCOLESTR sürümüne veya bir ANSI dizesini de LPCSTR sürümüne geçirebilirsiniz. Her iki durumda da, dize kullanılarak ayrılmış bir Unicode BSTR 'e dönüştürülür `SysAllocString` . Nesne türü VT_BSTR olacaktır `CComVariant` .

*bSrc*<br/>
'ndaki **`bool`** `CComVariant` Nesnesine atanacak. **`bool`** Bağımsız değişken depolanmadan önce VARIANT_BOOL dönüştürülür. Nesne türü VT_BOOL olacaktır `CComVariant` .

*nSrc*<br/>
'ndaki **`int`** Nesnesine atanacak, Byte, **`short`** , **`long`** , LONGLONG, ULONGLONG, **`unsigned short`** , **`unsigned long`** , veya **`unsigned int`** `CComVariant` . `CComVariant`Nesnenin türü, sırasıyla VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4 olacaktır.

*fltSrc*<br/>
'ndaki **`float`** `CComVariant` Nesnesine atanacak. Nesne türü VT_R4 olacaktır `CComVariant` .

*dblSrc*<br/>
'ndaki **`double`** `CComVariant` Nesnesine atanacak. Nesne türü VT_R8 olacaktır `CComVariant` .

*cySrc*<br/>
'ndaki `CY` `CComVariant` Nesnesine atanacak. Nesne türü VT_CY olacaktır `CComVariant` .

*pSrc*<br/>
'ndaki `IDispatch` `IUnknown` Nesneye atanacak olan veya işaretçisi `CComVariant` . `AddRef` , arabirim işaretçisi üzerinde çağrılır. `CComVariant`Nesnenin türü sırasıyla VT_DISPATCH veya VT_UNKNOWN olacaktır.

Ya da nesneye atanacak bir SAFEARRAY işaretçisi `CComVariant` . SAFEARRAY 'in bir kopyası `CComVariant` nesnesinde depolanır. Nesnenin türü, `CComVariant` SafeArray ve vt_array orijinal türünün bir birleşimi olacaktır.

*cSrc*<br/>
'ndaki Nesneye atanacak karakter `CComVariant` . Nesne türü VT_I1 olacaktır `CComVariant` .

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a> Ccomvarıant:: operator = =

`CComVariant`Nesnenin BELIRTILEN varyanta eşit olup olmadığını gösterir.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

*VarSrc* değeri ve türü, sırasıyla DEĞERINE eşitse true değerini döndürür `CComVariant` . Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

İşleci yalnızca değişken türlerinin değerini karşılaştırır. Dizeleri, tamsayıları ve kayan noktaları karşılaştırır, ancak dizileri veya kayıtları karşılaştırır.

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a> Ccomvarıant:: operator! =

`CComVariant`Nesnenin BELIRTILEN varyanta eşit olup olmadığını gösterir.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

*VarSrc* değeri veya türü, sırasıyla nesne değerine veya türüne EŞIT değilse true döndürür `CComVariant` . Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

İşleci yalnızca değişken türlerinin değerini karşılaştırır. Dizeleri, tamsayıları ve kayan noktaları karşılaştırır, ancak dizileri veya kayıtları karşılaştırır.

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a> CComVariant:: işleci &lt;

`CComVariant`Nesnenin BELIRTILEN VARIANT 'tan daha az olup olmadığını gösterir.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

`CComVariant`Nesnenin değeri *varSrc*değerinden küçükse true değerini döndürür. Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a> CComVariant:: işleci &gt;

`CComVariant`Nesnenin BELIRTILEN değişkenden daha büyük olup olmadığını gösterir.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

`CComVariant`Nesnenin değeri *varSrc*değerinden büyükse true değerini döndürür. Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a> CComVariant:: ReadFromStream

Temeldeki varyansı belirtilen akışta bulunan VARYANTA göre ayarlar.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Verileri içeren akıştaki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`ReadToStream`[WriteToStream](#writetostream)'e daha önceki bir çağrı gerektirir.

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a> CComVariant:: SetByRef

Nesnesini başlatır `CComVariant` ve `vt` üyeyi VT_BYREF olarak ayarlar.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
DEĞIŞKEN türü, örneğin, BSTR, **`int`** veya **`char`** .

*Yönergelerinin*<br/>
Nesneyi başlatmak için kullanılan işaretçi `CComVariant` .

### <a name="remarks"></a>Açıklamalar

`SetByRef` , `CComVariant` nesneyi Işaretçi *PT* olarak başlatan ve `vt` üyeyi VT_BYREF olarak ayarlayan bir işlev şablonudur. Örnek:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a> CComVariant:: WriteToStream

Temel varyansı bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Akıştaki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
