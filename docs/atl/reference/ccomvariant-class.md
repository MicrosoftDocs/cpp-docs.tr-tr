---
title: CComVariant Sınıfı
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
ms.openlocfilehash: 9a84d91e20242fb206d1d3f71fcb3dd207561f62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327224"
---
# <a name="ccomvariant-class"></a>CComVariant Sınıfı

Bu sınıf, depolanan veri türünü belirten bir üye sağlayarak VARIANT türünü sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Kcomvariant::Ccomvariant](#ccomvariant)|Oluşturucu.|
|[Kcomvariant::~Ccomvariant](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Ccomvariant::Ekle](#attach)|`CComVariant` Nesneye bir VARYANT bağlar.|
|[Ccomvariant::changetype](#changetype)|Nesneyi `CComVariant` yeni bir türe dönüştürür.|
|[Ccomvariant::Clear](#clear)|Nesneyi `CComVariant` temizler.|
|[Ccomvariant::Kopyala](#copy)|Nesneye bir VARYANT `CComVariant` kopyalar.|
|[Ccomvariant::copyto](#copyto)|`CComVariant` Nesnenin içeriğini kopyalar.|
|[CComVariant::Detach](#detach)|Temel VARYANT'ı `CComVariant` nesneden ayırır.|
|[Ccomvariant::Getsize](#getsize)|`CComVariant` Nesnenin içeriğinin bayt sayısında boyutu döndürür.|
|[Ccomvariant::readfromstream](#readfromstream)|Bir akıştan varyant yükler.|
|[Ccomvariant::setbyref](#setbyref)|Nesneyi `CComVariant` başharfe ve `vt` üyeyi VT_BYREF ayarlar.|
|[Ccomvariant::Writetostream](#writetostream)|Temel VARYANT'ı bir akışa kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|||
|-|-|
|[CComVariant::operatör <](#operator_lt)|Nesnenin `CComVariant` belirtilen VARYANT'tan daha az olup olmadığını gösterir.|
|[CComVariant::operatör >](#operator_gt)|Nesnenin `CComVariant` belirtilen VARYANT'tan büyük olup olmadığını gösterir.|
|[işleç !=](#operator_neq)|Nesnenin `CComVariant` belirtilen VARYANT'a eşit olup olmadığını gösterir.|
|[işleç =](#operator_eq)|`CComVariant` Nesneye bir değer atar.|
|[işleç ==](#operator_eq_eq)|Nesnenin `CComVariant` belirtilen VARYANT'a eşit olup olmadığını gösterir.|

## <a name="remarks"></a>Açıklamalar

`CComVariant`bir sendika ve bir üyeden oluşan VARIANT ve VARIANTARG türünü sarar ve birsendikada depolanan verilerin türünü gösterir. VARIAN'lar genellikle Otomasyon'da kullanılır.

`CComVariant`varyantın kullanılabildiği her yerde kullanılabilen VARIANT türünden türetilmiştir. Örneğin, V_VT makroyu kullanarak a `CComVariant` türünü ayıklayabilir veya `vt` üyeye bir VARYANT'ta olduğu gibi doğrudan erişebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomcli.h

## <a name="ccomvariantattach"></a><a name="attach"></a>Ccomvariant::Ekle

Nesnenin `CComVariant` geçerli içeriğini güvenli bir şekilde temizler, *pSrc* içeriğini bu nesneye kopyalar, sonra *pSrc'nin* varyant türünü VT_EMPTY ayarlar.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
[içinde] Nesneye eklenecek [VARYANT'a](/windows/win32/api/oaidl/ns-oaidl-variant) işaret edilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*pSrc* tarafından tutulan verilerin sahipliği `CComVariant` nesneye aktarılır.

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a>Kcomvariant::Ccomvariant

Her `VariantInit` kurucu, Win32 işlevini `CComVariant` çağırarak veya nesnenin değerini ve türünü geçirilen parametrelere göre ayarlayarak nesnenin güvenli başlatılmasını işler.

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
[içinde] `CComVariant` Nesneyi `CComVariant` başlatmada kullanılan veya VARIANT. Kaynak varyantın içeriği dönüşüm olmadan hedefe kopyalanır.

*lpszSrc*<br/>
[içinde] `CComVariant` Nesneyi başlatmada kullanılan karakter dizesi. Sıfır sonlandırılmış geniş (Unicode) karakter dizesini oluşturucunun LPCOLESTR sürümüne veya LPCSTR sürümüne bir ANSI dizesi geçirebilirsiniz. Her iki durumda da dize kullanılarak `SysAllocString`ayrılan Unicode BSTR dönüştürülür. `CComVariant` Nesnenin türü VT_BSTR.

*bSrc*<br/>
[içinde] `CComVariant` Nesneyi başharfe almak için kullanılan **bool.** **Bool** bağımsız değişkeni depolanmadan önce VARIANT_BOOL dönüştürülür. Nesnenin `CComVariant` türü VT_BOOL.

*nSrc*<br/>
[içinde] **Int**, **BYTE**, **kısa**, **uzun**, LONGLONG, ULONGLONG, **imzasız kısa**, **imzasız uzun**, veya **imzasız int** `CComVariant` nesnenin başlatılması için kullanılır. `CComVariant` Nesnenin türü sırasıyla VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4 olacaktır.

*vtSrc*<br/>
[içinde] Varyantın türü. İlk parametre **int**olduğunda, geçerli türleri VT_I4 ve VT_INT. İlk parametre **uzun**olduğunda, geçerli türleri VT_I4 ve VT_ERROR. İlk parametre **çift**olduğunda, geçerli türleri VT_R8 ve VT_DATE. İlk parametre **imzasız int**olduğunda, geçerli türleri VT_UI4 ve VT_UINT.

*fltSrc*<br/>
[içinde] `CComVariant` Nesneyi başlatmada kullanılan **şamandıra.** `CComVariant` Nesnenin türü VT_R4.

*dblSrc*<br/>
[içinde] `CComVariant` Nesneyi başlatmada kullanılan **çift.** `CComVariant` Nesnenin türü VT_R8.

*cySrc*<br/>
[içinde] Nesneyi `CY` başlatmak `CComVariant` için kullanılır. Nesnenin `CComVariant` türü VT_CY.

*pSrc*<br/>
[içinde] Nesneyi `IDispatch` başlatmada kullanılan işaretçi. `IUnknown` `CComVariant` `AddRef`arabirim işaretçisi üzerinde çağrılacaktır. `CComVariant` Nesnenin türü sırasıyla VT_DISPATCH veya VT_UNKNOWN olacaktır.

Veya nesneyi başlatmada kullanılan SAFERRAY işaretçisi. `CComVariant` SAFEARRAY'in bir kopyası `CComVariant` nesnede depolanır. `CComVariant` Nesnenin türü SAFEARRAY ve VT_ARRAY orijinal türü bir arada olacaktır.

*Csrc*<br/>
[içinde] **Char** nesneyi başlatmaiçin `CComVariant` kullanılır. Nesnenin `CComVariant` türü VT_I1.

*bstrSrc*<br/>
[içinde] BSTR nesneyi başlatmak `CComVariant` için kullanılır. `CComVariant` Nesnenin türü VT_BSTR.

### <a name="remarks"></a>Açıklamalar

Yıkıcı CComVariant arayarak temizleme [yönetir::Clear](#clear).

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a>Kcomvariant::~Ccomvariant

Yıkıcı.

```
~CComVariant() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem CComVariant çağırarak temizleme [yönetir::Temizleyin](#clear).

## <a name="ccomvariantchangetype"></a><a name="changetype"></a>Ccomvariant::changetype

Nesneyi `CComVariant` yeni bir türe dönüştürür.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*vtYeni*<br/>
[içinde] `CComVariant` Nesne için yeni tür.

*pSrc*<br/>
[içinde] Değeri yeni türe dönüştürülecek VARYANT için bir işaretçi. Varsayılan değer NULL'dur, `CComVariant` yani nesne yerine dönüştürülür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*Eğer pSrc*için bir `ChangeType` değer geçerseniz, dönüştürme için kaynak olarak bu VARIANT kullanır. Aksi takdirde, `CComVariant` nesne kaynak olacaktır.

## <a name="ccomvariantclear"></a><a name="clear"></a>Ccomvariant::Clear

Win32 `CComVariant` işlevini çağırarak nesneyi temizler. `VariantClear`

```
HRESULT Clear();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yıkıcı otomatik olarak çağırır. `Clear`

## <a name="ccomvariantcopy"></a><a name="copy"></a>Ccomvariant::Kopyala

Nesneyi `CComVariant` serbest bırakıp, belirtilen VARYANT'ın bir kopyasını atar.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Parametreler

*pSrc*<br/>
[içinde] [VARYANT'ın](/windows/win32/api/oaidl/ns-oaidl-variant) kopyalanacak bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomvariantcopyto"></a><a name="copyto"></a>Ccomvariant::copyto

`CComVariant` Nesnenin içeriğini kopyalar.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Parametreler

*pstrDest*<br/>
Nesnenin içeriğinin bir kopyasını alacak bir BSTR'ye işaret eder. `CComVariant`

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Nesne `CComVariant` VT_BSTR türünde olmalıdır.

## <a name="ccomvariantdetach"></a><a name="detach"></a>CComVariant::Detach

Alttaki VARYANT'ı `CComVariant` nesneden ayırır ve nesnenin türünü VT_EMPTY ayarlar.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
[çıkış] Nesnenin temel VARYANT değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*pDest* tarafından başvurulan VARIANT içeriğinin, çağrı `CComVariant` nesnesinin değeri ve türü atanmadan önce otomatik olarak temizleneceğini unutmayın.

## <a name="ccomvariantgetsize"></a><a name="getsize"></a>Ccomvariant::Getsize

Basit-sabit boyutlu VARIANT'lar için bu yöntem, temel veri türü artı **boyutlarını (VARTYPE)** **döndürür.**

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CComVariant` Nesnenin geçerli içeriğinin baytboyutu.

### <a name="remarks"></a>Açıklamalar

VARIANT bir arabirim işaretçisi içeriyorsa, `GetSize` sorgular veya `IPersistStream` `IPersistStreamInit`. Başarılı olursa, iade değeri, artı bir CLSID ve `GetSizeMax` **boyutlar (VARTYPE)** **tarafından** döndürülen değerin düşük sıralı 32 bit.'dir. Arabirim işaretçisi `GetSize` NULL ise, CLSID artı **boyut (VARTYPE)** **boyutlarını** döndürür. Toplam boyutu ULONG_MAX daha büyükse, `GetSize` hata yı gösteren **(VARTYPE) boyutlarını** döndürür.

Diğer tüm durumlarda, tip VT_BSTR geçici bir VARYANT geçerli VARYANT'tan zorla çıkarılır. Bu BSTR uzunluğu dize uzunluğu artı dize kendisi uzunluğu artı null karakter artı **boyutu (VARTYPE)** boyutu olarak hesaplanır. VARYANT, tür VT_BSTR varyantına zorlanamıyorsa, `GetSize` **(VARTYPE) boyutlarını**döndürür.

Bu yöntemle döndürülen boyut, CComVariant tarafından kullanılan bayt sayısıyla [eşleşir::WriteToStream](#writetostream) başarılı koşullar altında.

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a>CComVariant::operator =

`CComVariant` Nesneye bir değer ve karşılık gelen bir tür atar.

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
[içinde] `CComVariant` Nesneye `CComVariant` atanacak veya [VARYANT.](/windows/win32/api/oaidl/ns-oaidl-variant) Kaynak varyantın içeriği dönüşüm olmadan hedefe kopyalanır.

*bstrSrc*<br/>
[içinde] `CComVariant` Nesneye atanacak BSTR. `CComVariant` Nesnenin türü VT_BSTR.

*lpszSrc*<br/>
[içinde] Nesneye atanacak karakter `CComVariant` dizesi. Sıfır sonlandırılmış geniş (Unicode) karakter dizesini operatörün LPCOLESTR sürümüne veya LPCSTR sürümüne bir ANSI dizesi geçirebilirsiniz. Her iki durumda da, dize kullanılarak `SysAllocString`ayrılan Unicode BSTR dönüştürülür. `CComVariant` Nesnenin türü VT_BSTR.

*bSrc*<br/>
[içinde] `CComVariant` Nesneye atanacak **bool.** **Bool** bağımsız değişkeni depolanmadan önce VARIANT_BOOL dönüştürülür. Nesnenin `CComVariant` türü VT_BOOL.

*nSrc*<br/>
[içinde] **Int**, BYTE, **kısa**, **uzun**, LONGLONG, ULONGLONG, **imzasız kısa**, **imzasız uzun**, veya **imzasız int** `CComVariant` nesneye atanacak. `CComVariant` Nesnenin türü sırasıyla VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 veya VT_UI4 olacaktır.

*fltSrc*<br/>
[içinde] `CComVariant` Nesneye atanacak **şamandıra.** `CComVariant` Nesnenin türü VT_R4.

*dblSrc*<br/>
[içinde] `CComVariant` Nesneye atanacak **çift.** `CComVariant` Nesnenin türü VT_R8.

*cySrc*<br/>
[içinde] `CComVariant` Nesneye `CY` atanacak. Nesnenin `CComVariant` türü VT_CY.

*pSrc*<br/>
[içinde] Nesneye `IDispatch` atanacak işaretçi veya `IUnknown` işaretçi. `CComVariant` `AddRef`arabirim işaretçisi üzerinde çağrılacaktır. `CComVariant` Nesnenin türü sırasıyla VT_DISPATCH veya VT_UNKNOWN olacaktır.

Veya, nesneye atanacak bir `CComVariant` SAFEARRAY işaretçisi. SAFEARRAY'in bir kopyası `CComVariant` nesnede depolanır. `CComVariant` Nesnenin türü SAFEARRAY ve VT_ARRAY orijinal türü bir arada olacaktır.

*Csrc*<br/>
[içinde] `CComVariant` Nesneye atanacak char. Nesnenin `CComVariant` türü VT_I1.

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a>CComVariant::operator ==

Nesnenin `CComVariant` belirtilen VARYANT'a eşit olup olmadığını gösterir.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

*VarSrc* değeri ve türü `CComVariant` nesnenin değerine ve türüne eşitse TRUE döndürür. Aksi takdirde, YANLIŞ. İşletici karşılaştırma yı gerçekleştirmek için kullanıcının varsayılan yerel sini kullanır.

İşleç yalnızca varyant türlerinin değerini karşılaştırır. Dizeleri, tümsegerleri ve kayan noktaları karşılaştırır, ancak dizileri veya kayıtları karşılaştırır.

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a>CComVariant::operatör !=

Nesnenin `CComVariant` belirtilen VARYANT'a eşit olup olmadığını gösterir.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

*VarSrc* değeri veya türü `CComVariant` nesnenin değerine veya türüne eşit değilse TRUE döndürür. Aksi takdirde, YANLIŞ. İşletici karşılaştırma yı gerçekleştirmek için kullanıcının varsayılan yerel sini kullanır.

İşleç yalnızca varyant türlerinin değerini karşılaştırır. Dizeleri, tümsegerleri ve kayan noktaları karşılaştırır, ancak dizileri veya kayıtları karşılaştırır.

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a>CComVariant::operatör&lt;

Nesnenin `CComVariant` belirtilen VARYANT'tan daha az olup olmadığını gösterir.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnenin `CComVariant` değeri *varSrc*değerinden daha azsa TRUE döndürür. Aksi takdirde, YANLIŞ. İşletici karşılaştırma yı gerçekleştirmek için kullanıcının varsayılan yerel sini kullanır.

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a>CComVariant::operatör&gt;

Nesnenin `CComVariant` belirtilen VARYANT'tan büyük olup olmadığını gösterir.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnenin değeri `CComVariant` *varSrc*değerinden büyükse TRUE döndürür. Aksi takdirde, YANLIŞ. İşletici karşılaştırma yı gerçekleştirmek için kullanıcının varsayılan yerel sini kullanır.

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a>Ccomvariant::readfromstream

Altta yatan VARYANT'ı belirtilen akışta bulunan VARYANT'a ayarlar.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[içinde] Verileri içeren akıştaki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`ReadToStream`[WriteToStream](#writetostream)için önceki bir çağrı gerektirir.

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a>Ccomvariant::setbyref

Nesneyi `CComVariant` başharfe ve `vt` üyeyi VT_BYREF ayarlar.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
VARYANT türü, örneğin, BSTR, **int**, veya **char**.

*Pt*<br/>
Nesneyi başlatmaiçin kullanılan `CComVariant` işaretçi.

### <a name="remarks"></a>Açıklamalar

`SetByRef`nesneyi `CComVariant` işaretçi *pT'ye* açan ve üyeyi `vt` VT_BYREF ayarlayan bir işlev şablonudur. Örneğin:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a>Ccomvariant::Writetostream

Temel VARYANT'ı bir akışa kaydeder.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[içinde] Akış üzerindeki [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
