---
title: _mbsnbcmp, _mbsnbcmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsnbcmp
- _mbsnbcmp_l
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
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
dev_langs:
- C++
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7b48e13e112675556a126783af05c9a6a32e00f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="mbsnbcmp-mbsnbcmpl"></a>_mbsnbcmp, _mbsnbcmp_l

İlk karşılaştırır **n** bayt iki çok baytlı karakter dizeleri.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak dizeleri.

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Alt dizeler sıralı ilişkisi dönüş değerini gösterir *Dize1* ve *dize2*.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* alt dizesidir değerinden *dize2* substring.|
|0|*Dize1* alt dizesidir aynı *dize2* substring.|
|> 0|*Dize1* alt dizesidir büyük *dize2* substring.|

Parametre doğrulama hata **_mbsnbcmp** ve **_mbsnbcmp_l** dönmek **_NLSCMPERROR**, içinde tanımlanan \<string.h > ve \< Mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbcmp** işlevlerini karşılaştırmak en fazla ilk *sayısı* bayt cinsinden *Dize1* ve *dize2* ve belirten bir değeri döndürme alt dizeler arasındaki ilişki. **_mbsnbcmp** büyük küçük harfe duyarlı bir sürümü **_mbsnbicmp**. Farklı **_mbsnbcoll**, **_mbsnbcmp** yerel harmanlama düzeni tarafından etkilenmez. **_mbsnbcmp** geçerli çok baytlı göre çok baytlı karakter sıralarının tanıdığı [kod sayfası](../../c-runtime-library/code-pages.md).

**_mbsnbcmp** benzer **_mbsncmp**dışında **_mbsncmp** dizeleri karakterleri yerine bayt göre karşılaştırır.

Çıkış değerini etkilenir **LC_CTYPE** ön baytlar belirten yerel, ayarlama ve çok baytlı karakterlerin bayt sondaki kategorisi. Daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). **_Mbsnbcmp** işlevi için bu yerel ayara bağımlı davranış geçerli yerel ayarı kullanır. **_Mbsnbcmp_l** kullanır ancak bu işlevi aynı *yerel* parametre yerine. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Her iki *Dize1* veya *dize2* null işaretçi açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş **_NLSCMPERROR** ve **errno** ayarlanır **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|---------------------------------------|--------------------|-----------------------|
|**_tcsncmp**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcmp**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|
|**_tcsncmp_l**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcml**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcmp**|\<Mbstring.h >|
|**_mbsnbcmp_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbsnbcmp.c
#include <mbstring.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n          %s\n", string1 );
   printf( "          %s\n\n", string2 );
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );
   result = _mbsncmp( string1, string2 , 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );
   result = _mbsnicmp( string1, string2, 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
}
```

### <a name="output"></a>Çıkış

```Output
Compare strings:
          The quick brown dog jumps over the lazy fox
          The QUICK brown fox jumps over the lazy dog

Function: _mbsnbcmp (first 10 characters only)
Result:   String 1 is greater than string 2

Function: _mbsnicmp _mbsnicmp (first 10 characters only)
Result:   String 1 is equal to string 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
