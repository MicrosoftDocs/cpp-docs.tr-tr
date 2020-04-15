---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
ms.date: 4/2/2020
api_name:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
- _o__strxfrm_l
- _o__wcsxfrm_l
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
ms.openlocfilehash: aabe7e7c2e44f558b936e0fd4c6fa4a85dc582f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362967"
---
# <a name="strxfrm-wcsxfrm-_strxfrm_l-_wcsxfrm_l"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

Yerel e-özel bilgilere dayalı bir dize dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
size_t strxfrm(
   char *strDest,
   const char *strSource,
   size_t count
);
size_t wcsxfrm(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
size_t _strxfrm_l(
   char *strDest,
   const char *strSource,
   size_t count,
   _locale_t locale
);
size_t wcsxfrm_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strDest*<br/>
Hedef dizesi.

*strSource*<br/>
Kaynak dize.

*Sayısı*<br/>
*StrDest'e*yerleştirilecek maksimum karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Null karakterini sonlandırmayı saymayarak dönüştürülen dizeuzun uzunluğunu döndürür. İade değeri *sayımdan*büyük veya eşitse, *strDest'in* içeriği tahmin edilemez. Bir hata da, her işlev **errno** ayarlar ve **INT_MAX**döndürür. Geçersiz bir karakter **için, errno** **EILSEQ**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**strxfrm** işlevi *strSource* tarafından işaret edilen dizeyi *strDest'te*depolanan yeni bir harmanlanmış forma dönüştürür. Null karakteri de dahil olmak üzere *sayı* karakterlerinden fazlası dönüştürülür ve elde edilen dize ye yerleştirilir. Dönüştürme, yerel LC_COLLATE **kategori** ayarı kullanılarak yapılır. **LC_COLLATE**hakkında daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. **strxfrm,** yerele bağımlı davranışı için geçerli yerel durumu kullanır; **_strxfrm_l,** geçerli yerel alan yerine geçirilen yerelliği kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Dönüşümden sonra, iki dönüştürülmüş dize ile **strcmp** bir çağrı orijinal iki dizeleri uygulanan **strcoll** için bir çağrı aynı sonuçları verir. **strcoll** ve **stricoll'da**olduğu gibi **strxfrm,** çok bayt karakterli dizeleri otomatik olarak uygun şekilde işler.

**wcsxfrm** **strxfrm**geniş karakterli bir sürümüdür; **wcsxfrm** dize bağımsız değişkenleri geniş karakter işaretçileridir. **Wcsxfrm**için , dize dönüşümünden sonra, iki dönüştürülmüş dizeleri ile **wcscmp** bir çağrı orijinal iki dizeleri uygulanan **wcscoll** bir çağrı aynı sonuçları verir. **wcsxfrm** ve **strxfrm** aynı şekilde başka türlü çalışır. **wcsxfrm,** yerele bağımlı davranışı için geçerli yerel liği kullanır; **_wcsxfrm_l** geçerli yerel alan yerine geçirilen yerelliği kullanır.

Bu işlevler parametrelerini doğrular. *strSource* null işaretçisi yse veya *strDest* bir **NULL** işaretçisiyse (sayım sıfır değilse) veya *sayım* **INT_MAX**büyükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve **INT_MAX**döndürün.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" tambuslarında, karakter kümesindeki (ASCII karakter kümesi) karakterlerin sırası, karakterlerin lexicographic sırası ile aynıdır. Ancak, diğer yerel ayarlarda, karakter kümesindeki karakterlerin sırası lexicographic karakter sırasına göre farklı olabilir. Örneğin, bazı Avrupa yerel bölgelerinde ,'a' (değer 0x61) karakteri \#'&x00E4;' karakterinden önce gelir. (değer 0xE4) karakter kümesinde, ancak karakter 'ä' karakter 'a' lexicographically önce gelir.

Karakter kümesi ile lexicographic karakter sırasının farklı olduğu yerel ayarlarda, özgün dizelerde **strxfrm** kullanın ve ardından geçerli yerel in **LC_COLLATE** kategori ayarına göre bir lexicographic string karşılaştırması yapmak için ortaya çıkan dizeleri **üzerinde strcmp** kullanın. Böylece, yukarıdaki yerel iki dizeleri lexicographically karşılaştırmak için, özgün dizeleri **üzerinde strxfrm** kullanın, sonra elde edilen dizeleri **üzerinde strcmp.** Alternatif olarak, özgün dizeleri **üzerinde strcmp** yerine **strcoll** kullanabilirsiniz.

**strxfrm** temelde **LCMAP_SORTKEY**ile [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw) etrafında bir sarmalayıcı .

Aşağıdaki ifadenin değeri, kaynak dizesinin **strxfrm** dönüşümünün tutmak için gereken dizinin boyutudur:

`1 + strxfrm( NULL, string, 0 )`

Yalnızca "C" yerel sinde **strxfrm** aşağıdakilere eşdeğerdir:

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> \<veya wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
