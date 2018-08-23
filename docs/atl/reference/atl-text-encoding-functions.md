---
title: ATL metin kodlama işlevleri | Microsoft Docs
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9162c515f4fd451f3e663895953e106bb4e65135
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42465089"
---
# <a name="atl-text-encoding-functions"></a>ATL metin kodlama işlevleri
Bu işlevler, kodlama ve kodunu çözme metin destekler.

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|   
|[AtlGetVersion](#atlgetversion)|Kullanmakta olduğunuz ATL kitaplığı sürümünü almak için bu işlevi çağırın.  |  
|[AtlHexDecode](#atlhexdecode)|Onaltılı metin olarak önceki bir çağrı tarafından kodlanmış veri dizisinin kodunu çözer [AtlHexEncode](#atlhexencode).|
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
|[QPDecode](#qpdecode)|Sınırlandırılmış Yazdırılabilir biçimde gibi önceki bir çağrı tarafından kodlanmış veri dizisinin kodunu çözer [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[QPEncode](#qpencode)|Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUDecode](#uudecode)|Önceki bir çağrı uuencoded olarak bırakıldı veri dizisinin kodunu çözer [UUEncode](#uuencode).|
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
 *şirketinden chIn*  
 Onaltılık karakter '0'-'9', 'A'-'F' veya 'a'-'f'.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Znak na vstupu sayısal değeri bir onaltılık basamak yorumlanır. Örneğin, '0' ın girdi 0 değerini döndürür ve 'A' girdisi 10 değerini döndürür. Bu işlev, girdi karakteri bir onaltılık rakam değil, -1 döndürür.  
  
## <a name="atlgetversion"></a> AtlGetVersion
Kullanmakta olduğunuz ATL kitaplığı sürümünü almak için bu işlevi çağırın.  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Korunur*  
 Ayrılmış bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Derleme veya çalışan ATL kitaplığı sürümünü DWORD tamsayı değerini döndürür.  
  
## <a name="example"></a>Örnek  
 İşlev gibi çağrılmalıdır.  
  
 [!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  

## <a name="atlhexdecode"></a> AtlHexDecode
Onaltılı metin olarak önceki bir çağrı tarafından kodlanmış veri dizisinin kodunu çözer [AtlHexEncode](#atlhexencode).  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *pSrcData*  
 Kodu çözülecek veriler içeren dize.  
  
 *nSrcLen*  
 Karakter cinsinden uzunluğu *pSrcData*.  
  
 *pbDest*  
 Kodu çözülmüş verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Bayt cinsinden uzunluğunu içeren bir değişken işaretçisi *pbDest*. İşlev başarılı olursa değişken arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişken arabelleğin bayt cinsinden gerekli uzunluğunu alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength
Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanmış dize karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodu çözülen dize, tutabilen bir arabellek için gereken bayt sayısını *nSrcLen* karakter.  
  
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
 *pbSrcData*  
 Kodlanacak verileri içeren arabellek.  
  
 *nSrcLen*  
 Kodlanacak verilerin bayt cinsinden uzunluğu.  
  
 *szDest*  
 Kodlanmış verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szDest*. İşlev başarılı olursa değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabelleği gereken uzunluğu alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Her kaynak verileri baytlık 2 on altılı karakter olarak kodlanır.  
  
## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanacak veri baytı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış veri tutabilen bir arabellek için gereken karakter sayısı *nSrcLen* bayt.  
  
## <a name="atlhexvalue"></a> AtlHexValue
Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *şirketinden chIn*  
 Onaltılık karakter '0'-'9', 'A'-'F' veya 'a'-'f'.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Znak na vstupu sayısal değeri bir onaltılık basamak yorumlanır. Örneğin, '0' ın girdi 0 değerini döndürür ve 'A' girdisi 10 değerini döndürür. Bu işlev, girdi karakteri bir onaltılık rakam değil, -1 döndürür.  
  
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
 Dönüştürülecek Unicode dizesi  
  
 *nSrc*  
 Unicode dize karakter cinsinden uzunluğu.  
  
 *szDest*  
 Dönüştürülmüş dizeyi almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *nDest*  
 Arabelleğin bayt cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürülmüş dize karakter sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüştürülmüş dize için gerekli arabellek boyutunu belirlemek için 0'ı geçirmek için bu işlevi çağırın. *szDest* ve *nDest*.  
  
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
 *pbSrcData*  
 Kodlanacak verileri içeren arabellek.  
  
 *nSrcLen*  
 Kodlanacak verilerin bayt cinsinden uzunluğu.  
  
 *szDest*  
 Kodlanmış verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szDest*. İşlev başarılı olursa değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabelleği gereken uzunluğu alır.  
  
 *pszCharSet*  
 Karakter dönüştürme için kullanılacak ayarlayın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 "B" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength 
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanacak veri baytı sayısı.  
  
 *nCharsetLen*  
 Karakter dönüştürme için kullanacak şekilde karakter cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış veri tutabilen bir arabellek için gereken karakter sayısı *nSrcLen* bayt.  
  
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
 *szIn*  
 Dönüştürülecek dize.  
  
 *nSrclen*  
 Dönüştürülecek dize karakter cinsinden uzunluğu.  
  
 *szEsc*  
 Dönüştürülmüş dizeyi almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *nDestLen*  
 Arayana ayrılan arabelleğin karakter cinsinden uzunluğu.  
  
 *CertOpenStore*  
 ATL_ESC dönüştürme nasıl gerçekleştirilecek açıklayan bayrakları. 

- ATL_ESC_FLAG_NONE varsayılan davranışı geçersiz kılar. Tırnak işaretleri ve kesme dönüştürülmez.
- ATL_ESC_FLAG_ATTR tırnak işaretleri ve kesme dönüştürülür `&quot;` ve `&apos;` sırasıyla.


  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürülmüş dize karakter cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından gerçekleştirilebilse olası dönüştürmeler tabloda gösterilmiştir:  
  
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
 *szSrc*  
 Analiz edilecek dize.  
  
 *nSrcLen*  
 Dize karakter cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirlenen şekilde bir dizenin içinde bulunan Genişletilmiş karakter sayısını döndürür [IsExtendedChar](#isextendedchar).  
  
## <a name="isextendedchar"></a> IsExtendedChar
Belirli bir karakterin genişletilmiş bir karakter (32 den küçük, 126'dan büyük ve sekme, satır besleme veya satır başı değil) olup olmadığını öğrenmek için bu işlevi çağırın.  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *ch*  
 Test edilecek karakter  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karakter, yanlış aksi uzatıldıysa TRUE.  
  
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
 *pbSrcData*  
 Kodlanacak verileri içeren arabellek.  
  
 *nSrcLen*  
 Kodlanacak verilerin bayt cinsinden uzunluğu.  
  
 *szDest*  
 Kodlanmış verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szDest*. İşlev başarılı olursa değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabelleği gereken uzunluğu alır.  
  
 *pszCharSet*  
 Karakter dönüştürme için kullanılacak ayarlayın.  
  
 *pnNumEncoded*  
 Geri dönüş dönüştürülecek olan güvenli olmayan karakter sayısını içeren bir değişken için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 "Q" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength 
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanacak veri baytı sayısı.  
  
 *nCharsetLen*  
 Karakter dönüştürme için kullanacak şekilde karakter cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış veri tutabilen bir arabellek için gereken karakter sayısı *nSrcLen* bayt.  
  
### <a name="remarks"></a>Açıklamalar  
 "Q" kodlama düzeni RFC 2047 açıklanan ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qpdecode"></a> QPDecode
Sınırlandırılmış Yazdırılabilir biçimde gibi önceki bir çağrı tarafından kodlanmış veri dizisinin kodunu çözer [QPEncode](#qpencode).  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pbSrcData*  
 Kodu çözülecek veriler içeren arabellek.  
  
 [in] *nSrcLen*  
 Bayt cinsinden uzunluğu *pbSrcData*.  
  
 [out] *szDest*  
 Kodu çözülmüş verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 [out] *pnDestLen*  
 Bayt cinsinden uzunluğunu içeren bir değişken işaretçisi *szDest*. İşlev başarılı olursa değişken arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişken arabelleğin bayt cinsinden gerekli uzunluğunu alır.  
  
 [in] *CertOpenStore*  
 Dönüştürme nasıl gerçekleştirilecek açıklayan bayrakları. Bkz: [ATLSMTP_QPENCODE bayrakları](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınırlandırılmış Yazdırılabilir kodlama düzenini RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength
Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanmış dize karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodu çözülen dize, tutabilen bir arabellek için gereken bayt sayısını *nSrcLen* karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınırlandırılmış Yazdırılabilir kodlama düzenini RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
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
 *pbSrcData*  
 Kodlanacak verileri içeren arabellek.  
  
 *nSrcLen*  
 Kodlanacak verilerin bayt cinsinden uzunluğu.  
  
 *szDest*  
 Kodlanmış verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szDest*. İşlev başarılı olursa değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabelleği gereken uzunluğu alır.  
  
 *CertOpenStore*  
 Dönüştürme nasıl gerçekleştirilecek açıklayan ATLSMTP_QPENCODE bayraklar. 
- ATLSMTP_QPENCODE_DOT nokta bir satırın başlangıcında görünür, bu çıktısına eklendi hem de kodlanmış.
- ATLSMTP_QPENCODE_TRAILING_SOFT ekler `=\r\n` kodlanmış dize.

Sınırlandırılmış Yazdırılabilir kodlama düzenini açıklanan [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt).
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınırlandırılmış Yazdırılabilir kodlama düzenini RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanacak veri baytı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış veri tutabilen bir arabellek için gereken karakter sayısı *nSrcLen* bayt.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınırlandırılmış Yazdırılabilir kodlama düzenini RFC 2045 açıklanan ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="uudecode"></a> UUDecode
Önceki bir çağrı uuencoded olarak bırakıldı veri dizisinin kodunu çözer [UUEncode](#uuencode).  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 *pbSrcData*  
 Kodu çözülecek veriler içeren dize.  
  
 *nSrcLen*  
 Bayt cinsinden uzunluğu *pbSrcData*.  
  
 *pbDest*  
 Kodu çözülmüş verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Bayt cinsinden uzunluğunu içeren bir değişken işaretçisi *pbDest*. İşlev başarılı olursa değişken arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişken arabelleğin bayt cinsinden gerekli uzunluğunu alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulama POSIX P1003.2b/D11 izler.  
  
## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength
Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanmış dize karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodu çözülen dize, tutabilen bir arabellek için gereken bayt sayısını *nSrcLen* karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulama POSIX P1003.2b/D11 izler.  
  
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
 *pbSrcData*  
 Kodlanacak verileri içeren arabellek.  
  
 *nSrcLen*  
 Kodlanacak verilerin bayt cinsinden uzunluğu.  
  
 *szDest*  
 Kodlanmış verileri almak için çağırıcı tarafından ayrılan arabelleği.  
  
 *pnDestLen*  
 Karakter cinsinden uzunluğunu içeren bir değişken işaretçisi *szDest*. İşlev başarılı olursa değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken karakter arabelleği gereken uzunluğu alır.  
  
 *lpszFile*  
 ATLSMTP_UUENCODE_HEADER belirtildiğinde üstbilgiye eklenecek dosyanın *CertOpenStore*.  
  
 *CertOpenStore*  
 Bu işlevin davranışını denetleyen bayraklar. 
- Üst bilgi ATLSMTP_UUENCODE_HEADE kodlanmış olmalıdır.
- Son ATLSMTP_UUENCODE_END kodlanmış olmalıdır.
- ATLSMTP_UUENCODE_DOT veri doldurmak gerçekleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulama POSIX P1003.2b/D11 izler.  
  
## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength
Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcLen*  
 Kodlanacak veri baytı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kodlanmış veri tutabilen bir arabellek için gereken karakter sayısı *nSrcLen* bayt.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu uuencoding uygulama POSIX P1003.2b/D11 izler.  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)   