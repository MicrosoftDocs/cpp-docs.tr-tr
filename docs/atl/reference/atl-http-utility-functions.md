---
title: "ATL HTTP yardımcı programı işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 9cdb12373d93c17258fb615f667d7321e06f6728
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-http-utility-functions"></a>ATL HTTP yardımcı işlevleri

Bu işlevler URL'leri işlenmesini destekler.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Güvenli olmayan karakter ve alanları kaçış sıraları dönüştürme içeren bir URL canonicalizes.|  
|[AtlCombineUrl](#atlcombineurl)|Bir temel URL'yi ve göreli bir URL tek, Kurallı URL birleştirir.|  
|[AtlEscapeUrl](#atlescapeurl)|Tüm güvenli olmayan karakterleri kaçış dizilerine dönüştürür.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Belirli Internet Protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını alır.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Bir karakterin bir URL'de kullanılacak güvenli olup olmadığını belirler.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Dönüştürür özgün değerlerine karakteri kaçış.|  
|[RGBToHtml](#rgbtohtml)|Dönüştüren bir [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) bu renk değerine karşılık gelen HTML metin değeri.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  

## <a name="atlcanonicalizeurl"></a>AtlCanonicalizeUrl
Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın.  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `szUrl`  
 Getirilecek URL'si.  
  
 `szCanonicalized`  
 Kurallaştırılan URL almak için arabellek çağıran tarafından ayrılmış.  
  
 `pdwMaxLength`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szCanonicalized`. İşlev başarılı olursa, değişkeni sonlandırma null karakteri de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa sonlandırma null karakteri boşluk dahil olmak üzere arabelleğin bayt cinsinden alır.  
  
 `dwFlags`  
 Bu işlev davranışını denetleme ATL_URL bayraklar. 

- `ATL_URL_BROWSER_MODE`Değil kodlamak veya karakter kodunu çözmek sonra "#" veya "?" ve sonunda boşluk sonra kaldırmaz "?". Bu değer belirtilmezse, tüm URL kodlanmış ve sonunda boşluk kaldırılır.
- `ATL_URL_DECODE`Tüm % XX sıralarının URL ayrıştırılır önce kaçış sıraları dahil olmak üzere karaktere dönüştürür.
- `ATL_URL_ENCODE_PERCENT`Karşılaştı herhangi yüzde işaretleri kodlar. Varsayılan olarak, yüzde işaretleri kodlanmış değil.
- `ATL_URL_ENCODE_SPACES_ONLY`Yalnızca boşluk kodlar.
- `ATL_URL_ESCAPE`Tüm kaçış sıraları (% XX) kendi ilgili karakterlere dönüştürür.
- `ATL_URL_NO_ENCODE`Güvenli olmayan karakterleri kaçış dizilerine dönüştürmez.
- `ATL_URL_NO_META`Meta sıraları kaldırmaz (gibi "."ve"...") URL'den. 
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli sürümü gibi davranır [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) WinINet veya Internet Explorer yüklü olmasını gerektirmez, ancak.  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="atlcombineurl"></a>AtlCombineUrl
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
  
 `szBuffer`  
 Kurallaştırılan URL almak için arabellek çağıran tarafından ayrılmış.  
  
 `pdwMaxLength`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szBuffer`. İşlev başarılı olursa, değişkeni sonlandırma null karakteri de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa sonlandırma null karakteri boşluk dahil olmak üzere arabelleğin bayt cinsinden alır.  
  
 `dwFlags`  
 Bu işlev davranışını denetleme bayraklar. Bkz: [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli sürümü gibi davranır [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) WinINet veya Internet Explorer yüklü olmasını gerektirmez, ancak.  
  
## <a name="atlescapeurl"></a>AtlEscapeUrl
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
 `lpszStringIn`  
 Dönüştürülecek URL'si.  
  
 `lpszStringOut`  
 Çağıran tarafından ayrılan arabellek dönüştürülen URL yazılır.  
  
 `pdwStrLen`  
 DWORD değişkeni işaretçi. İşlev başarılı olursa, `pdwStrLen` sonlandırma null karakteri de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa sonlandırma null karakteri boşluk dahil olmak üzere arabelleğin bayt cinsinden alır. Bu yöntem geniş karakter sürümünü kullanırken `pdwStrLen` gereken, karakterlerin bayt sayısını değil sayısını alır.  
  
 `dwMaxLength`  
 Arabellek boyutu `lpszStringOut`.  
  
 `dwFlags`  
 Bu işlev davranışını denetleme ATL_URL bayraklar. Bkz: [ATLCanonicalizeUrl](#atlcanonicalizeurl) olası değerler için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
## <a name="atlgetdefaulturlport"></a> 
 Belirli bir Internet protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevi çağırın.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md) bağlantı noktası numarasını almak istediğiniz düzeni tanımlayan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port) düzeni tanınmıyor belirtilen düzeni veya ATL_URL_INVALID_PORT_NUMBER ile ilişkili.  

## <a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar
 Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `chIn`  
 Güvenliğiniz için sınanacak karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** giriş karakter güvenli, ise **FALSE** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 URL'ler kullanılmamalıdır karakterleri bu işlevi kullanılarak sınanabilir ve kullanılarak dönüştürülen [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="atlunescapeurl"></a>AtlUnescapeUrl
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
 `lpszStringIn`  
 Dönüştürülecek URL'si.  
  
 `lpszStringOut`  
 Çağıran tarafından ayrılan arabellek dönüştürülen URL yazılır.  
  
 `pdwStrLen`  
 DWORD değişkeni işaretçi. İşlev başarılı olursa, değişkeni sonlandırma null karakteri de dahil olmak üzere arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa sonlandırma null karakteri boşluk dahil olmak üzere arabelleğin bayt cinsinden alır.  
  
 `dwMaxLength`  
 Arabellek boyutu `lpszStringOut`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından uygulanan dönüştürme işlemi ters çevirir [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="rgbtohtml"></a>RGBToHtml
Dönüştüren bir [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) bu renk değerine karşılık gelen HTML metin değeri.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 RGB renk değeri.  
  
 `pbOut`  
 HTML renk değeri metin almak için arabellek çağıran tarafından ayrılmış. Arabellek alanı null Sonlandırıcı alanı dahil olmak üzere en az 8 karakter olmalıdır).  
  
 *nBuffer*  
 (Null Sonlandırıcı alanı dahil) arabelleğin bayt cinsinden boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 2 basamak her rengi kırmızı, yeşil ve mavi bileşenlerden biri kullanılarak 6 rakamlı onaltılık değeri arkasından pound işareti HTML renk değeridir (örneğin, #FFFFFF beyaz).  
  
## <a name="systemtimetohttpdate"></a>SystemTimeToHttpDate
Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Parametreler  
 `st`  
 Bir HTTP biçim dizesi alınabilmesi için sistem saati.  
  
 *strTime*  
 RFC 2616'da tanımlanan HTTP tarih saat almak için bir dize değişkeni bir başvuru ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) ve RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md)   

