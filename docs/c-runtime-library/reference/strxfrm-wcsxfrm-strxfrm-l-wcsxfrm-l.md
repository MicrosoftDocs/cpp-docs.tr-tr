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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 3ab3f978d4162f968f518272612c18767247f2fb
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912348"
---
# <a name="strxfrm-wcsxfrm-_strxfrm_l-_wcsxfrm_l"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

Bir dizeyi yerel ayara özgü bilgilere göre dönüştürün.

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
Hedef dize.

*strSource*<br/>
Kaynak dize.

*biriktirme*<br/>
*StrDest*içinde yerleştirilecek en fazla karakter sayısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Döndürülen boş karakteri saymayan, dönüştürülmüş dizenin uzunluğunu döndürür. Dönüş değeri *sayımla*eşit veya daha büyükse, *strDest* içeriği tahmin edilemez. Bir hatada, her işlev **errno** ayarlar ve **INT_MAX**döndürür. Geçersiz bir karakter için **errno** , **eilseq**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Strxfrm** işlevi, *strSource* tarafından Işaret edilen dizeyi *strDest*içinde depolanan yeni bir harmanlanmış forma dönüştürür. Null karakter dahil olmak üzere en fazla *sayı* karakteri dönüştürülür ve sonuç dizesine konur. Dönüştürme, yerel ayarın **LC_COLLATE** kategori ayarı kullanılarak yapılır. **LC_COLLATE**hakkında daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). **strxfrm** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_strxfrm_l** , geçerli yerel ayar yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Dönüşümden sonra, iki dönüştürülmüş dize içeren bir **strcmp** çağrısı, özgün iki dizeye uygulanan bir **strcoll** çağrısıyla aynı sonuçları verir. **Strcoll** ve **stricoll**ile birlikte, **strxfrm** uygun şekilde çok baytlı karakter dizelerini otomatik olarak işler.

**wcsxfrm** , **strxfrm**; öğesinin geniş karakterli bir sürümüdür. **wcsxfrm** 'nin dize bağımsız değişkenleri geniş karakter işaretçileridir. **Wcsxfrm**için, dize dönüşümünde, **wcscmp** öğesine yapılan bir çağrı, özgün iki dizeye uygulanan bir **wcscoll** çağrısıyla aynı sonucu verir. **wcsxfrm** ve **strxfrm** aynı şekilde davranır. **wcsxfrm** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_wcsxfrm_l** , geçerli yerel ayar yerine geçirilen yerel ayarı kullanır.

Bu işlevler, parametrelerini doğrular. *StrSource* null bir Işaretçiyse veya *strDest* **null** işaretçiyse (sayı sıfır değilse) veya *sayı* **INT_MAX**büyükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **INT_MAX**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" yerel ayarında, karakter kümesindeki karakterlerin sırası (ASCII karakter kümesi), karakterlerin lexicographic sıralaması ile aynıdır. Ancak, diğer yerel ayarlarda, karakter kümesindeki karakterlerin sırası lexicographic karakter sıraından farklı olabilir. Örneğin, bazı Avrupa yerel ayarlarda, ' a ' karakteri (0x61 değeri) ' &\#x00E4; ' karakterinden önce (değer 0xE4) karakter kümesinde, ancak ' ä ' karakteri ' a ' lexıgrafik karakterinden önce gelir.

Karakter kümesi ve lexicographic karakter sırasının farklı olduğu yerel ayarlarda, özgün dizeler üzerinde **strxfrm** ' yi ve ardından elde edilen dizelerde **strcmp** ' i kullanarak geçerli yerel ayarın **LC_COLLATE** kategori ayarına göre bir lexicographic dize karşılaştırması oluşturun. Bu nedenle, yukarıdaki yerel ayarda iki dizeyi lexıgrafik olarak karşılaştırmak için, özgün dizelerde **strxfrm** , sonra da elde edilen dizelerde **strcmp** komutunu kullanın. Alternatif olarak, özgün dizelerde **strcmp** yerine **strcoll** kullanabilirsiniz.

**strxfrm** , **LCMAP_SORTKEY**ile [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw) etrafında bir sarmalayıcı.

Aşağıdaki ifadenin değeri, kaynak dizenin **strxfrm** dönüşümünü tutmak için gereken dizinin boyutudur:

`1 + strxfrm( NULL, string, 0 )`

Yalnızca "C" yerel ayarında, **strxfrm** aşağıdaki şekilde eşdeğerdir:

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strxfrm**|\<String. h>|
|**wcsxfrm**|\<String. h> veya \<wchar. h>|
|**_strxfrm_l**|\<String. h>|
|**_wcsxfrm_l**|\<String. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
