---
title: _mbsnbset, _mbsnbset_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbset
- _mbsnbset_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsnbset
- mbsnbset_l
- _mbsnbset
- _mbsnbset_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnset function
- _tcsnset_l function
- _mbsnbset function
- _tcsnset function
- _mbsnbset_l function
- mbsnbset_l function
- tcsnset_l function
- mbsnbset function
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 316580b0c5f1f46ffa9f4a49ef759b347032fc09
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mbsnbset-mbsnbsetl"></a>_mbsnbset, _mbsnbset_l

İlk Ayarlar **n** çok baytlı karakter dizesi belirtilen bir karakterin için bayt. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_mbsnbset_s, _mbsnbset_s_l](mbsnbset-s-mbsnbset-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned char *_mbsnbset(
   unsigned char *str,
   unsigned int c,
   size_t count
);
unsigned char *_mbsnbset_l(
   unsigned char *str,
   unsigned int c,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Değiştirilecek dize.

*c*<br/>
Tek baytlı veya çok baytlı karakter ayarı.

*Sayısı*<br/>
Ayarlanacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbset** bir işaretçi değiştirilmiş dizesi olarak döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbset** ve **_mbsnbset_l** işlevleri ayarla, en fazla ilk *sayısı* bayt *str* için *c*. Varsa *sayısı* uzunluğundan daha büyük *str*, uzunluğu *str* yerine kullanılan *sayısı*. Varsa *c* birden çok baytlı karakter ve tamamen tarafından belirtilen son bayt içine ayarlanamaz *sayısı*, son bayta kalan boş bir karakter ile doldurulan. **_mbsnbset** ve **_mbsnbset_l** bir sonlandırma yerleştirmez sonunda null *str*.

**_mbsnbset** ve **_mbsnbset_l** benzer **_mbsnset**ayarlar dışında *sayısı* bayt yerine *sayısı* karakter *c*.

Varsa *str* olan **NULL** veya *sayısı* sıfır açıklandığı gibi bu işlev geçersiz bir parametre özel bir durum oluşturur [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**. Ayrıca, varsa *c* geçerli bir birden çok baytlı karakter değil **errno** ayarlanır **EINVAL** ve boşluk yerine kullanılır.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. **_Mbsnbset** bu işlev sürümünü kullanan geçerli yerel ayar için bu yerel ayara bağımlı davranışı; **_mbsnbset_l** sürümüne sahip olduğunu aynı kullanmak dışında yerine geçirilen yerel ayar parametresi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

**Güvenlik Notu** bu API taşması sorundan duruma olası bir tehdit doğurur. Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset**|**_strnset**|**_mbsnbset**|**_wcsnset**|
|**_tcsnset_l**|**_strnset_l**|**_mbsnbset_l**|**_wcsnset_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbset**|\<Mbstring.h >|
|**_mbsnbset_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbsnbset.c
// compile with: /W3
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset( string, '*', 4 ); // C4996
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s
   printf( "After:  %s\n", string );
}
```

### <a name="output"></a>Çıkış

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
