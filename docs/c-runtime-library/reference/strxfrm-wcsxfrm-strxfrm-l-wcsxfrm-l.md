---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
ms.date: 11/04/2016
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 4e4f5bb6639cbeee0f004f94f09177c08394d43e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590989"
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

Yerel ayara özgü bilgilere göre bir dize dönüştürür.

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
Kaynak dizesi.

*Sayısı*<br/>
En fazla yerleştirmek için karakter sayısını *strDest*.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sondaki null karakter sayılmaz dönüştürülmüş dize uzunluğunu döndürür. Dönüş değeri büyük veya ona eşit olup olmadığını *sayısı*, içeriği *strDest* tahmin edilemez. Her işlev bir hata, ayarlar **errno** ve döndürür **INT_MAX**. Geçersiz bir karakter için **errno** ayarlanır **EILSEQ**.

## <a name="remarks"></a>Açıklamalar

**Strxfrm** işlevi tarafından işaret edilen dizenin dönüştüren *strSource* yeni dosyaya depolanır form Harmanlanmış *strDest*. En fazla *sayısı* null karakter de dahil olmak üzere karakter dönüştürülür ve sonuç dizesine yerleştirilir. Dönüştürme, yerel ayarın kullanarak yapılan **LC_COLLATE** kategori ayarı. Daha fazla bilgi için **LC_COLLATE**, bkz: [setlocale](setlocale-wsetlocale.md). **strxfrm** yerel ayara bağlı davranışı için; geçerli yerel ayarı kullanır **_strxfrm_l** geçerli yerel ayarı yerine iletilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Sonra bir çağrı dönüştürme **strcmp** iki dönüştürülmüş dize ile çağrı aynı sonuçları verir **strcoll** özgün iki dizenin için uygulanır. Olduğu gibi **strcoll** ve **stricoll**, **strxfrm** çok baytlı karakter dizelerini uygun şekilde otomatik olarak işler.

**wcsxfrm** geniş karakterli sürümüdür **strxfrm**; dize bağımsız değişkenleri **wcsxfrm** geniş karakter işaretçiler. İçin **wcsxfrm**, sonra dize dönüşümü, çağrı **wcscmp** iki dönüştürülmüş dize ile çağrı aynı sonuçları verir **wcscoll** uygulanır özgün iki dize. **wcsxfrm** ve **strxfrm** aynı şekilde davranır. **wcsxfrm** yerel ayara bağlı davranışı için; geçerli yerel ayarı kullanır **_wcsxfrm_l** geçerli yerel ayarı yerine iletilen yerel ayarı kullanır.

Bu işlevler kendi parametrelerini doğrular. Varsa *strSource* null bir işaretçiyse veya *strDest* olduğu bir **NULL** işaretçi (sayısı sıfır değilse), veya *sayısı* büyük**INT_MAX**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **INT_MAX**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" yerel ayarında (ASCII karakter kümesi) karakter kümesindeki karakter sırası karakterlerin sözlük sıralamasına göre ile aynıdır. Ancak, diğer yerlerde karakter kümesindeki karakterlerin sırası sözlük karakter sırasından farklı olabilir. Örneğin, Avrupa belirli yerlerde karakter 'a' (değer 0x61) karakterinden önce gelen ' &\#x00E4;' (değer 0xE4) karakter kümesi, ancak karakteri 'ä' karakter 'a' lexicographically önce gelir.

Kendisi için karakter kümesi ve lexicographic karakter sırası farklı yerlerde kullanın **strxfrm** özgün dizeler ardından **strcmp** lexicographic dizesi üretmek için elde edilen dizeler Geçerli yerel ayarın göre karşılaştırma **LC_COLLATE** kategori ayarı. Bu nedenle, iki dizeyi lexicographically yukarıdaki yerel ayarında Karşılaştırılacak kullanın **strxfrm** özgün dizeler, ardından **strcmp** elde edilen dizeler. Alternatif olarak, kullanabileceğiniz **strcoll** yerine **strcmp** özgün dizeler.

**strxfrm** temelde çevresinde bir sarmalayıcı olan [LCMapString](/windows/desktop/api/winnls/nf-winnls-lcmapstringa) ile **LCMAP_SORTKEY**.

Aşağıdaki ifade beklemesi gereken dizinin boyutu değeri **strxfrm** dönüşümü kaynak dizesi:

`1 + strxfrm( NULL, string, 0 )`

Yalnızca "C" yerel ayarında **strxfrm** aşağıdakine eşdeğerdir:

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strxfrm**|\<String.h >|
|**wcsxfrm**|\<String.h > veya \<wchar.h >|
|**_strxfrm_l**|\<String.h >|
|**_wcsxfrm_l**|\<String.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
