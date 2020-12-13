---
description: 'Daha fazla bilgi edinin: kıvrımlı sınıf'
title: Sınıf kıvır
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
ms.openlocfilehash: e8453c4dd1abbfdcb6d794b89fd55f37d7b3f286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140302"
---
# <a name="curl-class"></a>Sınıf kıvır

Bu sınıf bir URL 'YI temsil eder. Var olan bir URL dizesi ayrıştırıp veya sıfırdan dize oluşturarak, URL 'nin her bir öğesini diğerlerinden bağımsız olarak değiştirmenize olanak sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CUrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Kıvır:: kıvrık](#curl)|Oluşturucu.|
|[Kıvır:: ~ kıvır](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kıvır:: canonicalize](#canonicalize)|URL dizesini kurallı biçime dönüştürmek için bu yöntemi çağırın.|
|[Kıvat:: Clear](#clear)|Tüm URL alanlarını temizlemek için bu yöntemi çağırın.|
|[Kıvm:: Kırkurl](#crackurl)|URL kodunu çözmek ve ayrıştırmak için bu yöntemi çağırın.|
|[Kıvır:: CreateUrl](#createurl)|URL 'YI oluşturmak için bu yöntemi çağırın.|
|[Kıvma:: Getextraınfo](#getextrainfo)|URL 'den daha fazla bilgi (örneğin, *metin* veya # *metin*) almak için bu yöntemi çağırın.|
|[Kıvma:: Getextraınfolength](#getextrainfolength)|URL 'den alınacak ek bilgilerin (örneğin, *metin* veya # *metin*) uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetHostName](#gethostname)|URL 'den ana bilgisayar adını almak için bu yöntemi çağırın.|
|[Kıvır:: GetHostNameLength](#gethostnamelength)|Ana bilgisayar adının uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetPassword](#getpassword)|URL 'den parola almak için bu yöntemi çağırın.|
|[Kıvır:: GetPasswordLength](#getpasswordlength)|Parolanın uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetPortNumber](#getportnumber)|ATL_URL_PORT açısından bağlantı noktası numarasını almak için bu yöntemi çağırın.|
|[Kıvır:: GetScheme](#getscheme)|URL düzenini almak için bu yöntemi çağırın.|
|[Kıvma:: Getbir Mename](#getschemename)|URL düzeni adını almak için bu yöntemi çağırın.|
|[Kıvır:: GetSchemeNameLength](#getschemenamelength)|URL şeması adının uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetUrlLength](#geturllength)|URL uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetUrlPath](#geturlpath)|URL yolunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetUrlPathLength](#geturlpathlength)|URL yol uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvır:: GetUserName](#getusername)|URL 'den Kullanıcı adını almak için bu yöntemi çağırın.|
|[Kıvır:: GetUserNameLength](#getusernamelength)|Kullanıcı adının uzunluğunu almak için bu yöntemi çağırın.|
|[Kıvma:: Setextraınfo](#setextrainfo)|URL 'nin ek bilgilerini (örneğin, *metin* veya # *metin*) ayarlamak için bu yöntemi çağırın.|
|[Kıvat:: SetHostName](#sethostname)|Ana bilgisayar adını ayarlamak için bu yöntemi çağırın.|
|[Kıvır:: SetPassword](#setpassword)|Parolayı ayarlamak için bu yöntemi çağırın.|
|[Kıvır:: SetPortNumber](#setportnumber)|Bağlantı noktası numarasını ATL_URL_PORT göre ayarlamak için bu yöntemi çağırın.|
|[Kıvır:: SetScheme](#setscheme)|URL düzenini ayarlamak için bu yöntemi çağırın.|
|[Kıvma:: set, Mename](#setschemename)|URL düzeni adını ayarlamak için bu yöntemi çağırın.|
|[Kıvl:: SetUrlPath](#seturlpath)|URL yolunu ayarlamak için bu yöntemi çağırın.|
|[Kıvır:: SetUserName](#setusername)|Kullanıcı adını ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Kıvır:: operator =](#operator_eq)|Belirtilen `CUrl` nesneyi geçerli `CUrl` nesneye atar.|

## <a name="remarks"></a>Açıklamalar

`CUrl` yol veya bağlantı noktası numarası gibi bir URL 'nin alanlarını değiştirmenize izin verir. `CUrl` aşağıdaki formun URL 'Lerini anlamıştır:

\<Scheme>://\<UserName>:\<Password>\@\<HostName>:\<PortNumber>/\<UrlPath>\<ExtraInfo>

(Bazı alanlar isteğe bağlıdır.) Örneğin, şu URL 'YI göz önünde bulundurun:

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[Kıvrımlı:: Kırkurl](#crackurl) bunu aşağıdaki şekilde ayrıştırır:

- Düzen: "http" veya [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- Kullanıcı adı: "birisi"

- Parola: "gizli"

- Ana bilgisayar adı: " `www.microsoft.com` "

- PortNumber: 80

- UrlPath: "VisualC/stuff.htm"

- ExtraInfo: "#contents"

UrlPath alanını (örneğin) işlemek için [Geturlpath](#geturlpath), [geturlpathlength](#geturlpathlength)ve [seturlpath](#seturlpath)' i kullanacaksınız. URL dizgisini tamamen oluşturmak için [CreateUrl](#createurl) 'yi kullanırsınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a> Kıvır:: canonicalize

URL dizesini kurallı biçime dönüştürmek için bu yöntemi çağırın.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Kurallaştırma denetimini denetleyen bayraklar. Hiçbir bayrak belirtilmemişse (*dwFlags* = 0), yöntem güvenli olmayan tüm karakterleri ve meta dizileri (örn \\ ., \.., ve \\ ...) kaçış dizileri için dönüştürür. *dwFlags* aşağıdaki değerlerden biri olabilir:

- ATL_URL_BROWSER_MODE: "#" veya "" karakterinden sonra karakterleri kodlayıp kodu çözmez ve "" öğesinden sonra sondaki boşluğu kaldırmaz. Bu değer belirtilmezse, tüm URL kodlanır ve sondaki boşluk kaldırılır.

- ATL_URL _DECODE: tüm% XX dizilerini, URL ayrıştırmadan önce kaçış dizileri dahil olmak üzere karakterlere dönüştürür.

- ATL_URL _ENCODE_PERCENT: bir yüzde işaretinin kodlanma ile karşılaşıldı. Varsayılan olarak, yüzde işaretleri kodlanmaz.

- ATL_URL _ENCODE_SPACES_ONLY: yalnızca boşlukları kodlar.

- ATL_URL _NO_ENCODE: güvenli olmayan karakterleri kaçış sıralarına dönüştürmez.

- ATL_URL _NO_META: URL 'den meta dizileri ("." ve "..") kaldırmaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kurallı biçime dönüştürme, güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürmeyi içerir.

## <a name="curlclear"></a><a name="clear"></a> Kıvat:: Clear

Tüm URL alanlarını temizlemek için bu yöntemi çağırın.

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a> Kıvm:: Kırkurl

URL kodunu çözmek ve ayrıştırmak için bu yöntemi çağırın.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*lpszUrl*<br/>
URL.

*dwFlags*<br/>
*LpszURL* içindeki tüm kaçış karakterlerini ayrıştırdıktan sonra gerçek değerlerine dönüştürmek için ATL_URL_DECODE veya ATL_URL_ESCAPE belirtin. (Visual C++ 2005 önce ATL_URL_DECODE ayrıştırmadan önce tüm kaçış karakterlerini dönüştürüyordu.)

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="curlcreateurl"></a><a name="createurl"></a> Kıvır:: CreateUrl

Bu yöntem, bir kıvrımlı nesnenin bileşen alanlarından bir URL dizesi oluşturur.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Parametreler

*lpszUrl*<br/>
URL dizesinin tamamını tutan dize arabelleği.

*pdwMaxLength*<br/>
*LpszURL* dize arabelleğinin uzunluk üst sınırı.

*dwFlags*<br/>
*LpszURL* 'deki tüm kaçış karakterlerini gerçek değerlerine dönüştürmek için ATL_URL_ESCAPE belirtin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, aşağıdaki biçimi kullanarak tüm URL dizesini oluşturmak için ayrı alanlarını ekler:

**\<scheme>://\<user>:\<pass>\@\<domain>:\<port>\<path>\<extra>**

Bu yöntem çağrılırken, *pdwMaxLength* parametresi başlangıçta *lpszURL* parametresi tarafından başvurulan dize arabelleğinin uzunluk üst sınırını içermelidir. *PdwMaxLength* parametresinin DEĞERI, URL dizesinin gerçek uzunluğu ile güncelleştirilir.

### <a name="example"></a>Örnek

Bu örnek, bir kıvrımlı nesnenin oluşturulmasını ve URL dizesini almayı gösterir

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a> Kıvır:: kıvrık

Oluşturucu.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametreler

*Urla*<br/>
`CUrl`URL oluşturmak için kopyalanacak nesne.

## <a name="curlcurl"></a><a name="dtor"></a> Kıvır:: ~ kıvır

Yok edicisi.

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a> Kıvma:: Getextraınfo

URL 'den daha fazla bilgi (örneğin, *metin* veya # *metin*) almak için bu yöntemi çağırın.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ek bilgileri içeren bir dize döndürür.

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a> Kıvma:: Getextraınfolength

URL 'den alınacak ek bilgilerin (örneğin, *metin* veya # *metin*) uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ek bilgileri içeren dizenin uzunluğunu döndürür.

## <a name="curlgethostname"></a><a name="gethostname"></a> Kıvır:: GetHostName

URL 'den ana bilgisayar adını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar adını döndürür.

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a> Kıvır:: GetHostNameLength

Ana bilgisayar adının uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar adı uzunluğunu döndürür.

## <a name="curlgetpassword"></a><a name="getpassword"></a> Kıvır:: GetPassword

URL 'den parola almak için bu yöntemi çağırın.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parolayı döndürür.

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a> Kıvır:: GetPasswordLength

Parolanın uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parola uzunluğunu döndürür.

## <a name="curlgetportnumber"></a><a name="getportnumber"></a> Kıvır:: GetPortNumber

Bağlantı noktası numarasını almak için bu yöntemi çağırın.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı noktası numarasını döndürür.

## <a name="curlgetscheme"></a><a name="getscheme"></a> Kıvır:: GetScheme

URL düzenini almak için bu yöntemi çağırın.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL 'nin düzenini açıklayan [ATL_URL_SCHEME](atl-url-scheme-enum.md) değerini döndürür.

## <a name="curlgetschemename"></a><a name="getschemename"></a> Kıvma:: Getbir Mename

URL düzeni adını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL şeması adını döndürür (örneğin, "http" veya "FTP").

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a> Kıvır:: GetSchemeNameLength

URL şeması adının uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL şeması adı uzunluğunu döndürür.

## <a name="curlgeturllength"></a><a name="geturllength"></a> Kıvır:: GetUrlLength

URL uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL uzunluğunu döndürür.

## <a name="curlgeturlpath"></a><a name="geturlpath"></a> Kıvır:: GetUrlPath

URL yolunu almak için bu yöntemi çağırın.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL yolunu döndürür.

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a> Kıvır:: GetUrlPathLength

URL yol uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

URL yol uzunluğunu döndürür.

## <a name="curlgetusername"></a><a name="getusername"></a> Kıvır:: GetUserName

URL 'den Kullanıcı adını almak için bu yöntemi çağırın.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı adını döndürür.

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a> Kıvır:: GetUserNameLength

Kullanıcı adının uzunluğunu almak için bu yöntemi çağırın.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı adı uzunluğunu döndürür.

## <a name="curloperator-"></a><a name="operator_eq"></a> Kıvır:: operator =

Belirtilen `CUrl` nesneyi geçerli `CUrl` nesneye atar.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametreler

*Urla*<br/>
`CUrl`Geçerli nesneye kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru döndürür.

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a> Kıvma:: Setextraınfo

URL 'nin ek bilgilerini (örneğin, *metin* veya # *metin*) ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Parametreler

*lpszInfo*<br/>
URL 'ye dahil edilecek ek bilgileri içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="curlsethostname"></a><a name="sethostname"></a> Kıvat:: SetHostName

Ana bilgisayar adını ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Parametreler

*lpszHost*<br/>
Ana bilgisayar adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="curlsetpassword"></a><a name="setpassword"></a> Kıvır:: SetPassword

Parolayı ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Parametreler

*lpszPass*<br/>
Parola.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="curlsetportnumber"></a><a name="setportnumber"></a> Kıvır:: SetPortNumber

Bağlantı noktası numarasını ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Parametreler

*nPrt*<br/>
Bağlantı noktası numarası.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="curlsetscheme"></a><a name="setscheme"></a> Kıvır:: SetScheme

URL düzenini ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Parametreler

*nScheme*<br/>
Düzenin [ATL_URL_SCHEME](atl-url-scheme-enum.md) değerlerinden biri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrıca, düzeni adına göre de ayarlayabilirsiniz (bkz. [kıvrımlı:: set, Mename](#setschemename)).

## <a name="curlsetschemename"></a><a name="setschemename"></a> Kıvma:: set, Mename

URL düzeni adını ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSchm*<br/>
URL düzeni adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Ayrıca, bir [ATL_URL_SCHEME](atl-url-scheme-enum.md) sabiti kullanarak düzeni ayarlayabilirsiniz (bkz. [kıvrımlı:: SetScheme](#setscheme)).

## <a name="curlseturlpath"></a><a name="seturlpath"></a> Kıvl:: SetUrlPath

URL yolunu ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
URL yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="curlsetusername"></a><a name="setusername"></a> Kıvır:: SetUserName

Kullanıcı adını ayarlamak için bu yöntemi çağırın.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Parametreler

*lpszUser*<br/>
Kullanıcı adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)
