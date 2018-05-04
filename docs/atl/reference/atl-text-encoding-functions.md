---
title: ATL metin işlevleri kodlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
ms.openlocfilehash: 26eb0709c4009070e6255c6ee178f19d13d8a9c3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-text-encoding-functions"></a>ATL metin işlevleri kodlama
Bu işlevleri kodlamak ve kodlarını çözmek metin destekler.

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|   
|[AtlGetVersion](#atlgetversion)|Kullanmakta olduğunuz ATL kitaplığı sürümünü almak için bu işlevini çağırın.  |  
|[AtlHexDecode](#atlhexdecode)|Onaltılık metin olarak gibi önceki çağrısıyla kodlandıktan veri dizesi kodunu çözer [AtlHexEncode](#atlhexencode).|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[AtlHexEncode](#atlhexencode)|Herhangi bir veriyi onaltılık bir metin dizesi olarak kodlamak için bu işlevi çağırın.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[AtlHexValue](#atlhexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Unicode dizesini UTF-8'e dönüştürmek için bu işlevi çağırın. |
|[BEncode](#bencode)|Bazı verileri "B" kodlama kullanarak dönüştürmek için bu işlevi çağırın.|
|[BEncodeGetRequiredLength](#bencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[EscapeXML](#escapexml)|XML'de kullanılması güvenli olmayan karakterleri güvenli eşdeğerlerine dönüştürmek için bu işlevi çağırın.|
|[GetExtendedChars](#getextendedchars)|Bir dizede genişletilmiş karakter sayısını almak için bu işlevi çağırın.|
|[IsExtendedChar](#isextendedchar)|Belirli bir karakterin genişletilmiş bir karakter (32 den küçük, 126'dan büyük ve sekme, satır besleme veya satır başı değil) olup olmadığını öğrenmek için bu işlevi çağırın.|
|[QEncode](#qencode)|Bazı verileri "Q" kodlama kullanarak dönüştürmek için bu işlevi çağırın.  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[QPDecode](#qpdecode)|Tırnak içine alınmış-yazdırılabilir biçiminde gibi önceki çağrısıyla kodlandıktan veri dizesi kodunu çözer [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[QPEncode](#qpencode)|Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUDecode](#uudecode)|Uuencoded gibi önceki bir çağrı tarafından kaldırıldı veri dizesi kodunu çözer [UUEncode](#uuencode).|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUEncode](#uuencode)|Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlenc.h  
 
## <a name="atlgethexvalue"></a> AtlGetHexValue
Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `chIn`  
 Onaltılık karakter '0'-'9', 'A'-'F' veya 'a'-'f'.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş karakter sayısal değeri bir onaltılık yorumlanır. Örneğin, bir giriş '0' ın 0 değerini döndürür ve giriş 'A' 10 değerini döndürür. Giriş karakter onaltılık basamak değilse, bu işlev, -1 döndürür.  
  
## <a name="atlgetversion"></a> AtlGetVersion
Kullanmakta olduğunuz ATL kitaplığı sürümünü almak için bu işlevini çağırın.  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pReserved`  
 Ayrılmış bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `DWORD` derleme veya çalışan ATL kitaplığı sürümünün tamsayı değeri.  
  
## <a name="example"></a>Örnek  
 İşlevi aşağıda çağrılmalıdır.  
  
 [!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  

## <a name="atlhexdecode"></a> AtlHexDecode
Onaltılık metin olarak gibi önceki çağrısıyla kodlandıktan veri dizesi kodunu çözer [AtlHexEncode](#atlhexencode).  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pSrcData`  
 Kodu çözülecek veriler içeren dize.  
  
 `nSrcLen`  
 Karakter cinsinden uzunluğu `pSrcData`.  
  
 `pbDest`  
 Kodu çözülmüş verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Bayt cinsinden uzunluğu içeren bir değişkeni işaretçi `pbDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa arabelleğinin bayt olarak alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength
Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanmış dizedeki karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodu çözülmüş dizesi tutan bir arabellek için gereken bayt sayısını `nSrcLen` karakter.  
  
## <a name="atlhexencode"></a> AtlHexEncode
Herhangi bir veriyi onaltılık bir metin dizesi olarak kodlamak için bu işlevi çağırın.  
  
```  
inline BOOL AtlHexEncode(  
   const BYTE * pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
int * pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pbSrcData`  
 Kodlanacak verileri içeren bir arabellek.  
  
 `nSrcLen`  
 Kodlanacak veri uzunluğu bayt.  
  
 `szDest`  
 Kodlanmış verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabellek gerekli uzunluğa alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Her kaynak verilerin baytı 2 on altılı karakter olarak kodlanır.  
  
## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanacak veri baytı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış verileri tutmak için arabellek gerekli karakter sayısı `nSrcLen` bayt sayısı.  
  
## <a name="atlhexvalue"></a> AtlHexValue
Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `chIn`  
 Onaltılık karakter '0'-'9', 'A'-'F' veya 'a'-'f'.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş karakter sayısal değeri bir onaltılık yorumlanır. Örneğin, bir giriş '0' ın 0 değerini döndürür ve giriş 'A' 10 değerini döndürür. Giriş karakter onaltılık basamak değilse, bu işlev, -1 döndürür.  
  
## <a name="atlunicodetoutf8"></a> AtlUnicodeToUTF8
Unicode dizesini UTF-8'e dönüştürmek için bu işlevi çağırın.  
  
```  
ATL_NOINLINE inline int AtlUnicodeToUTF8(  
   LPCWSTR wszSrc,  
   int nSrc,  
   LPSTR szDest,  
   int nDest) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *wszSrc*  
 Dönüştürülecek UNICODE dizesi  
  
 `nSrc`  
 UNICODE dizesi karakter cinsinden uzunluğu.  
  
 `szDest`  
 Dönüştürülmüş dizeyi almak için arabellek çağıran tarafından ayrılmış.  
  
 `nDest`  
 Bayt cinsinden uzunluğu arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürülmüş dizeyi karakter sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüştürülmüş dizeyi için gerekli olan arabellek boyutunu belirlemek için 0 geçirmek için bu işlev çağrısı `szDest` ve `nDest`.  
  
## <a name="bencode"></a> BEncode  
Bazı verileri "B" kodlama kullanarak dönüştürmek için bu işlevi çağırın.  
  
```  
inline BOOL BEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pbSrcData`  
 Kodlanacak verileri içeren bir arabellek.  
  
 `nSrcLen`  
 Kodlanacak veri uzunluğu bayt.  
  
 `szDest`  
 Kodlanmış verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabellek gerekli uzunluğa alır.  
  
 `pszCharSet`  
 Karakter dönüştürme için kullanmak üzere ayarlanmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 "B" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength 
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanacak veri baytı sayısı.  
  
 `nCharsetLen`  
 Dönüştürme için kullanmak üzere ayarlanmış karakter karakter cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış verileri tutmak için arabellek gerekli karakter sayısı `nSrcLen` bayt sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 "B" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="escapexml"></a> EscapeXML
XML'de kullanılması güvenli olmayan karakterleri güvenli eşdeğerlerine dönüştürmek için bu işlevi çağırın.  
  
```  
inline int EscapeXML(  
   const wchar_t * szIn,  
   int nSrcLen,  
   wchar_t * szEsc,  
   int nDestLen,  
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `szIn`  
 Dönüştürülecek dizesi.  
  
 *nSrclen*  
 Dönüştürülecek dizeyi karakter cinsinden uzunluğu.  
  
 *szEsc*  
 Dönüştürülmüş dizeyi almak için arabellek çağıran tarafından ayrılmış.  
  
 *nDestLen*  
 Çağıran tarafından ayrılan arabellek karakter cinsinden uzunluğu.  
  
 `dwFlags`  
 ATL_ESC nasıl gerçekleştirilecek dönüştürme olduğunu tanımlayan işaretler. 

- `ATL_ESC_FLAG_NONE` Varsayılan davranışı. Tırnak işaretleri ve kesme dönüştürülmez.
- `ATL_ESC_FLAG_ATTR` Tırnak işaretleri ve kesme dönüştürülür `&quot;` ve `&apos;` sırasıyla.


  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürülmüş dizeyi karakter cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından gerçekleştirilen olası dönüşümleri tabloda gösterilmiştir:  
  
|Kaynak|Hedef|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="getextendedchars"></a> GetExtendedChars
Bir dizede genişletilmiş karakter sayısını almak için bu işlevi çağırın.  
  
```  
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `szSrc`  
 Çözümlenecek dizesi.  
  
 `nSrcLen`  
 Dizenin karakter cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirlenen dizesi içinde bulunan genişletilmiş karakterlerin sayısını döndürür [IsExtendedChar](#isextendedchar).  
  
## <a name="isextendedchar"></a> IsExtendedChar
Belirli bir karakterin genişletilmiş bir karakter (32 den küçük, 126'dan büyük ve sekme, satır besleme veya satır başı değil) olup olmadığını öğrenmek için bu işlevi çağırın.  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *ch*  
 Sınanacak karakter  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** karakter genişletilmişse **FALSE** Aksi takdirde.  
  
## <a name="qencode"></a> QEncode
Bazı verileri "Q" kodlama kullanarak dönüştürmek için bu işlevi çağırın.  
  
```  
inline BOOL QEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet,  
   int* pnNumEncoded = NULL) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pbSrcData`  
 Kodlanacak verileri içeren bir arabellek.  
  
 `nSrcLen`  
 Kodlanacak veri uzunluğu bayt.  
  
 `szDest`  
 Kodlanmış verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabellek gerekli uzunluğa alır.  
  
 `pszCharSet`  
 Karakter dönüştürme için kullanmak üzere ayarlanmış.  
  
 *pnNumEncoded*  
 Geri dönüş dönüştürülüp gerekiyordu güvenli olmayan karakter sayısını içeren bir değişkeni için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 "Q" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength 
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanacak veri baytı sayısı.  
  
 `nCharsetLen`  
 Dönüştürme için kullanmak üzere ayarlanmış karakter karakter cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış verileri tutmak için arabellek gerekli karakter sayısı `nSrcLen` bayt sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 "Q" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qpdecode"></a> QPDecode
Tırnak içine alınmış-yazdırılabilir biçiminde gibi önceki çağrısıyla kodlandıktan veri dizesi kodunu çözer [QPEncode](#qpencode).  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pbSrcData`  
 Kodu çözülecek veriler içeren bir arabellek.  
  
 [in] `nSrcLen`  
 Bayt cinsinden uzunluğu `pbSrcData`.  
  
 [out] `szDest`  
 Kodu çözülmüş verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 [out] `pnDestLen`  
 Bayt cinsinden uzunluğu içeren bir değişkeni işaretçi `szDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa arabelleğinin bayt olarak alır.  
  
 [in] `dwFlags`  
 Nasıl gerçekleştirilecek dönüştürme olduğunu tanımlayan işaretler. Bkz: [ATLSMTP_QPENCODE bayrakları](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` başarılı, `FALSE` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Tırnak içine alınmış-yazdırılabilir kodlama düzeni RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength
Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanmış dizedeki karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodu çözülmüş dizesi tutan bir arabellek için gereken bayt sayısını `nSrcLen` karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Tırnak içine alınmış-yazdırılabilir kodlama düzeni RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpencode"></a> QPEncode
Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.  
  
```  
inline BOOL QPEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pbSrcData`  
 Kodlanacak verileri içeren bir arabellek.  
  
 `nSrcLen`  
 Kodlanacak veri uzunluğu bayt.  
  
 `szDest`  
 Kodlanmış verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabellek gerekli uzunluğa alır.  
  
 `dwFlags`  
 Nasıl gerçekleştirilecek dönüştürme olduğunu tanımlayan ATLSMTP_QPENCODE işaretler. 
- `ATLSMTP_QPENCODE_DOT` Bir süre bir satır başlangıcında görünüyorsa, bu çıkışı eklenen yanı sıra kodlanmış.
- `ATLSMTP_QPENCODE_TRAILING_SOFT` Ekler `=\r\n` kodlu bir dize için.

Tırnak içine alınmış-yazdırılabilir kodlama düzeni açıklanan [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt).
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Tırnak içine alınmış-yazdırılabilir kodlama düzeni RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanacak veri baytı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış verileri tutmak için arabellek gerekli karakter sayısı `nSrcLen` bayt sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Tırnak içine alınmış-yazdırılabilir kodlama düzeni RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="uudecode"></a> UUDecode
Uuencoded gibi önceki bir çağrı tarafından kaldırıldı veri dizesi kodunu çözer [UUEncode](#uuencode).  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pbSrcData`  
 Kodu çözülecek veriler içeren dize.  
  
 `nSrcLen`  
 Bayt cinsinden uzunluğu `pbSrcData`.  
  
 `pbDest`  
 Kodu çözülmüş verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Bayt cinsinden uzunluğu içeren bir değişkeni işaretçi `pbDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişkeni gerekli uzunluğa arabelleğinin bayt olarak alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulanması POSIX P1003.2b/D11 izler.  
  
## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength
Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanmış dizedeki karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodu çözülmüş dizesi tutan bir arabellek için gereken bayt sayısını `nSrcLen` karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulanması POSIX P1003.2b/D11 izler.  
  
## <a name="uuencode"></a> UUEncode
Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın.  
  
```  
inline BOOL UUEncode(  
   const BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCTSTR lpszFile = _T("file"),  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 `pbSrcData`  
 Kodlanacak verileri içeren bir arabellek.  
  
 `nSrcLen`  
 Kodlanacak veri uzunluğu bayt.  
  
 `szDest`  
 Kodlanmış verileri almak için arabellek çağıran tarafından ayrılmış.  
  
 `pnDestLen`  
 Karakter cinsinden uzunluğu içeren bir değişkeni işaretçi `szDest`. İşlev başarılı olursa, değişkeni arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabellek gerekli uzunluğa alır.  
  
 *lpszFile*  
 ATLSMTP_UUENCODE_HEADER belirtildiğinde üstbilgiye eklenecek dosyanın `dwFlags`.  
  
 `dwFlags`  
 Bu işlev davranışını denetleme bayraklar. 
- `ATLSMTP_UUENCODE_HEADE` Üstbilgi kodlanmış olmalıdır.
- `ATLSMTP_UUENCODE_END` Son kodlanmış olmalıdır.
- `ATLSMTP_UUENCODE_DOT` Veri doldurmak gerçekleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulanması POSIX P1003.2b/D11 izler.  
  
## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 `nSrcLen`  
 Kodlanacak veri baytı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış verileri tutmak için arabellek gerekli karakter sayısı `nSrcLen` bayt sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulanması POSIX P1003.2b/D11 izler.  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)   