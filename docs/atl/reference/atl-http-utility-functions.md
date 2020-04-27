---
title: ATL HTTP Yardımcı İşlevleri
ms.date: 11/04/2016
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
ms.openlocfilehash: c95681503da0d661382e6da33bd33e8f2004838b
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168611"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP Yardımcı İşlevleri

Bu işlevler, URL 'Lerin işlenmesini destekler.

|||
|-|-|
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Güvenli olmayan karakterleri ve boşlukları kaçış dizilerine dönüştürmeyi içeren bir URL canonicalizes.|
|[AtlCombineUrl](#atlcombineurl)|Temel URL 'yi ve göreli URL 'YI tek ve kurallı bir URL ile birleştirir.|
|[Attascapeurl 'Si](#atlescapeurl)|Güvenli olmayan tüm karakterleri kaçış sıralarına dönüştürür.|
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Belirli bir Internet Protokolü veya şeması ile ilişkili varsayılan bağlantı noktası numarasını alır.|
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Bir karakterin bir URL 'de kullanılmak üzere güvenli olup olmadığını belirler.|
|[AtlUnescapeUrl 'Si](#atlunescapeurl)|Atlanan karakterleri özgün değerlerine dönüştürür.|
|[RGBToHtml](#rgbtohtml)|[Colorref](/windows/win32/gdi/colorref) değerini, bu renk değerine KARŞıLıK gelen HTML metnine dönüştürür.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a>AtlCanonicalizeUrl

Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın.

```cpp
inline BOOL AtlCanonicalizeUrl(
   LPCTSTR szUrl,
   LPTSTR szCanonicalized,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*szUrl*<br/>
Kurallı olacak URL.

*szCanonicalized*<br/>
Kurallı URL 'sini almak için arayan tarafından ayrılmış arabellek.

*pdwMaxLength*<br/>
*SzCanonicalized*karakter cinsinden uzunluğu içeren bir değişken işaretçisi. İşlev başarılı olursa, değişken, Sonlandırıcı null karakteri dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken, Sonlandırıcı null karakteri için boşluk dahil olmak üzere arabelleğin bayt cinsinden gereken uzunluğunu alır.

*dwFlags*<br/>
Bu işlevin davranışını denetleyen bayraklar ATL_URL.

- ATL_URL_BROWSER_MODE "#" veya "?" karakterinden sonra karakterleri kodlayıp çözmez ve "?" karakterinden sonra sondaki boşluğu kaldırmaz. Bu değer belirtilmezse, tüm URL kodlanır ve sondaki boşluk kaldırılır.

- ATL_URL_DECODE, URL ayrıştırmadan önce kaçış dizileri dahil olmak üzere tüm% XX dizilerini karakterlere dönüştürür.

- ATL_URL_ENCODE_PERCENT, tüm yüzde işaretlerine kodlandı. Varsayılan olarak, yüzde işaretleri kodlanmaz.

- ATL_URL_ENCODE_SPACES_ONLY yalnızca boşlukları kodluyor.

- ATL_URL_ESCAPE, tüm kaçış dizilerini (% XX) karşılık gelen karakterlere dönüştürür.

- ATL_URL_NO_ENCODE, güvenli olmayan karakterleri kaçış sıralarına dönüştürmez.

- ATL_URL_NO_META, URL 'den meta dizileri ("." ve ".." gibi) kaldırmaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli [InternetCanonicalizeUrl](/windows/win32/api/wininet/nf-wininet-internetcanonicalizeurlw) sürümü gibi davranır ancak WinInet veya Internet Explorer 'ın yüklenmesini gerektirmez.

## <a name="atlcombineurl"></a><a name="atlcombineurl"></a>AtlCombineUrl

Temel URL ile göreli bir URL'yi, kurallı tek bir URL'de birleştirmek için bu işlevi çağırın.

```cpp
inline BOOL AtlCombineUrl(
   LPCTSTR szBaseUrl,
   LPCTSTR szRelativeUrl,
   LPTSTR szBuffer,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*szBaseUrl*<br/>
Temel URL.

*szRelativeUrl 'Si*<br/>
Temel URL 'ye göre URL.

*szBuffer*<br/>
Kurallı URL 'sini almak için arayan tarafından ayrılmış arabellek.

*pdwMaxLength*<br/>
*SzBuffer*karakterleri içindeki uzunluğu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken, Sonlandırıcı null karakteri dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken, Sonlandırıcı null karakteri için boşluk dahil olmak üzere arabelleğin bayt cinsinden gereken uzunluğunu alır.

*dwFlags*<br/>
Bu işlevin davranışını denetleyen bayraklar. Bkz. [AtlCanonicalizeUrl](#atlcanonicalizeurl).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli [InternetCombineUrl](/windows/win32/api/wininet/nf-wininet-internetcombineurlw) sürümü gibi davranır ancak WinInet veya Internet Explorer 'ın yüklenmesini gerektirmez.

## <a name="atlescapeurl"></a><a name="atlescapeurl"></a>Attascapeurl 'Si

Tüm güvenli olmayan karakterleri kaçış sıralarına dönüştürmek için bu işlevi çağırın.

```cpp
inline BOOL AtlEscapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();

inline BOOL AtlEscapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*lpszStringIn*<br/>
Dönüştürülecek URL.

*lpszStringOut*<br/>
Dönüştürülen URL 'nin yazılacağı, arayana ayrılan arabellek.

*pdwStrLen*<br/>
DWORD değişkenine yönelik işaretçi. İşlev başarılı olursa, *pdwStrLen* , Sonlandırıcı null karakteri dahil olmak üzere, arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken, Sonlandırıcı null karakteri için boşluk dahil olmak üzere arabelleğin bayt cinsinden gereken uzunluğunu alır. Bu yöntemin geniş karakter sürümünü kullanırken, *pdwStrLen* bayt sayısını değil, gereken karakter sayısını alır.

*dwMaxLength*<br/>
Buffer *lpszStringOut*boyutu.

*dwFlags*<br/>
Bu işlevin davranışını denetleyen bayraklar ATL_URL. Olası değerler için bkz. [ATLCanonicalizeUrl](#atlcanonicalizeurl) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="atlgetdefaulturlport"></a><a name="atlgetdefaulturlport"></a>AtlGetDefaultUrlPort

Belirli bir Internet protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevi çağırın.

```cpp
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();
```

### <a name="parameters"></a>Parametreler

*m_nScheme*<br/>
Bağlantı noktası numarasını almak istediğiniz düzeni tanımlayan [ATL_URL_SCHEME](atl-url-scheme-enum.md) değeri.

### <a name="return-value"></a>Dönüş Değeri

Düzen tanınmazsa, belirtilen düzen veya ATL_URL_INVALID_PORT_NUMBER ilişkili [ATL_URL_PORT](atl-typedefs.md#atl_url_port) .

## <a name="atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar

Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın.

```cpp
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();
```

### <a name="parameters"></a>Parametreler

*chIn*<br/>
Güvenlik için test edilecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Giriş karakteri güvenli değilse TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

URL 'lerde kullanılması gereken karakterler, bu işlev kullanılarak test edilebilir ve [AtlCanonicalizeUrl](#atlcanonicalizeurl)kullanılarak dönüştürülür.

## <a name="atlunescapeurl"></a><a name="atlunescapeurl"></a>AtlUnescapeUrl 'Si

Kaçış karakterlerini orijinal değerlerine döndürmek için bu işlevi çağırın.

```cpp
inline BOOL AtlUnescapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();

inline BOOL AtlUnescapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();
```

### <a name="parameters"></a>Parametreler

*lpszStringIn*<br/>
Dönüştürülecek URL.

*lpszStringOut*<br/>
Dönüştürülen URL 'nin yazılacağı, arayana ayrılan arabellek.

*pdwStrLen*<br/>
DWORD değişkenine yönelik işaretçi. İşlev başarılı olursa, değişken, Sonlandırıcı null karakteri dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken, Sonlandırıcı null karakteri için boşluk dahil olmak üzere arabelleğin bayt cinsinden gereken uzunluğunu alır.

*dwMaxLength*<br/>
Buffer *lpszStringOut*boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

[Atelscapeurl](#atlescapeurl)tarafından uygulanan dönüştürme işlemini tersine çevirir.

## <a name="rgbtohtml"></a><a name="rgbtohtml"></a>RGBToHtml

[Colorref](/windows/win32/gdi/colorref) değerini, bu renk değerine KARŞıLıK gelen HTML metnine dönüştürür.

```cpp
bool inline RGBToHtml(
   COLORREF color,
   LPTSTR pbOut,
   long nBuffer);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
Bir RGB renk değeri.

*Phakkında*<br/>
HTML renk değeri için metni almak üzere arayan tarafından ayrılmış arabellek. Arabellekte boş Sonlandırıcı için boşluk da dahil olmak üzere en az 8 karakter uzunluğunda olmalıdır.

*nBuffer*<br/>
Arabelleğin bayt cinsinden boyutu (null Sonlandırıcı için boşluk da dahil).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bir HTML renk değeri, rengin kırmızı, yeşil ve mavi bileşenlerinin her biri için 2 basamaklı olan 6 basamaklı onaltılık bir değer ve sonra da (örneğin, #FFFFFF beyazdır).

## <a name="systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a>SystemTimeToHttpDate

Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.

```cpp
inline void SystemTimeToHttpDate(
   const SYSTEMTIME& st,
   CStringA& strTime);
```

### <a name="parameters"></a>Parametreler

*oluşan*<br/>
HTTP biçim dizesi olarak elde edilecek sistem süresi.

*strTime*<br/>
RFC 2616 ([https://www.ietf.org/rfc/rfc2616.txt](https://www.ietf.org/rfc/rfc2616.txt)) ve RFC 1123 ([https://www.ietf.org/rfc/rfc1123.txt](https://www.ietf.org/rfc/rfc1123.txt)) ' de tanımlanan http Tarih saatini almak için bir dize değişkenine başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../atl-com-desktop-components.md)<br/>
[InternetCanonicalizeUrl](/windows/win32/api/wininet/nf-wininet-internetcanonicalizeurlw)
