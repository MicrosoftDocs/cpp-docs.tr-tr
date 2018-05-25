---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc9746d2c98f1799cbdd244e7fc4d465fd705fa
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

Yerel ayarlara özgü bilgilere dayalı bir dize dönüştürün.

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
Yerleştirmek için karakter üst sınırını *strDest*.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sondaki boş karakter saymaz dönüştürülmüş dize uzunluğunu döndürür. Dönüş değeri sıfırdan büyük veya eşit olup olmadığını *sayısı*, içeriği *strDest* tahmin edilemez. Bir hata, her işlev ayarlar **errno** ve döndürür **INT_MAX**. Geçersiz bir karakter için **errno** ayarlanır **EILSEQ**.

## <a name="remarks"></a>Açıklamalar

**Strxfrm** işlevi dönüştüren gösterdiği dize *strSource* yeni dosyaya depolanır form Harmanlanmış *strDest*. En fazla *sayısı* null karakteri gibi karakterler dönüştürülen ve sonuçta elde edilen dizeye yerleştirilir. Dönüştürme yerel kullanılarak yapılan **LC_COLLATE** kategori ayarı. Daha fazla bilgi için **LC_COLLATE**, bkz: [setlocale](setlocale-wsetlocale.md). **strxfrm** yerel ayara bağımlı davranışı için; geçerli yerel ayarı kullanır **_strxfrm_l** geçerli yerel yerine geçilen yerel kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Dönüştürme için bir çağrı sonra **strcmp** iki dönüştürülmüş dizeyi ile yapılan bir çağrı içeriğiyle aynı sonuçları verir **strcoll** özgün iki dizeyi uygulanır. İle **strcoll** ve **stricoll**, **strxfrm** çok baytlı karakter dizeleri uygun şekilde otomatik olarak yönetir.

**wcsxfrm** bir joker karakter sürümü **strxfrm**; dize bağımsız değişkenleri **wcsxfrm** joker karakter işaretçiler. İçin **wcsxfrm**, sonra dize dönüştürme, bir çağrı **wcscmp** iki dönüştürülmüş dizeyi ile yapılan bir çağrı içeriğiyle aynı sonuçları verir **wcscoll** uygulanır özgün iki dize. **wcsxfrm** ve **strxfrm** Aksi takdirde aynı şekilde davranır. **wcsxfrm** yerel ayara bağımlı davranışı için; geçerli yerel ayarı kullanır **_wcsxfrm_l** geçerli yerel yerine geçilen yerel ayar kullanır.

Bu işlevler kendi parametreleri doğrulayın. Varsa *strSource* null işaretçinin veya *strDest* olan bir **NULL** işaretçisi (sayısı sıfır değilse), veya *sayısı* büyük**INT_MAX**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **INT_MAX**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" yerel ayarını karakter (ASCII karakter kümesi) karakter kümesinde sırasını karakterleri lexicographic sırasını ile aynıdır. Ancak, diğer yerlerde karakter kümesinden karakter sırasını lexicographic karakter siparişte farklı olabilir. Örneğin, bazı Avrupa yerlerde karakter 'a' (değer 0x61) karakterinden önce gelen ' &\#x00E4;' (değer 0xE4) karakter kümesi, ancak karakteri 'ä' karakter 'a' lexicographically önce gelir.

Karakter kümesi ve lexicographic karakter sırası için farklı yerlerde kullanmak **strxfrm** özgün dizeler ve ardından **strcmp** lexicographic dize üretmek için sonuçta elde edilen dizeler Geçerli yerel göre karşılaştırma **LC_COLLATE** kategori ayarı. Bu nedenle, iki dizelerde lexicographically yukarıdaki yerel karşılaştırmak için kullanın **strxfrm** özgün dizeler, ardından **strcmp** elde edilen dizelerde. Alternatif olarak, kullanabileceğiniz **strcoll** yerine **strcmp** özgün dizelerde.

**strxfrm** temelde çevresinde bir sarmalayıcı olan [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) ile **LCMAP_SORTKEY**.

Tutmak için gerekli dizinin boyutu aşağıdaki ifade değeri **strxfrm** kaynak dizesi dönüşümü:

`1 + strxfrm( NULL, string, 0 )`

Yalnızca, "C" yerel **strxfrm** şuna eşdeğerdir:

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

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
