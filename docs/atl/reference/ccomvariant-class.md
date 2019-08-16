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
ms.openlocfilehash: b4c157435aaffab5f1315fd4636f55f9d4e0d5b4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496868"
---
# <a name="ccomvariant-class"></a>CComVariant sınıfı

Bu sınıf, depolanan veri türünü gösteren bir üye sağlayan DEĞIŞKEN türünü sarmalanmış.

## <a name="syntax"></a>Sözdizimi

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
|[Ccomvarıant:: Attach](#attach)|`CComVariant` Nesneye bir değişken ekler.|
|[CComVariant:: ChangeType](#changetype)|`CComVariant` Nesneyi yeni bir türe dönüştürür.|
|[Ccomvarıant:: Clear](#clear)|`CComVariant` Nesneyi temizler.|
|[Ccomvarıant:: Copy](#copy)|Bir varyantı `CComVariant` nesnesine kopyalar.|
|[CComVariant:: CopyTo](#copyto)|`CComVariant` Nesnesinin içeriğini kopyalar.|
|[CComVariant::D etach](#detach)|Temel varyansı `CComVariant` nesneden ayırır.|
|[Ccomvarıant:: GetSize](#getsize)|`CComVariant` Nesnenin içeriğinin bayt cinsinden boyutunu döndürür.|
|[CComVariant:: ReadFromStream](#readfromstream)|Akıştan bir DEĞIŞKEN yükler.|
|[CComVariant:: SetByRef](#setbyref)|Nesnesini başlatır ve `vt` üyeyi VT_BYREF olarak ayarlar. `CComVariant`|
|[CComVariant:: WriteToStream](#writetostream)|Temel varyansı bir akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|||
|-|-|
|[Ccomvarıant:: operator <](#operator_lt)|`CComVariant` Nesnenin belirtilen VARIANT 'tan daha az olup olmadığını gösterir.|
|[Ccomvarıant:: operator >](#operator_gt)|`CComVariant` Nesnenin belirtilen değişkenden daha büyük olup olmadığını gösterir.|
|[işleç! =](#operator_neq)|`CComVariant` Nesnenin belirtilen varyanta eşit olup olmadığını gösterir.|
|[işleç =](#operator_eq)|`CComVariant` Nesnesine bir değer atar.|
|[işleç = =](#operator_eq_eq)|`CComVariant` Nesnenin belirtilen varyanta eşit olup olmadığını gösterir.|

## <a name="remarks"></a>Açıklamalar

`CComVariant`birleşim ve birleşim içinde depolanan verilerin türünü gösteren bir üyenin yer aldığı varyant ve VARIANTARG türünü sarmalanmış. Çeşitler genellikle Otomasyonda kullanılır.

`CComVariant`değişken türünden türeyebilir, bu nedenle bir VARYANTıN kullanılabileceği her yerde kullanılabilir. Örneğin, V_VT makrosunu kullanarak bir `CComVariant` veya türünü çıkarabilir veya bir değişkenle yaptığınız gibi doğrudan `vt` üyeye erişebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

##  <a name="attach"></a>Ccomvarıant:: Attach

`CComVariant` Nesnenin geçerli içeriğini güvenli bir şekilde temizler, *pSrc* içeriğini bu nesneye kopyalar ve ardından *pSrc* 'nin varyant türünü VT_EMPTY olarak ayarlar.

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

##  <a name="ccomvariant"></a>Ccomvarıant:: CComVariant

Her Oluşturucu `VariantInit` Win32 işlevini çağırarak veya geçirilen parametrelere `CComVariant` göre nesnenin değerini ve türünü ayarlayarak nesnenin güvenli bir şekilde başlatılmasını işler.

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
'ndaki Nesneyi başlatmak için kullanılan `CComVariant` `CComVariant` veya değişkeni. Kaynak varyantın içeriği, dönüştürme yapılmadan hedefe kopyalanır.

*lpszSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan karakter dizesi. Sıfır ile sonlandırılmış geniş (Unicode) bir karakter dizesini oluşturucunun LPCOTASTR sürümüne veya bir ANSI dizesinin LPCSTR sürümüne geçirebilirsiniz. Her iki durumda da, dize kullanılarak `SysAllocString`ayrılmış bir Unicode BSTR 'e dönüştürülür. `CComVariant` Nesne türü VT_BSTR olacaktır.

*bSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan **bool** . **Bool** bağımsız değişkeni depolanmadan önce bir VARIANT_BOOL dönüştürülür. `CComVariant` Nesne türü vt_bool olacaktır.

*nSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için **int**, **byte**, **Short**, **Long**, longlong, ULONGLONG, **işaretsiz kısa**, **işaretsiz Long**veya **işaretsiz int** kullanılır. `CComVariant` Nesne türü sırasıyla VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4 olacaktır.

*vtSrc*<br/>
'ndaki Varyantın türü. İlk parametre **int**olduğunda GEÇERLI türler VT_I4 ve VT_INT olur. İlk parametre **uzun**olduğunda GEÇERLI türler VT_I4 ve VT_ERROR olur. İlk parametre **Double**olduğunda GEÇERLI türler VT_R8 ve VT_DATE olur. İlk parametre **işaretsiz int**olduğunda GEÇERLI türler VT_UI4 ve VT_UINT olur.

*fltSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan **float** . `CComVariant` Nesne türü VT_R4 olacaktır.

*dblSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan **çift** . `CComVariant` Nesne türü VT_R8 olacaktır.

*cySrc*<br/>
'ndaki Nesneyi başlatmak için `CY`kullanılır. `CComVariant` `CComVariant` Nesne türü VT_CY olacaktır.

*pSrc*<br/>
'ndaki Nesneyi başlatmak `IUnknown` için kullanılan veyaişaretçisi.`IDispatch` `CComVariant` `AddRef`, arabirim işaretçisi üzerinde çağrılır. `CComVariant` Nesne türü sırasıyla VT_DISPATCH veya VT_UNKNOWN olacaktır.

Ya da, `CComVariant` nesneyi başlatmak için kullanılan saferray işaretçisi. SafeArray 'in bir kopyası `CComVariant` nesnesinde depolanır. `CComVariant` Nesnenin türü, SAFEARRAY ve vt_array orijinal türünün bir birleşimi olacaktır.

*cSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan **karakter** . `CComVariant` Nesne türü VT_I1 olacaktır.

*bstrSrc*<br/>
'ndaki `CComVariant` Nesneyi başlatmak için kullanılan BSTR. `CComVariant` Nesne türü VT_BSTR olacaktır.

### <a name="remarks"></a>Açıklamalar

Yıkıcı, [Ccomvarıant:: Clear](#clear)öğesini çağırarak Temizleme işlemini yönetir.

##  <a name="dtor"></a>Ccomvarıant:: ~ CComVariant

Yok edicisi.

```
~CComVariant() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [Ccomvarıant:: Clear](#clear)öğesini çağırarak Temizleme işlemini yönetir.

##  <a name="changetype"></a>CComVariant:: ChangeType

`CComVariant` Nesneyi yeni bir türe dönüştürür.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*Yeni VT*<br/>
'ndaki `CComVariant` Nesnenin yeni türü.

*pSrc*<br/>
'ndaki DEĞIŞKEN için değeri yeni türe dönüştürülecek olan bir işaretçi. Varsayılan değer null, yani `CComVariant` nesnenin yerinde dönüştürülecektir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PSrc*için bir değer geçirirseniz, `ChangeType` bu değişkeni dönüştürmenin kaynağı olarak kullanır. Aksi takdirde, `CComVariant` nesne kaynak olur.

##  <a name="clear"></a>Ccomvarıant:: Clear

Win32işlevini`VariantClear` çağırarak nesneyi temizler. `CComVariant`

```
HRESULT Clear();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yıkıcı otomatik olarak çağırır `Clear`.

##  <a name="copy"></a>Ccomvarıant:: Copy

`CComVariant` Nesneyi serbest bırakır ve sonra belirtilen varyantın bir kopyasını atar.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
'ndaki Kopyalanacak [varyanta](/windows/win32/api/oaidl/ns-oaidl-variant) yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="copyto"></a>CComVariant:: CopyTo

`CComVariant` Nesnesinin içeriğini kopyalar.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Parametreler

*pstrDest*<br/>
`CComVariant` Nesnenin içeriğinin bir kopyasını alacak bir BSTR 'ye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`CComVariant` Nesne VT_BSTR türünde olmalıdır.

##  <a name="detach"></a>CComVariant::D etach

`CComVariant` Nesnenin temel türevini nesneden ayırır ve nesnenin türünü VT_EMPTY olarak ayarlar.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
dışı Nesnenin temel varyant değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*PDest* tarafından başvurulan değişkenin içeriğinin, `CComVariant` nesne değeri ve türü atanmadan önce otomatik olarak temizlendiğini unutmayın.

##  <a name="getsize"></a>Ccomvarıant:: GetSize

Basit sabit boyutlu çeşitler için, bu yöntem, temel alınan veri türü artı **sizeof (VARTYPE)** ile sizeof ' u döndürür.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CComVariant` Nesnenin geçerli içeriğinin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Değişken bir arabirim işaretçisi içeriyorsa, `GetSize` veya `IPersistStreamInit`için `IPersistStream` sorgular. Başarılı olursa, dönüş değeri, tarafından `GetSizeMax` döndürülen değerin alt sıra 32 bitleridir ve **sizeof** bir CLSID ve **sizeof (VARTYPE)** . Arabirim işaretçisi null ise, `GetSize` **sizeof** bir CLSID Plus **sizeof (VARTYPE)** döndürür. Toplam boyut ulong_max değerinden büyükse, `GetSize` bir hatayı gösteren **sizeof (VARTYPE)** değerini döndürür.

Diğer tüm durumlarda, VT_BSTR türünde geçici bir DEĞIŞKEN geçerli VARIANT 'tan zorlanır. Bu BSTR 'nin uzunluğu, dizenin uzunluğu artı dize uzunluğu ve null karakter artı **sizeof (VARTYPE)** boyutu olarak hesaplanır. Değişken, VT_BSTR türünde bir değişkenle zorlanamadığında, `GetSize` **sizeof (VARTYPE)** döndürür.

Bu yöntem tarafından döndürülen boyut, başarılı koşullar altında [CComVariant:: WriteToStream](#writetostream) tarafından kullanılan bayt sayısıyla eşleşir.

##  <a name="operator_eq"></a>Ccomvarıant:: operator =

`CComVariant` Nesneye bir değer ve karşılık gelen tür atar.

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
'ndaki Nesneyeatanacak`CComVariant` veya değişken. [](/windows/win32/api/oaidl/ns-oaidl-variant) `CComVariant` Kaynak varyantın içeriği, dönüştürme yapılmadan hedefe kopyalanır.

*bstrSrc*<br/>
'ndaki `CComVariant` Nesneye atanacak BSTR. `CComVariant` Nesne türü VT_BSTR olacaktır.

*lpszSrc*<br/>
'ndaki `CComVariant` Nesneye atanacak karakter dizesi. Sıfır ile sonlandırılmış geniş (Unicode) bir karakter dizesini işlecin LPCOLESTR sürümüne veya bir ANSI dizesini de LPCSTR sürümüne geçirebilirsiniz. Her iki durumda da, dize kullanılarak `SysAllocString`ayrılmış bir Unicode BSTR 'e dönüştürülür. `CComVariant` Nesne türü VT_BSTR olacaktır.

*bSrc*<br/>
'ndaki `CComVariant` Nesneye atanacak **bool** . **Bool** bağımsız değişkeni depolanmadan önce bir VARIANT_BOOL dönüştürülür. `CComVariant` Nesne türü vt_bool olacaktır.

*nSrc*<br/>
'ndaki Nesneye`CComVariant` atanmak üzere **int**, Byte, **Short**, **Long**, longlong, ULONGLONG, **işaretsiz kısa**, **işaretsiz Long**veya **işaretsiz int** . `CComVariant` Nesne türü sırasıyla VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4 olacaktır.

*fltSrc*<br/>
'ndaki `CComVariant` Nesneye atanacak **float** . `CComVariant` Nesne türü VT_R4 olacaktır.

*dblSrc*<br/>
'ndaki `CComVariant` Nesneye atanacak **Double** . `CComVariant` Nesne türü VT_R8 olacaktır.

*cySrc*<br/>
'ndaki Nesnesineatanacak`CComVariant` . `CY` `CComVariant` Nesne türü VT_CY olacaktır.

*pSrc*<br/>
'ndaki Nesneyeatanacak`CComVariant` olan `IUnknown`veyaişaretçisi `IDispatch` . `AddRef`, arabirim işaretçisi üzerinde çağrılır. `CComVariant` Nesne türü sırasıyla VT_DISPATCH veya VT_UNKNOWN olacaktır.

Ya da `CComVariant` nesneye atanacak bir SAFEARRAY işaretçisi. SafeArray 'in bir kopyası `CComVariant` nesnesinde depolanır. `CComVariant` Nesnenin türü, SAFEARRAY ve vt_array orijinal türünün bir birleşimi olacaktır.

*cSrc*<br/>
'ndaki `CComVariant` Nesneye atanacak karakter. `CComVariant` Nesne türü VT_I1 olacaktır.

##  <a name="operator_eq_eq"></a>Ccomvarıant:: operator = =

`CComVariant` Nesnenin belirtilen varyanta eşit olup olmadığını gösterir.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

*VarSrc* değeri ve türü, sırasıyla `CComVariant` değerine eşitse true değerini döndürür. Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

İşleci yalnızca değişken türlerinin değerini karşılaştırır. Dizeleri, tamsayıları ve kayan noktaları karşılaştırır, ancak dizileri veya kayıtları karşılaştırır.

##  <a name="operator_neq"></a>Ccomvarıant:: operator! =

`CComVariant` Nesnenin belirtilen varyanta eşit olup olmadığını gösterir.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

*VarSrc* değeri veya türü, sırasıyla `CComVariant` nesne değerine veya türüne eşit değilse true döndürür. Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

İşleci yalnızca değişken türlerinin değerini karşılaştırır. Dizeleri, tamsayıları ve kayan noktaları karşılaştırır, ancak dizileri veya kayıtları karşılaştırır.

##  <a name="operator_lt"></a>CComVariant:: işleci&lt;

`CComVariant` Nesnenin belirtilen VARIANT 'tan daha az olup olmadığını gösterir.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

`CComVariant` Nesnenin değeri *varSrc*değerinden küçükse true değerini döndürür. Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

##  <a name="operator_gt"></a>CComVariant:: işleci&gt;

`CComVariant` Nesnenin belirtilen değişkenden daha büyük olup olmadığını gösterir.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

`CComVariant` Nesnenin değeri *varSrc*değerinden büyükse true değerini döndürür. Aksi takdirde, FALSE. İşleci, karşılaştırmayı gerçekleştirmek için kullanıcının varsayılan yerel ayarını kullanır.

##  <a name="readfromstream"></a>CComVariant:: ReadFromStream

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

##  <a name="setbyref"></a>CComVariant:: SetByRef

Nesnesini başlatır ve `vt` üyeyi VT_BYREF olarak ayarlar. `CComVariant`

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Parametreler

*ŞI*<br/>
DEĞIŞKEN türü, örneğin, BSTR, **int**veya **char**.

*Yönergelerinin*<br/>
`CComVariant` Nesneyi başlatmak için kullanılan işaretçi.

### <a name="remarks"></a>Açıklamalar

`SetByRef`, `CComVariant` nesneyi işaretçi *PT* olarak başlatan ve `vt` üyeyi VT_BYREF olarak ayarlayan bir işlev şablonudur. Örneğin:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>CComVariant:: WriteToStream

Temel varyansı bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Akıştaki IStream arabirimine [](/windows/win32/api/objidl/nn-objidl-istream) yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
