---
title: ATL metin kodlama Işlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 330a73e0d41bf384a799635d5f2e6f09f7e3dd03
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833861"
---
# <a name="atl-text-encoding-functions"></a>ATL metin kodlama Işlevleri

Bu işlevler metin kodlamasını ve kod çözmeyi destekler.

|İşlev|Açıklama|
|-|-|
|[AtlGetHexValue](#atlgethexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|
|[AtlGetVersion](#atlgetversion)|Kullanmakta olduğunuz ATL kitaplığının sürümünü almak için bu işlevi çağırın.  |
|[Atlonaltık kodu çözme](#atlhexdecode)|Bir önceki [Atlonaltıl kodlaması](#atlhexencode)çağrısıyla gibi onaltılık metin olarak kodlanmış bir veri dizesinin kodunu çözer.|
|[Atlonaltıdecodegetrequiredlength](#atlhexdecodegetrequiredlength)|Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[Atlonaltıl kodlama](#atlhexencode)|Herhangi bir veriyi onaltılık bir metin dizesi olarak kodlamak için bu işlevi çağırın.|
|[Atlonaltıencodegetrequiredlength](#atlhexencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[Atlonaltıl değeri](#atlhexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Unicode dizesini UTF-8'e dönüştürmek için bu işlevi çağırın. |
|[BEncode](#bencode)|Bazı verileri "B" kodlama kullanarak dönüştürmek için bu işlevi çağırın.|
|[BEncodeGetRequiredLength](#bencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[Çıkar Exml](#escapexml)|XML'de kullanılması güvenli olmayan karakterleri güvenli eşdeğerlerine dönüştürmek için bu işlevi çağırın.|
|[Gebir Dedchars](#getextendedchars)|Bir dizede genişletilmiş karakter sayısını almak için bu işlevi çağırın.|
|[IsExtendedChar](#isextendedchar)|Belirli bir karakterin genişletilmiş bir karakter olup olmadığını bulmak için bu işlevi çağırın (32 ' dan az, 126 ' den büyük olan ve sekme, satır besleme veya satır başı değil)|
|[QEncode](#qencode)|Bazı verileri "Q" kodlama kullanarak dönüştürmek için bu işlevi çağırın.  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[Qpkodunu çöz](#qpdecode)|Daha önceki bir [QPEncode](#qpencode)çağrısıyla gibi tırnaklı yazdırılabilir biçimde kodlanmış bir veri dizesinin kodunu çözer.|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[QPEncode](#qpencode)|Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUDecode](#uudecode)|Daha önceki [uuencode](#uuencode)çağrısıyla gibi uuencoded bir veri dizesinin kodunu çözer.|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUEncode](#uuencode)|Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlenc. h

## <a name="atlgethexvalue"></a><a name="atlgethexvalue"></a> AtlGetHexValue

Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.

```cpp
inline char AtlGetHexValue(char chIn) throw();
```

### <a name="parameters"></a>Parametreler

*chIn*<br/>
' 0 '-' 9 ', ' A'-'F ' veya ' A'-'f ' onaltılık karakteri.

### <a name="return-value"></a>Dönüş Değeri

Giriş karakterinin sayısal değeri, onaltılık bir sayı olarak yorumlanır. Örneğin, ' 0 ' girişi 0 değerini döndürür ve ' A ' girişi 10 değerini döndürür. Giriş karakteri onaltılık bir sayı değilse, bu işlev-1 döndürür.

## <a name="atlgetversion"></a><a name="atlgetversion"></a> AtlGetVersion

Kullanmakta olduğunuz ATL kitaplığının sürümünü almak için bu işlevi çağırın.

```cpp
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);
```

### <a name="parameters"></a>Parametreler

*Korunacağını*<br/>
Ayrılmış bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Derlediğiniz veya çalıştırdığınız ATL Kitaplığı sürümünün DWORD tamsayı değerini döndürür.

## <a name="example"></a>Örnek

İşlevin aşağıdaki şekilde çağrılması gerekir.

[!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlhexdecode"></a><a name="atlhexdecode"></a> Atlonaltık kodu çözme

Bir önceki [Atlonaltıl kodlaması](#atlhexencode)çağrısıyla gibi onaltılık metin olarak kodlanmış bir veri dizesinin kodunu çözer.

```cpp
inline BOOL AtlHexDecode(
   LPCSTR pSrcData,
   int nSrcLen,
   LPBYTE pbDest,
   int* pnDestLen) throw();
```

### <a name="parameters"></a>Parametreler

*pSrcData*<br/>
Kodu çözülecek verileri içeren dize.

*nSrcLen*<br/>
*PSrcData*karakter uzunluğu.

*pbDest*<br/>
Kodu çözülen verileri almak için arayana ayrılan arabellek.

*pnDestLen*<br/>
*PbDest*bayt cinsinden uzunluğu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişken arabelleğin bayt cinsinden gereken uzunluğu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="atlhexdecodegetrequiredlength"></a><a name="atlhexdecodegetrequiredlength"></a> Atlonaltıdecodegetrequiredlength

Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanan dizedeki karakterlerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kodu çözülen *nSrcLen* karakter dizesini tutan bir arabellek için gereken bayt sayısı.

## <a name="atlhexencode"></a><a name="atlhexencode"></a> Atlonaltıl kodlama

Herhangi bir veriyi onaltılık bir metin dizesi olarak kodlamak için bu işlevi çağırın.

```cpp
inline BOOL AtlHexEncode(
   const BYTE * pbSrcData,
   int nSrcLen,
   LPSTR szDest,
int * pnDestLen) throw();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
Kodlanacak verileri içeren arabellek.

*nSrcLen*<br/>
Kodlanan verilerin bayt cinsinden uzunluğu.

*szDest*<br/>
Kodlanmış verileri almak için arayan tarafından ayrılmış arabellek.

*pnDestLen*<br/>
*SzDest*'ın karakter uzunluğunu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken arabelleğin karakter cinsinden gereken uzunluğu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kaynak verilerin her baytı 2 onaltılık karakter olarak kodlanır.

## <a name="atlhexencodegetrequiredlength"></a><a name="atlhexencodegetrequiredlength"></a> Atlonaltıencodegetrequiredlength

Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanacak veri bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

*NSrcLen* bayt kodlu verileri tutabilecek bir arabellek için gereken karakter sayısı.

## <a name="atlhexvalue"></a><a name="atlhexvalue"></a> Atlonaltıl değeri

Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.

```cpp
inline short AtlHexValue(char chIn) throw();
```

### <a name="parameters"></a>Parametreler

*chIn*<br/>
' 0 '-' 9 ', ' A'-'F ' veya ' A'-'f ' onaltılık karakteri.

### <a name="return-value"></a>Dönüş Değeri

Giriş karakterinin sayısal değeri, onaltılık bir sayı olarak yorumlanır. Örneğin, ' 0 ' girişi 0 değerini döndürür ve ' A ' girişi 10 değerini döndürür. Giriş karakteri onaltılık bir sayı değilse, bu işlev-1 döndürür.

## <a name="atlunicodetoutf8"></a><a name="atlunicodetoutf8"></a> AtlUnicodeToUTF8

Unicode dizesini UTF-8'e dönüştürmek için bu işlevi çağırın.

```cpp
ATL_NOINLINE inline int AtlUnicodeToUTF8(
   LPCWSTR wszSrc,
   int nSrc,
   LPSTR szDest,
   int nDest) throw();
```

### <a name="parameters"></a>Parametreler

*wszSrc*<br/>
Dönüştürülecek Unicode dize

*nSrc*<br/>
Unicode dizesinin karakter cinsinden uzunluğu.

*szDest*<br/>
Dönüştürülmüş dizeyi almak için arayan tarafından ayrılan arabellek.

*nDest*<br/>
Arabelleğin bayt cinsinden uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülen dize için karakter sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüştürülen dize için gereken arabelleğin boyutunu öğrenmek için, *szDest* ve *nDest*için 0 geçirerek bu işlevi çağırın.

## <a name="bencode"></a><a name="bencode"></a> BEncode

Bazı verileri "B" kodlama kullanarak dönüştürmek için bu işlevi çağırın.

```cpp
inline BOOL BEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCSTR pszCharSet) throw();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
Kodlanacak verileri içeren arabellek.

*nSrcLen*<br/>
Kodlanan verilerin bayt cinsinden uzunluğu.

*szDest*<br/>
Kodlanmış verileri almak için arayan tarafından ayrılmış arabellek.

*pnDestLen*<br/>
*SzDest*'ın karakter uzunluğunu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken arabelleğin karakter cinsinden gereken uzunluğu alır.

*pszCharSet*<br/>
Dönüştürme için kullanılacak karakter kümesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

"B" kodlama şeması, RFC 2047 () bölümünde açıklanmaktadır [https://www.ietf.org/rfc/rfc2047.txt](https://www.ietf.org/rfc/rfc2047.txt) .

## <a name="bencodegetrequiredlength"></a><a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength

Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanacak veri bayt sayısı.

*nCharsetLen*<br/>
Dönüştürme için kullanılacak karakter kümesinin karakter uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

*NSrcLen* bayt kodlu verileri tutabilecek bir arabellek için gereken karakter sayısı.

### <a name="remarks"></a>Açıklamalar

"B" kodlama şeması, RFC 2047 () bölümünde açıklanmaktadır [https://www.ietf.org/rfc/rfc2047.txt](https://www.ietf.org/rfc/rfc2047.txt) .

## <a name="escapexml"></a><a name="escapexml"></a> Çıkar Exml

XML'de kullanılması güvenli olmayan karakterleri güvenli eşdeğerlerine dönüştürmek için bu işlevi çağırın.

```cpp
inline int EscapeXML(
   const wchar_t * szIn,
   int nSrcLen,
   wchar_t * szEsc,
   int nDestLen,
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();
```

### <a name="parameters"></a>Parametreler

*szın*<br/>
Dönüştürülecek dize.

*nSrclen*<br/>
Dönüştürülecek dizenin karakter cinsinden uzunluğu.

*szEsc*<br/>
Dönüştürülmüş dizeyi almak için arayan tarafından ayrılan arabellek.

*nDestLen*<br/>
Arayan tarafından ayrılan arabelleğin karakter cinsinden uzunluğu.

*dwFlags*<br/>
Dönüştürmenin nasıl gerçekleştirileceğini açıklayan ATL_ESC bayrakları.

- Varsayılan davranışı ATL_ESC_FLAG_NONE. Tırnak işaretleri ve kesme çizgileri dönüştürülmez.
- ATL_ESC_FLAG_ATTR tırnak işaretleri ve kesme çizgileri, `&quot;` ve sırasıyla öğesine dönüştürülür `&apos;` .

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülmüş dizenin karakter cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından gerçekleştirilen olası dönüşümler tabloda gösterilmiştir:

|Kaynak|Hedef|
|------------|-----------------|
|\<|&lt;|
|>|&gt;|
|&|&amp;|
|'|&apos;|
|"|&quot;|

## <a name="getextendedchars"></a><a name="getextendedchars"></a> Gebir Dedchars

Bir dizede genişletilmiş karakter sayısını almak için bu işlevi çağırın.

```cpp
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();
```

### <a name="parameters"></a>Parametreler

*szSrc*<br/>
Çözümlenecek dize.

*nSrcLen*<br/>
Dizenin karakter cinsinden uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

[IsExtendedChar](#isextendedchar)tarafından belirlendiği şekilde dizedeki bulunan genişletilmiş karakter sayısını döndürür.

## <a name="isextendedchar"></a><a name="isextendedchar"></a> IsExtendedChar

Belirli bir karakterin genişletilmiş bir karakter olup olmadığını bulmak için bu işlevi çağırın (32 ' dan az, 126 ' den büyük olan ve sekme, satır besleme veya satır başı değil)

```cpp
inline int IsExtendedChar(char ch) throw();
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*<br/>
Sınanacak karakter

### <a name="return-value"></a>Dönüş Değeri

Karakter genişletilmişse doğru, aksi takdirde yanlış olur.

## <a name="qencode"></a><a name="qencode"></a> QEncode

Bazı verileri "Q" kodlama kullanarak dönüştürmek için bu işlevi çağırın.

```cpp
inline BOOL QEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCSTR pszCharSet,
   int* pnNumEncoded = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
Kodlanacak verileri içeren arabellek.

*nSrcLen*<br/>
Kodlanan verilerin bayt cinsinden uzunluğu.

*szDest*<br/>
Kodlanmış verileri almak için arayan tarafından ayrılmış arabellek.

*pnDestLen*<br/>
*SzDest*'ın karakter uzunluğunu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken arabelleğin karakter cinsinden gereken uzunluğu alır.

*pszCharSet*<br/>
Dönüştürme için kullanılacak karakter kümesi.

*pnNumEncoded*<br/>
Dönüşte bir değişken işaretçisi, dönüştürülmesi gereken güvenli olmayan karakter sayısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

"Q" kodlama şeması, RFC 2047 () bölümünde açıklanmaktadır [https://www.ietf.org/rfc/rfc2047.txt](https://www.ietf.org/rfc/rfc2047.txt) .

## <a name="qencodegetrequiredlength"></a><a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength

Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanacak veri bayt sayısı.

*nCharsetLen*<br/>
Dönüştürme için kullanılacak karakter kümesinin karakter uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

*NSrcLen* bayt kodlu verileri tutabilecek bir arabellek için gereken karakter sayısı.

### <a name="remarks"></a>Açıklamalar

"Q" kodlama şeması, RFC 2047 () bölümünde açıklanmaktadır [https://www.ietf.org/rfc/rfc2047.txt](https://www.ietf.org/rfc/rfc2047.txt) .

## <a name="qpdecode"></a><a name="qpdecode"></a> Qpkodunu çöz

Daha önceki bir [QPEncode](#qpencode)çağrısıyla gibi tırnaklı yazdırılabilir biçimde kodlanmış bir veri dizesinin kodunu çözer.

```cpp
inline BOOL QPDecode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
'ndaki Kodu çözülecek verileri içeren arabellek.

*nSrcLen*<br/>
'ndaki *PbSrcData*bayt cinsinden uzunluğu.

*szDest*<br/>
dışı Kodu çözülen verileri almak için arayana ayrılan arabellek.

*pnDestLen*<br/>
dışı *SzDest*bayt cinsinden uzunluğu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişken arabelleğin bayt cinsinden gereken uzunluğu alır.

*dwFlags*<br/>
'ndaki Dönüştürmenin nasıl gerçekleştirileceğini açıklayan ATLSMTP_QPENCODE bayrakları.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Tırnaklı yazdırılabilir kodlama şeması, RFC 2045 () içinde açıklanmaktadır [https://www.ietf.org/rfc/rfc2045.txt](https://www.ietf.org/rfc/rfc2045.txt) .

## <a name="qpdecodegetrequiredlength"></a><a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength

Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanan dizedeki karakterlerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kodu çözülen *nSrcLen* karakter dizesini tutan bir arabellek için gereken bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Tırnaklı yazdırılabilir kodlama şeması, RFC 2045 () içinde açıklanmaktadır [https://www.ietf.org/rfc/rfc2045.txt](https://www.ietf.org/rfc/rfc2045.txt) .

## <a name="qpencode"></a><a name="qpencode"></a> QPEncode

Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.

```cpp
inline BOOL QPEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   DWORD dwFlags = 0) throw ();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
Kodlanacak verileri içeren arabellek.

*nSrcLen*<br/>
Kodlanan verilerin bayt cinsinden uzunluğu.

*szDest*<br/>
Kodlanmış verileri almak için arayan tarafından ayrılmış arabellek.

*pnDestLen*<br/>
*SzDest*'ın karakter uzunluğunu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken arabelleğin karakter cinsinden gereken uzunluğu alır.

*dwFlags*<br/>
Dönüştürmenin nasıl gerçekleştirileceğini açıklayan ATLSMTP_QPENCODE bayrakları.

- ATLSMTP_QPENCODE_DOT satırın başlangıcında bir nokta görünürse, çıkışa ve kodlanacak şekilde eklenir.

- ATLSMTP_QPENCODE_TRAILING_SOFT `=\r\n` kodlanmış dizeye ekler.

Tırnaklı yazdırılabilir kodlama şeması, [RFC 2045](https://www.ietf.org/rfc/rfc2045.txt)' de açıklanmaktadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Tırnaklı yazdırılabilir kodlama şeması, RFC 2045 () içinde açıklanmaktadır [https://www.ietf.org/rfc/rfc2045.txt](https://www.ietf.org/rfc/rfc2045.txt) .

## <a name="qpencodegetrequiredlength"></a><a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength

Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanacak veri bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

*NSrcLen* bayt kodlu verileri tutabilecek bir arabellek için gereken karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Tırnaklı yazdırılabilir kodlama şeması, RFC 2045 () içinde açıklanmaktadır [https://www.ietf.org/rfc/rfc2045.txt](https://www.ietf.org/rfc/rfc2045.txt) .

## <a name="uudecode"></a><a name="uudecode"></a> UUDecode

Daha önceki [uuencode](#uuencode)çağrısıyla gibi uuencoded bir veri dizesinin kodunu çözer.

```cpp
inline BOOL UUDecode(
   BYTE* pbSrcData,
   int nSrcLen,
   BYTE* pbDest,
   int* pnDestLen) throw ();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
Kodu çözülecek verileri içeren dize.

*nSrcLen*<br/>
*PbSrcData*bayt cinsinden uzunluğu.

*pbDest*<br/>
Kodu çözülen verileri almak için arayana ayrılan arabellek.

*pnDestLen*<br/>
*PbDest*bayt cinsinden uzunluğu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan bayt sayısını alır. İşlev başarısız olursa, değişken arabelleğin bayt cinsinden gereken uzunluğu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu uuencoding uygulama, POSIX P 1003.2 b/D11 belirtimini izler.

## <a name="uudecodegetrequiredlength"></a><a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength

Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanan dizedeki karakterlerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kodu çözülen *nSrcLen* karakter dizesini tutan bir arabellek için gereken bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Bu uuencoding uygulama, POSIX P 1003.2 b/D11 belirtimini izler.

## <a name="uuencode"></a><a name="uuencode"></a> UUEncode

Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın.

```cpp
inline BOOL UUEncode(
   const BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCTSTR lpszFile = _T("file"),
   DWORD dwFlags = 0) throw ();
```

### <a name="parameters"></a>Parametreler

*pbSrcData*<br/>
Kodlanacak verileri içeren arabellek.

*nSrcLen*<br/>
Kodlanan verilerin bayt cinsinden uzunluğu.

*szDest*<br/>
Kodlanmış verileri almak için arayan tarafından ayrılmış arabellek.

*pnDestLen*<br/>
*SzDest*'ın karakter uzunluğunu içeren bir değişkene yönelik işaretçi. İşlev başarılı olursa, değişken arabelleğe yazılan karakter sayısını alır. İşlev başarısız olursa, değişken arabelleğin karakter cinsinden gereken uzunluğu alır.

*lpszFile*<br/>
ATLSMTP_UUENCODE_HEADER *dwFlags*içinde belirtildiğinde üstbilgiye eklenecek dosya.

*dwFlags*<br/>
Bu işlevin davranışını denetleyen bayraklar.

- Üstbilgi kodlanacak ATLSMTP_UUENCODE_HEADE.

- ATLSMTP_UUENCODE_END bitiş kodlanacak.

- ATLSMTP_UUENCODE_DOT veri stuffing gerçekleştirilecek.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu uuencoding uygulama, POSIX P 1003.2 b/D11 belirtimini izler.

## <a name="uuencodegetrequiredlength"></a><a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength

Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.

```cpp
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>Parametreler

*nSrcLen*<br/>
Kodlanacak veri bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

*NSrcLen* bayt kodlu verileri tutabilecek bir arabellek için gereken karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bu uuencoding uygulama, POSIX P 1003.2 b/D11 belirtimini izler.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../atl-com-desktop-components.md)
