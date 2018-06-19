---
title: Sınıf cUrl | Microsoft Docs
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
ms.openlocfilehash: afb0f7abc079d699cfcf682356b88b9cc8aa2bb9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366240"
---
# <a name="curl-class"></a>CUrl sınıfı
Bu sınıf, bir URL temsil eder. URL diğer bağımsız olarak her öğenin var olan bir URL Ayrıştırma olup olmadığını denetlemek tanır dize ya da sıfırdan bir dize oluşturma.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CUrl
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUrl::CUrl](#curl)|Oluşturucu.|  
|[CUrl:: ~ CUrl](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUrl::Canonicalize](#canonicalize)|URL dizesi için kurallı biçimi dönüştürmek için bu yöntemi çağırın.|  
|[CUrl::Clear](#clear)|URL alanların tümünü temizlemek için bu yöntemi çağırın.|  
|[CUrl::CrackUrl](#crackurl)|Kod çözme ve URL ayrıştırmak için bu yöntemi çağırın.|  
|[CUrl::CreateUrl](#createurl)|URL oluşturmak için bu yöntemi çağırın.|  
|[CUrl::GetExtraInfo](#getextrainfo)|Ek bilgi almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den.|  
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Ek bilgi uzunluğu almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den alınamadı.|  
|[CUrl::GetHostName](#gethostname)|URL'den ana bilgisayar adını almak için bu yöntemi çağırın.|  
|[CUrl::GetHostNameLength](#gethostnamelength)|Ana bilgisayar adı uzunluğu almak için bu yöntemi çağırın.|  
|[CUrl::GetPassword](#getpassword)|URL'den parola almak için bu yöntemi çağırın.|  
|[CUrl::GetPasswordLength](#getpasswordlength)|Parola uzunluğu almak için bu yöntemi çağırın.|  
|[CUrl::GetPortNumber](#getportnumber)|Bağlantı noktası numarası ATL_URL_PORT bakımından almak için bu yöntemi çağırın.|  
|[CUrl::GetScheme](#getscheme)|URL şeması almak için bu yöntemi çağırın.|  
|[CUrl::GetSchemeName](#getschemename)|URL şeması adı almak için bu yöntemi çağırın.|  
|[CUrl::GetSchemeNameLength](#getschemenamelength)|URL şeması adının uzunluğu almak için bu yöntemi çağırın.|  
|[CUrl::GetUrlLength](#geturllength)|URL uzunluğu almak için bu yöntemi çağırın.|  
|[CUrl::GetUrlPath](#geturlpath)|URL yolunu almak için bu yöntemi çağırın.|  
|[CUrl::GetUrlPathLength](#geturlpathlength)|URL yolu uzunluğu almak için bu yöntemi çağırın.|  
|[CUrl::GetUserName](#getusername)|URL'SİNDEN kullanıcı adını almak için bu yöntemi çağırın.|  
|[CUrl::GetUserNameLength](#getusernamelength)|Kullanıcı adının uzunluğu almak için bu yöntemi çağırın.|  
|[CUrl::SetExtraInfo](#setextrainfo)|Ek bilgi için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'si.|  
|[CUrl::SetHostName](#sethostname)|Ana bilgisayar adı ayarlamak için bu yöntemi çağırın.|  
|[CUrl::SetPassword](#setpassword)|Parolayı ayarlamak için bu yöntemi çağırın.|  
|[CUrl::SetPortNumber](#setportnumber)|Bağlantı noktası numarası ATL_URL_PORT bakımından ayarlamak için bu yöntemi çağırın.|  
|[CUrl::SetScheme](#setscheme)|URL şeması ayarlamak için bu yöntemi çağırın.|  
|[CUrl::SetSchemeName](#setschemename)|URL şeması adı ayarlamak için bu yöntemi çağırın.|  
|[CUrl::SetUrlPath](#seturlpath)|URL yolunu ayarlamak için bu yöntemi çağırın.|  
|[CUrl::SetUserName](#setusername)|Kullanıcı adı ayarlamak için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUrl::operator =](#operator_eq)|Belirtilen atar `CUrl` geçerli nesne `CUrl` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CUrl` yol veya bağlantı noktası numarası gibi bir URL alanlarının yönetmenize olanak sağlar. `CUrl` aşağıdaki biçimde URL'lerini anlar:  
  
 \<Düzen > ://\<kullanıcı adı >:\<parola > @\<ana bilgisayar adı >:\<BağlantıNoktasıNumarası > /\<UrlPath >\<ExtraInfo >  
  
 (Bazı alanlar isteğe bağlıdır.) Örneğin, bu URL'yi göz önünde bulundurun:  
  
 http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents  
  
 [CUrl::CrackUrl](#crackurl) gibi ayrıştırır:  
  
-   Şeması: "http" veya [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)  
  
-   Kullanıcı adı: "biri"  
  
-   Parola: "gizli"  
  
-   Ana bilgisayar adı: "www.microsoft.com"  
  
-   PortNumber: 80  
  
-   UrlPath: "visualc/stuff.htm"  
  
-   ExtraInfo: "#contents"  
  
 UrlPath alan (örneğin) işlemek için kullanacağınız [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), ve [SetUrlPath](#seturlpath). Kullanacağınız [CreateUrl](#createurl) tam URL dizesi oluşturmak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="canonicalize"></a>  CUrl::Canonicalize  
 URL dizesi için kurallı biçimi dönüştürmek için bu yöntemi çağırın.  
  
```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Standartlaştırma denetim bayrakları. Bayrak belirtilmezse, ( `dwFlags` = 0), tüm güvenli olmayan karakter ve meta sıraları yöntemi dönüştürür (gibi \\., \.., ve \\...) kaçınmak için serileri. `dwFlags` Aşağıdaki değerlerden biri olabilir:  
  
-   ATL_URL_BROWSER_MODE: Bırakmaz kodlamak veya karakter kod çözme sonra "#" veya "" ve sonunda boşluk sonra kaldırmaz "". Bu değer belirtilmezse, tüm URL kodlanmış ve sonunda boşluk kaldırılır.  
  
-   ATL_URL _DECODE: karakterlere URL ayrıştırılır önce kaçış sıraları dahil olmak üzere, tüm % XX sıralarının dönüştürür.  
  
-   ATL_URL _ENCODE_PERCENT: karşılaştı herhangi yüzde işaretleri kodlar. Varsayılan olarak, yüzde işaretleri kodlanmış değil.  
  
-   ATL_URL _ENCODE_SPACES_ONLY: yalnızca boşluk kodlar.  
  
-   ATL_URL _NO_ENCODE: dizileri kaçınmak için güvenli olmayan karakterleri dönüştürmez.  
  
-   ATL_URL _NO_META: meta sıraları kaldırmaz (gibi "."ve"...") URL'den.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kurallı biçimi dönüştürme güvenli olmayan karakterler ve boşluklar kaçış dizilerine dönüştürme içerir.  
  
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
 `lpszUrl`  
 URL.  
  
 `dwFlags`  
 İçindeki tüm kaçış karakterleri dönüştürmek için ATL_URL_DECODE ya da ATL_URL_ESCAPE belirtin `lpszUrl` gerçek değerlerine ayrıştırma sonra. (Visual C++ 2005 önce ATL_URL_DECODE tüm kaçış karakterleri ayrıştırmadan önce dönüştürülür.)  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="createurl"></a>  CUrl::CreateUrl  
 Bu yöntem bir CUrl nesnesinin bileşen alanlarından URL dizesi oluşturur.  
  
```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszUrl*  
 Tam URL dizesi tutmak için bir dize arabelleği.  
  
 `pdwMaxLength`  
 En büyük uzunluğu *lpszUrl* dizesi arabelleği.  
  
 `dwFlags`  
 İçindeki tüm kaçış karakterleri dönüştürmek için ATL_URL_ESCAPE belirtin *lpszUrl* gerçek değerlerine.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, aşağıdaki biçimi kullanarak tam URL dizesi oluşturmak için tek tek alanların ekler:  
  
 **\<Düzen > ://\<kullanıcı >:\<geçirmek > @\<etki alanı >:\<bağlantı noktası >\<yolu >\<fazladan >**  
  
 Bu yöntem çağrılırken `pdwMaxLength` parametresi tarafından başvurulan dize arabelleğinin maksimum uzunluğu başlangıçta içermelidir *lpszUrl* parametresi. Değeri `pdwMaxLength` URL dizesi gerçek uzunluğuyla parametre güncelleştirilir.  
  
### <a name="example"></a>Örnek  
 Bu örnek bir CUrl nesnesi ve onun URL dizesi alınırken oluşturulmasını gösterir  
  
 [!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]  
  
##  <a name="curl"></a>  CUrl::CUrl  
 Oluşturucu.  
  
```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `urlThat`  
 `CUrl` URL oluşturmak için kopyalamak için nesne.  
  
##  <a name="dtor"></a>  CUrl:: ~ CUrl  
 Yok Edicisi.  
  
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
 Ek bilgi uzunluğu almak için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'den alınamadı.  
  
```
inline DWORD GetExtraInfoLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ek bilgi içeren dize uzunluğunu döndürür.  
  
##  <a name="gethostname"></a>  CUrl::GetHostName  
 URL'den ana bilgisayar adını almak için bu yöntemi çağırın.  
  
```
inline LPCTSTR GetHostName() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ana bilgisayar adını döndürür.  
  
##  <a name="gethostnamelength"></a>  CUrl::GetHostNameLength  
 Ana bilgisayar adı uzunluğu almak için bu yöntemi çağırın.  
  
```
inline DWORD GetHostNameLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ana bilgisayar adı uzunluğu döndürür.  
  
##  <a name="getpassword"></a>  CUrl::GetPassword  
 URL'den parola almak için bu yöntemi çağırın.  
  
```
inline LPCTSTR GetPassword() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parolayı döndürür.  
  
##  <a name="getpasswordlength"></a>  CUrl::GetPasswordLength  
 Parola uzunluğu almak için bu yöntemi çağırın.  
  
```
inline DWORD GetPasswordLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parola uzunluğu döndürür.  
  
##  <a name="getportnumber"></a>  CUrl::GetPortNumber  
 Bağlantı noktası numarasını almak için bu yöntemi çağırın.  
  
```
inline ATL_URL_PORT GetPortNumber() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantı noktası numarasını döndürür.  
  
##  <a name="getscheme"></a>  CUrl::GetScheme  
 URL şeması almak için bu yöntemi çağırın.  
  
```
inline ATL_URL_SCHEME GetScheme() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür [ATL_URL_SCHEME](atl-url-scheme-enum.md) URL şeması açıklayan değeri.  
  
##  <a name="getschemename"></a>  CUrl::GetSchemeName  
 URL şeması adı almak için bu yöntemi çağırın.  
  
```
inline LPCTSTR GetSchemeName() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL şeması adı (örneğin, "http" veya "ftp") döndürür.  
  
##  <a name="getschemenamelength"></a>  CUrl::GetSchemeNameLength  
 URL şeması adının uzunluğu almak için bu yöntemi çağırın.  
  
```
inline DWORD GetSchemeNameLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL şeması adı uzunluğu döndürür.  
  
##  <a name="geturllength"></a>  CUrl::GetUrlLength  
 URL uzunluğu almak için bu yöntemi çağırın.  
  
```
inline DWORD GetUrlLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL uzunluğu döndürür.  
  
##  <a name="geturlpath"></a>  CUrl::GetUrlPath  
 URL yolunu almak için bu yöntemi çağırın.  
  
```
inline LPCTSTR GetUrlPath() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL yolunu döndürür.  
  
##  <a name="geturlpathlength"></a>  CUrl::GetUrlPathLength  
 URL yolu uzunluğu almak için bu yöntemi çağırın.  
  
```
inline DWORD GetUrlPathLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL yolu uzunluğu döndürür.  
  
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
 Belirtilen atar `CUrl` geçerli nesne `CUrl` nesne.  
  
```
CUrl& operator= (const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `urlThat`  
 `CUrl` Geçerli nesnesine kopyalamak için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesne için bir başvuru döndürür.  
  
##  <a name="setextrainfo"></a>  CUrl::SetExtraInfo  
 Ek bilgi için bu yöntemi çağırın (gibi *metin* veya # *metin*) URL'si.  
  
```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszInfo*  
 URL'de bulunmasını istediğiniz ek bilgileri içeren dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="sethostname"></a>  CUrl::SetHostName  
 Ana bilgisayar adı ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszHost`  
 Ana bilgisayar adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="setpassword"></a>  CUrl::SetPassword  
 Parolayı ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszPass*  
 Parola.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="setportnumber"></a>  CUrl::SetPortNumber  
 Bağlantı noktası numarasını ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *nPrt*  
 Bağlantı noktası numarası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="setscheme"></a>  CUrl::SetScheme  
 URL şeması ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nScheme`  
 Aşağıdakilerden birini [ATL_URL_SCHEME](atl-url-scheme-enum.md) düzeni için değerleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Ada göre düzeni de ayarlayabilirsiniz (bkz [CUrl::SetSchemeName](#setschemename)).  
  
##  <a name="setschemename"></a>  CUrl::SetSchemeName  
 URL şeması adı ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszSchm*  
 URL Düzen adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanarak düzeni ayarlayabilirsiniz bir [ATL_URL_SCHEME](atl-url-scheme-enum.md) sabit (bkz [CUrl::SetScheme](#setscheme)).  
  
##  <a name="seturlpath"></a>  CUrl::SetUrlPath  
 URL yolunu ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPath`  
 URL yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
##  <a name="setusername"></a>  CUrl::SetUserName  
 Kullanıcı adı ayarlamak için bu yöntemi çağırın.  
  
```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszUser*  
 Kullanıcı adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../atl/reference/atl-classes.md)
