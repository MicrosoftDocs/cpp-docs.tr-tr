---
title: CUrl Sınıfı
ms.date: 05/06/2019
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
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
ms.openlocfilehash: 3468e17b031d0a72bc56d915c689fbe4c78859e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330483"
---
# <a name="curl-class"></a>CUrl Sınıfı

Bu sınıf bir URL'yi temsil eder. Varolan bir URL dizesini ayrıştırmak veya sıfırdan bir dize oluşturmak olsun, URL'nin her öğesini diğerlerinden bağımsız olarak işlemenizi sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CUrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CUrl::curl](#curl)|Oluşturucu.|
|[CUrl::~CUrl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CUrl::Canonicalize](#canonicalize)|URL dizesini kanonik forma dönüştürmek için bu yöntemi arayın.|
|[CUrl::Açık](#clear)|Tüm URL alanlarını temizlemek için bu yöntemi arayın.|
|[CUrl::Crackurl](#crackurl)|URL'yi çözmek ve ayrıştmak için bu yöntemi arayın.|
|[CUrl::CreateUrl](#createurl)|URL'yi oluşturmak için bu yöntemi arayın.|
|[Curl::GetExtraInfo](#getextrainfo)|URL'den ek bilgi *(metin* veya # *metin*gibi) almak için bu yöntemi arayın.|
|[Curl::GetExtraInfoLength](#getextrainfolength)|URL'den almak için ek bilgilerin *(metin* veya # *metni*gibi) uzunluğunu almak için bu yöntemi arayın.|
|[CUrl::GetHostName](#gethostname)|Ana bilgisayar adını URL'den almak için bu yöntemi arayın.|
|[CUrl::GetHostNameLength](#gethostnamelength)|Ana bilgisayar adının uzunluğunu almak için bu yöntemi arayın.|
|[CUrl::Şifre Alma](#getpassword)|Parolayı URL'den almak için bu yöntemi arayın.|
|[CUrl::Parola Boyu Alma](#getpasswordlength)|Parolanın uzunluğunu almak için bu yöntemi arayın.|
|[CUrl::GetPortNumber](#getportnumber)|ATL_URL_PORT açısından bağlantı noktası numarasını almak için bu yöntemi arayın.|
|[CUrl::GetScheme](#getscheme)|URL düzenini almak için bu yöntemi arayın.|
|[CUrl::GetSchemeName](#getschemename)|URL düzeni adını almak için bu yöntemi arayın.|
|[CUrl::GetSchemeNameLength](#getschemenamelength)|URL düzeni adının uzunluğunu almak için bu yöntemi arayın.|
|[CUrl::GetUrllength](#geturllength)|URL uzunluğunu almak için bu yöntemi arayın.|
|[CUrl::GetUrlpath](#geturlpath)|URL yolunu almak için bu yöntemi arayın.|
|[CUrl::GetUrlPathLength](#geturlpathlength)|URL yol uzunluğunu almak için bu yöntemi arayın.|
|[CUrl::GetUserName](#getusername)|Kullanıcı adını URL'den almak için bu yöntemi arayın.|
|[CUrl::GetUserNameLength](#getusernamelength)|Kullanıcı adının uzunluğunu almak için bu yöntemi arayın.|
|[CUrl:SetExtraInfo](#setextrainfo)|URL'nin ek bilgilerini *(metin* veya # *metni*gibi) ayarlamak için bu yöntemi arayın.|
|[CUrl::SetHostName](#sethostname)|Ana bilgisayar adını ayarlamak için bu yöntemi çağırın.|
|[CUrl::SetPassword](#setpassword)|Parolayı ayarlamak için bu yöntemi arayın.|
|[CUrl::SetPortNumber](#setportnumber)|Bağlantı noktası numarasını ATL_URL_PORT olarak ayarlamak için bu yöntemi arayın.|
|[CUrl::SetScheme](#setscheme)|URL düzenini ayarlamak için bu yöntemi arayın.|
|[CUrl::SetSchemeName](#setschemename)|URL düzeni adını ayarlamak için bu yöntemi arayın.|
|[CUrl::Seturlpath](#seturlpath)|URL yolunu ayarlamak için bu yöntemi arayın.|
|[CUrl::SetUserName](#setusername)|Kullanıcı adını ayarlamak için bu yöntemi arayın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CUrl::operator =](#operator_eq)|Belirtilen `CUrl` nesneyi geçerli `CUrl` nesneye atar.|

## <a name="remarks"></a>Açıklamalar

`CUrl`yol veya bağlantı noktası numarası gibi bir URL'nin alanlarını işlemenizi sağlar. `CUrl`aşağıdaki formun URL'lerini anlar:

\<Şema\<>:// Kullanıcı\<Adı \@ \<>:\<Password>\<HostName \<>: PortNumber>/ UrlPath>ExtraInfo>

(Bazı alanlar isteğe bağlıdır.) Örneğin, bu URL'yi göz önünde bulundurun:

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[CUrl::CrackUrl](#crackurl) aşağıdaki gibi parses:

- Şema: "http" veya [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- Kullanıcı Adı: "birisi"

- Şifre: "gizli"

- Ev Sahibi`www.microsoft.com`Adı: " "

- Bağlantı Noktası Sayısı: 80

- UrlPath: "visualc/stuff.htm"

- ExtraInfo: "#contents"

UrlPath alanını işlemek için (örneğin), [GetUrlPath,](#geturlpath) [GetUrlPathLength](#geturlpathlength)ve [SetUrlPath'i](#seturlpath)kullanırsınız. Tam URL dizesini oluşturmak için [CreateUrl'yi](#createurl) kullanırsınız.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a>CUrl::Canonicalize

URL dizesini kanonik forma dönüştürmek için bu yöntemi arayın.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Kanoniizasyonu kontrol eden bayraklar. Bayrak belirtilmemişse *(dwFlags* = 0), yöntem tüm güvenli olmayan karakterleri ve \\meta dizilerini (.,\ .., ve \\...) dizilerden kaçmak için dönüştürür. *dwFlags* aşağıdaki değerlerden biri olabilir:

- ATL_URL_BROWSER_MODE: Karakterleri "#" veya "" sonradan kodlamaz veya çözmez ve ""'den sonra beyaz boşluğu kaldırmaz. Bu değer belirtilmemişse, URL'nin tamamı kodlanır ve sondaki beyaz alan kaldırılır.

- ATL_URL _DECODE: URL ayrıştırılmadan önce tüm %XX dizilerini kaçış sekansları da dahil olmak üzere karakterlere dönüştürür.

- ATL_URL _ENCODE_PERCENT: Karşılaşılan yüzde işaretleri kodlar. Varsayılan olarak, yüzde işaretleri kodlanmaz.

- ATL_URL _ENCODE_SPACES_ONLY: Yalnızca boşlukları kodlar.

- ATL_URL _NO_ENCODE: Güvenli olmayan karakterleri kaçış dizilerine dönüştürmez.

- ATL_URL _NO_META: Meta dizilerini ("." ve "..") URL'den kaldırmaz.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Kanonik forma dönüştürme, güvenli olmayan karakterleri ve alanları dizilerden kaçmak için dönüştürmeyi içerir.

## <a name="curlclear"></a><a name="clear"></a>CUrl::Açık

Tüm URL alanlarını temizlemek için bu yöntemi arayın.

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a>CUrl::Crackurl

URL'yi çözmek ve ayrıştmak için bu yöntemi arayın.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
The URL.

*Dwflags*<br/>
*LpszUrl'deki* tüm kaçış karakterlerini ayrıştırma sonra gerçek değerlerine dönüştürmek için ATL_URL_DECODE veya ATL_URL_ESCAPE belirtin. (Visual C++ 2005'ten önce ATL_URL_DECODE, ayrıştırmadan önce tüm kaçış karakterlerini dönüştürer.)

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="curlcreateurl"></a><a name="createurl"></a>CUrl::CreateUrl

Bu yöntem, curl nesnenin bileşen alanlarından bir URL dizesi oluşturuyor.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
TAM URL dizesini tutmak için bir dize arabelleği.

*pdwMaxLength*<br/>
*lpszUrl* dize arabelleği maksimum uzunluğu.

*Dwflags*<br/>
*LpszUrl'deki* tüm kaçış karakterlerini gerçek değerlerine dönüştürmek için ATL_URL_ESCAPE belirtin.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, aşağıdaki biçimi kullanarak tam URL dizesini oluşturmak için tek tek alanlarını ekler:

**\<şema\<>://\<kullanıcı \@ \<>:\<>\<etki \<> geçmek: port>yolu>ekstra>**

Bu yöntemi ararken, *pdwMaxLength* parametresi başlangıçta *lpszUrl* parametresi tarafından başvurulan dize arabelleği maksimum uzunluğunu içermelidir. *pdwMaxLength* parametresinin değeri URL dizesinin gerçek uzunluğuyla güncelleştirilir.

### <a name="example"></a>Örnek

Bu örnek, bir CUrl nesnesinin oluşturulmasını ve URL dizesini alma

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a>CUrl::curl

Oluşturucu.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametreler

*urlThat*<br/>
URL'yi `CUrl` oluşturmak için kopyalanması gereken nesne.

## <a name="curlcurl"></a><a name="dtor"></a>CUrl::~CUrl

Yıkıcı.

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a>Curl::GetExtraInfo

URL'den ek bilgi *(metin* veya # *metin*gibi) almak için bu yöntemi arayın.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ek bilgileri içeren bir dize döndürür.

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a>Curl::GetExtraInfoLength

URL'den almak için ek bilgilerin *(metin* veya # *metni*gibi) uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ek bilgileri içeren dize uzunluğunu döndürür.

## <a name="curlgethostname"></a><a name="gethostname"></a>CUrl::GetHostName

Ana bilgisayar adını URL'den almak için bu yöntemi arayın.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar adını döndürür.

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a>CUrl::GetHostNameLength

Ana bilgisayar adının uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar ad uzunluğunu verir.

## <a name="curlgetpassword"></a><a name="getpassword"></a>CUrl::Şifre Alma

Parolayı URL'den almak için bu yöntemi arayın.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parolayı döndürür.

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a>CUrl::Parola Boyu Alma

Parolanın uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parola uzunluğunu döndürür.

## <a name="curlgetportnumber"></a><a name="getportnumber"></a>CUrl::GetPortNumber

Bağlantı noktası numarasını almak için bu yöntemi arayın.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı noktası numarasını verir.

## <a name="curlgetscheme"></a><a name="getscheme"></a>CUrl::GetScheme

URL düzenini almak için bu yöntemi arayın.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL düzenini açıklayan [ATL_URL_SCHEME](atl-url-scheme-enum.md) değerini döndürür.

## <a name="curlgetschemename"></a><a name="getschemename"></a>CUrl::GetSchemeName

URL düzeni adını almak için bu yöntemi arayın.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL düzeni adını döndürür ("http" veya "ftp" gibi).

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a>CUrl::GetSchemeNameLength

URL düzeni adının uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL düzeni ad uzunluğunu verir.

## <a name="curlgeturllength"></a><a name="geturllength"></a>CUrl::GetUrllength

URL uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL uzunluğunu verir.

## <a name="curlgeturlpath"></a><a name="geturlpath"></a>CUrl::GetUrlpath

URL yolunu almak için bu yöntemi arayın.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL yolunu döndürür.

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a>CUrl::GetUrlPathLength

URL yol uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL yol uzunluğunu döndürür.

## <a name="curlgetusername"></a><a name="getusername"></a>CUrl::GetUserName

Kullanıcı adını URL'den almak için bu yöntemi arayın.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı adını döndürür.

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a>CUrl::GetUserNameLength

Kullanıcı adının uzunluğunu almak için bu yöntemi arayın.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı adı uzunluğunu verir.

## <a name="curloperator-"></a><a name="operator_eq"></a>CUrl::operator =

Belirtilen `CUrl` nesneyi geçerli `CUrl` nesneye atar.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametreler

*urlThat*<br/>
Geçerli `CUrl` nesneye kopyalanması gereken nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru verir.

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a>CUrl:SetExtraInfo

URL'nin ek bilgilerini *(metin* veya # *metni*gibi) ayarlamak için bu yöntemi arayın.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Parametreler

*lpszInfo*<br/>
URL'ye ekecek ek bilgileri içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="curlsethostname"></a><a name="sethostname"></a>CUrl::SetHostName

Ana bilgisayar adını ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Parametreler

*lpszHost*<br/>
Ana bilgisayar adı.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="curlsetpassword"></a><a name="setpassword"></a>CUrl::SetPassword

Parolayı ayarlamak için bu yöntemi arayın.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Parametreler

*lpszPass*<br/>
Parola.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="curlsetportnumber"></a><a name="setportnumber"></a>CUrl::SetPortNumber

Bağlantı noktası numarasını ayarlamak için bu yöntemi arayın.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Parametreler

*nPrt*<br/>
Bağlantı noktası numarası.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="curlsetscheme"></a><a name="setscheme"></a>CUrl::SetScheme

URL düzenini ayarlamak için bu yöntemi arayın.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Parametreler

*nŞeki*<br/>
Şema için [ATL_URL_SCHEME](atl-url-scheme-enum.md) değerlerinden biri.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Düzeni ada göre de ayarlayabilirsiniz (bkz. [CUrl::SetSchemeName).](#setschemename)

## <a name="curlsetschemename"></a><a name="setschemename"></a>CUrl::SetSchemeName

URL düzeni adını ayarlamak için bu yöntemi arayın.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSchm*<br/>
URL düzeni adı.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Şemayı [ATL_URL_SCHEME](atl-url-scheme-enum.md) sabiti kullanarak da ayarlayabilirsiniz [(bkz. CUrl:SetScheme).](#setscheme)

## <a name="curlseturlpath"></a><a name="seturlpath"></a>CUrl::Seturlpath

URL yolunu ayarlamak için bu yöntemi arayın.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
URL yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="curlsetusername"></a><a name="setusername"></a>CUrl::SetUserName

Kullanıcı adını ayarlamak için bu yöntemi arayın.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Parametreler

*lpszUser*<br/>
Kullanıcı adı.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)
