---
title: ATL HTTP yardımcı işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 224f4d78aec432a27b2a0258d0d6b3d4a8f2174d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209514"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP yardımcı işlevleri

Bu işlevler URL'leri işlenmesini destekler.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL canonicalizes.|  
|[AtlCombineUrl](#atlcombineurl)|Temel URL ile göreli bir URL'yi, kurallı tek bir URL birleştirir.|  
|[AtlEscapeUrl](#atlescapeurl)|Tüm güvenli olmayan karakterleri kaçış dizilerine dönüştürür.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Belirli bir Internet Protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını alır.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Bir karakterin bir URL içinde kullanılmak üzere güvenli olup olmadığını belirler.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Özgün değerlerine karakterleri kaçış karakterleri dönüştürür.|  
|[RGBToHtml](#rgbtohtml)|Dönüştürür bir [COLORREF](/windows/desktop/gdi/colorref) ilgili renk değerine karşılık gelen HTML metnine değeri.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  

## <a name="atlcanonicalizeurl"></a> AtlCanonicalizeUrl
Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın.  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *szUrl*  
 Getirilecek URL'si.  
  
 *szCanonicalized*  
 Kurallaştırılan URL'sini almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pdwMaxLength*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szCanonicalized*. İşlev başarılı olursa değişken sondaki null karakter de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluk alanı sondaki null karakter de dahil olmak üzere arabelleğin bayt cinsinden alır.  
  
 *CertOpenStore*  
 Bu işlevin davranışını denetleme ATL_URL bayraklar. 

- ATL_URL_BROWSER_MODE desteklemiyor kodlayın veya karakter kodunu çözme sonra: "#" veya "?" ve sonra sondaki boşluk kaldırmaz "?". Bu değer belirtilmezse, URL'nin tamamını kodlanır ve boşluk kaldırılır.
- ATL_URL_DECODE tüm % XX dizileri URL ayrıştırılmadan önce kaçış dizileri içeren karaktere dönüştürür.
- ATL_URL_ENCODE_PERCENT kodlar herhangi bir yüzde işaretleri ile karşılaşıldı. Varsayılan olarak, yüzde işaretleri kodlanmaz.
- ATL_URL_ENCODE_SPACES_ONLY kodlar yalnızca boşlukları.
- ATL_URL_ESCAPE dönüştürür, karşılık gelen karakterle tüm kaçış dizilerine (% XX).
- ATL_URL_NO_ENCODE mu güvenli olmayan karakterleri kaçış sıralarına dönüştürme yok.
- ATL_URL_NO_META kaldırmaz meta dizileri (gibi "."ve"...") URL'sinden. 
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli sürümü gibi davranır [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla) ancak WinINet veya Internet Explorer yüklenmesini gerektirmez.  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla)

 ## <a name="atlcombineurl"></a> AtlCombineUrl
 Temel URL ile göreli bir URL'yi, kurallı tek bir URL'de birleştirmek için bu işlevi çağırın.  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *szBaseUrl*  
 Temel URL'si.  
  
 *szRelativeUrl*  
 Temel URL göreli URL'si.  
  
 *szBuffer*  
 Kurallaştırılan URL'sini almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pdwMaxLength*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szBuffer*. İşlev başarılı olursa değişken sondaki null karakter de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluk alanı sondaki null karakter de dahil olmak üzere arabelleğin bayt cinsinden alır.  
  
 *CertOpenStore*  
 Bu işlevin davranışını denetleyen bayraklar. Bkz: [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli sürümü gibi davranır [InternetCombineUrl](/windows/desktop/api/wininet/nf-wininet-internetcombineurla) ancak WinINet veya Internet Explorer yüklenmesini gerektirmez.  
  
## <a name="atlescapeurl"></a> AtlEscapeUrl
 Tüm güvenli olmayan karakterleri kaçış sıralarına dönüştürmek için bu işlevi çağırın.  
  
```    
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
 *lpszStringIn*  
 Dönüştürülecek URL'si.  
  
 *lpszStringOut*  
 Dönüştürülen URL yazılacağı arayana ayrılan arabelleği.  
  
 *pdwStrLen*  
 DWORD değişken işaretçisi. İşlev başarılı olursa *pdwStrLen* sondaki null karakter de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluk alanı sondaki null karakter de dahil olmak üzere arabelleğin bayt cinsinden alır. Bu yöntem, geniş karakter sürümünü kullanırken *pdwStrLen* karakter gereken bayt sayısını değil sayısını alır.  
  
 *dwMaxLength*  
 Arabellek boyutu *lpszStringOut*.  
  
 *CertOpenStore*  
 Bu işlevin davranışını denetleme ATL_URL bayraklar. Bkz: [ATLCanonicalizeUrl](#atlcanonicalizeurl) için olası değerler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort
 Belirli bir Internet protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevi çağırın.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md) bağlantı noktası numarasını almak istediğiniz düzeni tanımlayan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port) düzeni tanınmadığında ATL_URL_INVALID_PORT_NUMBER ve belirtilen şema ile ilişkili.  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *şirketinden chIn*  
 Güvenliğiniz için test edilecek karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Znak na vstupu aksi güvenli, FALSE ise TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 URL'leri kullanılmamalıdır karakter kullanarak bu işlevi test edilebilir ve kullanılarak dönüştürülüp [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="atlunescapeurl"></a> AtlUnescapeUrl
 Kaçış karakterlerini orijinal değerlerine döndürmek için bu işlevi çağırın.  
  
```    
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
 *lpszStringIn*  
 Dönüştürülecek URL'si.  
  
 *lpszStringOut*  
 Dönüştürülen URL yazılacağı arayana ayrılan arabelleği.  
  
 *pdwStrLen*  
 DWORD değişken işaretçisi. İşlev başarılı olursa değişken sondaki null karakter de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluk alanı sondaki null karakter de dahil olmak üzere arabelleğin bayt cinsinden alır.  
  
 *dwMaxLength*  
 Arabellek boyutu *lpszStringOut*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından uygulanan dönüştürme işlemi tersine çevirir [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="rgbtohtml"></a> RGBToHtml
Dönüştürür bir [COLORREF](/windows/desktop/gdi/colorref) ilgili renk değerine karşılık gelen HTML metnine değeri.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Renk*  
 Bir RGB renk değeri.  
  
 *pbOut*  
 HTML renk değeri metnini almak için çağırıcı tarafından ayrılan arabelleği. Arabellek alanı için null sonlandırıcıyı ortasının dahil olmak üzere en az 8 karakter olmalıdır).  
  
 *nBuffer*  
 (Null sonlandırıcıyı ortasının dahil) arabelleğin bayt cinsinden boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Her bir rengin kırmızı, yeşil ve mavi bileşenlerinin için 2 basamak kullanarak 6 basamaklı bir onaltılık değer tarafından izlenen bir diyez işareti HTML renk değeridir (örneğin #FFFFFF beyaz).  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Parametreler  
 *St*  
 Bir HTTP biçim dizesi alınması için sistem saati.  
  
 *strTime*  
 RFC 2616'da tanımlanan HTTP tarih saat almak için bir dize değişkeni başvuru ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) ve RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)   

