---
description: ': Strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l hakkında daha fazla bilgi edinin'
title: strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l
ms.date: 1/20/2021
api_name:
- strncat
- _strncat_l
- _mbsncat
- _mbsncat_l
- wcsncat
- wcsncat_l
- _o__mbsncat
- _o__mbsncat_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsncat_l
- _wcsncat_l
- _tcsnccat_l
- _mbsncat
- _strncat_l
- strncat
- _tcsnccat
- _mbsncat_l
- _ftcsncat
- wcsncat
- _tcsncat
helpviewer_keywords:
- concatenating strings
- ftcsncat function
- tcsncat_l function
- _tcsnccat_l function
- _tcsncat function
- strncat function
- _ftcsncat function
- mbsncat function
- mbsncat_l function
- strings [C++], appending
- wcsncat function
- tcsnccat function
- tcsnccat_l function
- _tcsnccat function
- string concatenation [C++]
- appending strings
- characters [C++], appending to strings
- _mbsncat function
- _tcsncat_l function
- _mbsncat_l function
- tcsncat function
ms.openlocfilehash: 4b5ae812560cb42498ebed71bb9b8791581ef332
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667019"
---
# <a name="strncat-_strncat_l-wcsncat-_wcsncat_l-_mbsncat-_mbsncat_l"></a>strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l

Bir dizenin karakterlerini ekler. Bu işlevlerin daha güvenli sürümleri mevcuttur, bkz `[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l` .] (strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.MD).

> [!IMPORTANT]
> **`_mbsncat`** ve **`_mbsncat_l`** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strncat(
   char *strDest,
   const char *strSource,
   size_t count
);
wchar_t *wcsncat(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
unsigned char *_mbsncat(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count
);
unsigned char *_mbsncat_l(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
char *strncat(
   char (&strDest)[size],
   const char *strSource,
   size_t count
); // C++ only
template <size_t size>
wchar_t *wcsncat(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsncat(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsncat_l(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*`strDest`*\
Null ile sonlandırılmış hedef dizesi.

*`strSource`*\
Null ile sonlandırılmış kaynak dizesi.

*`count`*\
Eklenecek karakter sayısı.

*`locale`*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Hedef dizeye bir işaretçi döndürür. Bir hatayı göstermek için hiçbir dönüş değeri ayrılmadı.

## <a name="remarks"></a>Açıklamalar

**`strncat`** İşlevi, en çok, ' *`count`* nin ilk karakterini ekler *`strSource`* *`strDest`* . Öğesinin ilk karakteri, *`strSource`* Sonlandırıcı null karakterinin üzerine yazar *`strDest`* . Karakterler eklenmeden önce içinde null bir karakter görünürse *`strSource`* *`count`* , **`strncat`** tüm karakterleri *`strSource`* , null karaktere kadar ekler. , *`count`* Uzunluğundan büyükse, yerine öğesinin *`strSource`* uzunluğu *`strSource`* kullanılır *`count`* . Her durumda, sonuçta elde edilen dize bir null karakterle sonlandırılır. Çakışan dizeler arasında kopyalama gerçekleşmesi durumunda davranış tanımsızdır.

> [!IMPORTANT]
> **`strncat`** , içinde yeterli alanı denetlemez *`strDest`* ; Bu nedenle arabellek taşmalarının olası bir nedeni vardır. *`count`* Eklenen karakter sayısını sınırlayan göz önünde bulundurun; bu boyut bir sınır değildir *`strDest`* . Aşağıdaki örneğe bakın. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

**`wcsncat`** ve, **`_mbsncat`** öğesinin geniş karakterli ve çok baytlı karakter sürümleridir **`strncat`** . Dize bağımsız değişkenleri ve dönüş değeri **`wcsncat`** geniş karakterli dizelerdir; bunlar **`_mbsncat`** çok baytlı karakter dizeleridir. Bu üç işlev, aynı şekilde davranır.

Çıkış değeri **`LC_CTYPE`** yerel ayarın kategori ayarı ayarından etkilenir. Daha fazla bilgi için bkz [`setlocale`](setlocale-wsetlocale.md) . daha fazla bilgi için. Bu işlevlerin sonekine sahip olmayan sürümleri, **`_l`** yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. Sonekine sahip sürümler, **`_l`** bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

C++ ' da, bu işlevlerde şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|`TCHAR.H `rutin|`_UNICODE & _MBCS` tanımsız|`_MBCS` tanımlı|`_UNICODE` tanımlı|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_tcsncat`**|**`strncat`**|**`_mbsnbcat`**|**`wcsncat`**|
|**`_tcsncat_l`**|**`_strncat_l`**|**`_mbsnbcat_l`**|**`_wcsncat_l`**|

> [!NOTE]
> **`_strncat_l`** ve **`_wcsncat_l`** yerel ayar bağımlılığını yoktur ve doğrudan çağrılması anlamına gelir. Tarafından iç kullanım için sağlanır **`_tcsncat_l`** .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`strncat`**|\<string.h>|
|**`wcsncat`**|\<string.h> veya \<wchar.h>|
|**`_mbsncat`**|\<mbstring.h>|
|**`_mbsncat_l`**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strncat.c
// Use strcat and strncat to append to a string.
#include <stdlib.h>

#define MAXSTRINGLEN 39

char string[MAXSTRINGLEN+1];
// or char *string = malloc(MAXSTRINGLEN+1);

void BadAppend( char suffix[], int n )
{
   strncat( string, suffix, n );
}

void GoodAppend( char suffix[], size_t n )
{
   strncat( string, suffix, __min( n, MAXSTRINGLEN-strlen(string)) );
}

int main( void )
{
   string[0] = '\0';
   printf( "string can hold up to %d characters\n", MAXSTRINGLEN );

   strcpy( string, "This is the initial string!" );
   // concatenate up to 20 characters...
   BadAppend( "Extra text to add to the string...", 20 );
   printf( "After BadAppend :  %s (%d chars)\n", string, strlen(string) );

   strcpy( string, "This is the initial string!" );
   // concatenate up to 20 characters...
   GoodAppend( "Extra text to add to the string...", 20 );
   printf( "After GoodAppend:  %s (%d chars)\n", string, strlen(string) );
}
```

### <a name="output"></a>Çıktı

```Output
string can hold up to 39 characters
After BadAppend :  This is the initial string!Extra text to add to (47 chars)
After GoodAppend:  This is the initial string!Extra text t (39 chars)
```

**BadAppend** 'in bir arabellek taşmasına neden olduğunu unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)\
[`_mbsnbcat, _mbsnbcat_l`](mbsnbcat-mbsnbcat-l.md)\
[`strcat, wcscat, _mbscat`](strcat-wcscat-mbscat.md)\
[`strcmp, wcscmp, _mbscmp`](strcmp-wcscmp-mbscmp.md)\
[`strcpy, wcscpy, _mbscpy`](strcpy-wcscpy-mbscpy.md)\
[`strncmp, wcsncmp, _mbsncmp, _mbsncmp_l`](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)\
[`strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l`](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)\
[`_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l`](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)\
[`strrchr, wcsrchr, _mbsrchr, _mbsrchr_l`](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)\
[`_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l`](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)\
[`strspn, wcsspn, _mbsspn, _mbsspn_l`](strspn-wcsspn-mbsspn-mbsspn-l.md)\
[Ayarlar](../../c-runtime-library/locale.md)\
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
