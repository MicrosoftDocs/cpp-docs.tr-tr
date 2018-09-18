---
title: CUrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
dev_langs:
- C++
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0ab7906961936239ac564137d0760e6d64de9de
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068227"
---
# <a name="curl-class"></a>CUrl sınıfı

Bu sınıf, bir URL temsil eder. Var olan bir URL Ayrıştırma olup olmadığını her öğeyi diğerlerinden URL'sinin düzenlemesini sağlar dize veya bir dize sıfırdan oluşturma.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CUrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CUrl::CUrl](#curl)|Oluşturucu.|
|[CUrl:: ~ CUrl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CUrl::Canonicalize](#canonicalize)|URL dizesi kurallı biçimine dönüştürmek için bu yöntemi çağırın.|
|[CUrl::Clear](#clear)|URL alanların tümünü temizlemek için bu yöntemi çağırın.|
|[CUrl::CrackUrl](#crackurl)|Kod çözme ve URL ayrıştırmak için bu yöntemi çağırın.|
|[CUrl::CreateUrl](#createurl)|URL oluşturmak için bu yöntemi çağırın.|
|[CUrl::GetExtraInfo](#getextrainfo)|Ek bilgi almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den.|
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Ek bilgi uzunluğunu almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den alınacak.|
|[CUrl::GetHostName](#gethostname)|URL ana bilgisayar adını almak için bu yöntemi çağırın.|
|[CUrl::GetHostNameLength](#gethostnamelength)|Ana bilgisayar adı uzunluğunu almak için bu yöntemi çağırın.|
|[CUrl::GetPassword](#getpassword)|URL'den parolasını almak için bu yöntemi çağırın.|
|[CUrl::GetPasswordLength](#getpasswordlength)|Parola uzunluğunu almak için bu yöntemi çağırın.|
|[CUrl::GetPortNumber](#getportnumber)|Bağlantı noktası numarasını ATL_URL_PORT açısından almak için bu yöntemi çağırın.|
|[CUrl::GetScheme](#getscheme)|URL düzeni almak için bu yöntemi çağırın.|
|[CUrl::GetSchemeName](#getschemename)|URL düzen adını almak için bu yöntemi çağırın.|
|[CUrl::GetSchemeNameLength](#getschemenamelength)|URL düzeni adı uzunluğunu almak için bu yöntemi çağırın.|
|[CUrl::GetUrlLength](#geturllength)|URL uzunluğu almak için bu yöntemi çağırın.|
|[CUrl::GetUrlPath](#geturlpath)|URL yolu almak için bu yöntemi çağırın.|
|[CUrl::GetUrlPathLength](#geturlpathlength)|URL yolu uzunluğu almak için bu yöntemi çağırın.|
|[CUrl::GetUserName](#getusername)|URL'SİNDEN kullanıcı adını almak için bu yöntemi çağırın.|
|[CUrl::GetUserNameLength](#getusernamelength)|Kullanıcı adının uzunluğu almak için bu yöntemi çağırın.|
|[CUrl::SetExtraInfo](#setextrainfo)|Ek bilgi için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'si.|
|[CUrl::SetHostName](#sethostname)|Konak adı ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetPassword](#setpassword)|Parolayı ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetPortNumber](#setportnumber)|Bağlantı noktası numarasını ATL_URL_PORT açısından ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetScheme](#setscheme)|URL düzeni ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetSchemeName](#setschemename)|URL düzeni adı ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetUrlPath](#seturlpath)|URL yolunu ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetUserName](#setusername)|Kullanıcı adı ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CUrl::operator =](#operator_eq)|Belirtilen atar `CUrl` geçerli nesneye `CUrl` nesne.|

## <a name="remarks"></a>Açıklamalar

`CUrl` yol veya bağlantı noktası numarası gibi bir URL alanlarını yönetmenize olanak sağlar. `CUrl` Aşağıdaki biçimindeki URL'ler anlar:

\<Düzeni > ://\<kullanıcı adı >:\<parola >\@\<ana bilgisayar adı >:\<PortNumber > /\<UrlPath >\<ExtraInfo >

(Bazı alanlar isteğe bağlıdır.) Örneğin, bu URL'yi göz önünde bulundurun:

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[CUrl::CrackUrl](#crackurl) gibi ayrıştırır:

- Düzeni: "http" veya [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- Kullanıcı adı: "kişi"

- Parola: "gizli"

- Ana bilgisayar adı: "`www.microsoft.com`"

- PortNumber: 80

- UrlPath: "visualc/stuff.htm"

- ExtraInfo: "#contents"

UrlPath alanın (örneğin) işlemek için kullanacağınız [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), ve [SetUrlPath](#seturlpath). Kullanacağınız [CreateUrl](#createurl) tam URL dizesi oluşturmak için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

##  <a name="canonicalize"></a>  CUrl::Canonicalize

URL dizesi kurallı biçimine dönüştürmek için bu yöntemi çağırın.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Standartlaştırma denetleyen bayraklar. Bayrak belirtilmezse (*CertOpenStore* = 0), tüm güvenli olmayan karakterleri ve meta dizileri yöntemi dönüştürür (gibi \\., \.., ve \\...) kaçış dizileri. *CertOpenStore* aşağıdaki değerlerden biri olabilir:

- ATL_URL_BROWSER_MODE: Kodlama etmez veya karakter kodunu çözme sonra: "#" veya "" ve boşluk sonra kaldırmaz "". Bu değer belirtilmezse, URL'nin tamamını kodlanır ve boşluk kaldırılır.

- ATL_URL _DECODE: tüm % XX dizileri URL ayrıştırılmadan önce kaçış dizileri içeren karaktere dönüştürür.

- ATL_URL _ENCODE_PERCENT: karşılaştı herhangi bir yüzde işaretleri kodlar. Varsayılan olarak, yüzde işaretleri kodlanmaz.

- ATL_URL _ENCODE_SPACES_ONLY: yalnızca boşluk kodlar.

- ATL_URL _NO_ENCODE: Güvenli olmayan karakterleri kaçış sıralarına dönüştürmez.

- ATL_URL _NO_META: meta dizileri kaldırmaz (gibi "."ve"...") URL'sinden.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Kurallı biçimine dönüştürmeyi, güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içerir.

##  <a name="clear"></a>  CUrl::Clear

URL alanların tümünü temizlemek için bu yöntemi çağırın.

```
inline void Clear() throw();
```

##  <a name="crackurl"></a>  CUrl::CrackUrl

Kod çözme ve URL ayrıştırmak için bu yöntemi çağırın.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*lpszUrl*<br/>
URL.

*CertOpenStore*<br/>
Tüm çıkış karakterlerinin tanınmasından dönüştürülecek ATL_URL_DECODE veya ATL_URL_ESCAPE belirtin *lpszUrl* gerçek değerlerine ayrıştırma sonra. (Visual C++ 2005'den önce ATL_URL_DECODE tüm kaçış karakterleri ayrıştırma önce dönüştürülür.)

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="createurl"></a>  CUrl::CreateUrl

Bu yöntem bir CUrl nesnenin bileşen alanlardan bir URL dizesi oluşturur.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Parametreler

*lpszUrl*<br/>
Tam URL dizesi tutmak için bir dize arabelleği.

*pdwMaxLength*<br/>
En büyük uzunluğunu *lpszUrl* dizesi arabelleği.

*CertOpenStore*<br/>
Tüm çıkış karakterlerinin tanınmasından dönüştürülecek ATL_URL_ESCAPE belirtin *lpszUrl* gerçek değerlerine.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, aşağıdaki biçimi kullanarak eksiksiz bir URL dizesi oluşturmak için her bir alanı ekler:

**\<düzeni > ://\<kullanıcı >:\<geçirmek >\@\<etki alanı >:\<bağlantı noktası >\<yolu >\<ek >**

Bu yöntem çağrılırken *pdwMaxLength* parametresi tarafından başvurulan dize arabelleğinin en büyük uzunluğu başlangıçta içermelidir *lpszUrl* parametresi. Değerini *pdwMaxLength* parametresi gerçek URL dize uzunluğu ile güncelleştirilir.

### <a name="example"></a>Örnek

Bu örnek, bir CUrl nesnesi ve onun URL dizesi alınırken oluşturulmasını gösterir.

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

##  <a name="curl"></a>  CUrl::CUrl

Oluşturucu.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametreler

*urlThat*<br/>
`CUrl` URL'yi oluşturmak için nesne.

##  <a name="dtor"></a>  CUrl:: ~ CUrl

Yıkıcı.

```
~CUrl() throw();
```

##  <a name="getextrainfo"></a>  CUrl::GetExtraInfo

Ek bilgi almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ek bilgi içeren bir dize döndürür.

##  <a name="getextrainfolength"></a>  CUrl::GetExtraInfoLength

Ek bilgi uzunluğunu almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den alınacak.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ek bilgi içeren dize uzunluğunu döndürür.

##  <a name="gethostname"></a>  CUrl::GetHostName

URL ana bilgisayar adını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar adını döndürür.

##  <a name="gethostnamelength"></a>  CUrl::GetHostNameLength

Ana bilgisayar adı uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Konak adı uzunluğunu döndürür.

##  <a name="getpassword"></a>  CUrl::GetPassword

URL'den parolasını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parolayı döndürür.

##  <a name="getpasswordlength"></a>  CUrl::GetPasswordLength

Parola uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parola uzunluğunu döndürür.

##  <a name="getportnumber"></a>  CUrl::GetPortNumber

Bağlantı noktası numarasını almak için bu yöntemi çağırın.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı noktası numarasını döndürür.

##  <a name="getscheme"></a>  CUrl::GetScheme

URL düzeni almak için bu yöntemi çağırın.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür [ATL_URL_SCHEME](atl-url-scheme-enum.md) URL düzeni açıklayan değeri.

##  <a name="getschemename"></a>  CUrl::GetSchemeName

URL düzen adını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL düzeni adı (örneğin, "http" veya "ftp") döndürür.

##  <a name="getschemenamelength"></a>  CUrl::GetSchemeNameLength

URL düzeni adı uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL düzeni adı uzunluğunu döndürür.

##  <a name="geturllength"></a>  CUrl::GetUrlLength

URL uzunluğu almak için bu yöntemi çağırın.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL uzunluğu döndürür.

##  <a name="geturlpath"></a>  CUrl::GetUrlPath

URL yolu almak için bu yöntemi çağırın.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL yolu döndürür.

##  <a name="geturlpathlength"></a>  CUrl::GetUrlPathLength

URL yolu uzunluğu almak için bu yöntemi çağırın.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL yol uzunluğunu döndürür.

##  <a name="getusername"></a>  CUrl::GetUserName

URL'SİNDEN kullanıcı adını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı adını döndürür.

##  <a name="getusernamelength"></a>  CUrl::GetUserNameLength

Kullanıcı adının uzunluğu almak için bu yöntemi çağırın.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı adının uzunluğu döndürür.

##  <a name="operator_eq"></a>  CUrl::operator =

Belirtilen atar `CUrl` geçerli nesneye `CUrl` nesne.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametreler

*urlThat*<br/>
`CUrl` Nesne geçerli nesneye kopyalanacak.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru döndürür.

##  <a name="setextrainfo"></a>  CUrl::SetExtraInfo

Ek bilgi için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'si.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Parametreler

*lpszInfo*<br/>
URL'de dahil edilecek ek bilgileri içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="sethostname"></a>  CUrl::SetHostName

Konak adı ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Parametreler

*lpszHost*<br/>
Konak adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="setpassword"></a>  CUrl::SetPassword

Parolayı ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Parametreler

*lpszPass*<br/>
Parola.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="setportnumber"></a>  CUrl::SetPortNumber

Bağlantı noktası numarasını ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Parametreler

*nPrt*<br/>
Bağlantı noktası numarası.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="setscheme"></a>  CUrl::SetScheme

URL düzeni ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Parametreler

*nScheme*<br/>
Aşağıdakilerden birini [ATL_URL_SCHEME](atl-url-scheme-enum.md) düzeni için değerler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Ada göre düzeni de ayarlayabilirsiniz (bkz [CUrl::SetSchemeName](#setschemename)).

##  <a name="setschemename"></a>  CUrl::SetSchemeName

URL düzeni adı ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSchm*<br/>
URL Düzen adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanarak düzeni de ayarlayabilirsiniz bir [ATL_URL_SCHEME](atl-url-scheme-enum.md) sabit (bkz [CUrl::SetScheme](#setscheme)).

##  <a name="seturlpath"></a>  CUrl::SetUrlPath

URL yolunu ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
URL yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="setusername"></a>  CUrl::SetUserName

Kullanıcı adı ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Parametreler

*lpszUser*<br/>
Kullanıcı adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../atl/reference/atl-classes.md)
