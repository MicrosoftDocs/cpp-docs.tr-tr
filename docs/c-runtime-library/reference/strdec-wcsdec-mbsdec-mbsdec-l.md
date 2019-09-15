---
title: _strdec, _wcsdec, _mbsdec, _mbsdec_l
ms.date: 11/04/2016
api_name:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _strdec
- mbsdec_l
- strdec
- _mbsdec
- _mbsdec_l
- mbsdec
- wcsdec
- _wcsdec
helpviewer_keywords:
- mbsdec_l function
- mbsdec function
- tcsdec function
- _tcsdec function
- _strdec function
- _wcsdec function
- _mbsdec_l function
- strdec function
- wcsdec function
- _mbsdec function
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
ms.openlocfilehash: ffb2b81f5ce5a251fb931099a1023a441ca4d496
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958206"
---
# <a name="_strdec-_wcsdec-_mbsdec-_mbsdec_l"></a>_strdec, _wcsdec, _mbsdec, _mbsdec_l

Bir dize işaretçisini bir karakter geri kaydırır.

> [!IMPORTANT]
> **mbsdec** ve **mbsdec_l** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned char *_strdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned wchar_t *_wcsdec(
   const unsigned wchar_t *start,
   const unsigned wchar_t *current
);
unsigned char *_mbsdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned char *_mbsdec_l(
   const unsigned char *start,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*start*<br/>
Kaynak dizedeki herhangi bir karaktere yönelik işaretçi (veya **_mbsdec** ve **_mbsdec_l**için bir çok baytlı karakterin ilk baytı). *Başlangıç* , Kaynak dizedeki *geçerli* öğesinden önce gelmelidir.

*geçerli*<br/>
Kaynak dizedeki herhangi bir karaktere yönelik işaretçi (veya **_mbsdec** ve **_mbsdec_l**için bir çok baytlı karakterin ilk baytı). *geçerli* , Kaynak dizedeki *başlangıçtan* sonra gelmelidir.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsdec**, **_mbsdec_l**, **_strdec**ve **_wcsdec** her biri, hemen *geçerli*olan karaktere bir işaretçi döndürür; **_mbsdec** , *Start* değeri *Current*değerinden büyükse veya eşitse **null** değerini döndürür. **_tcsdec** , bu işlevlerden biriyle eşlenir ve dönüş değeri eşlemeye bağlıdır.

## <a name="remarks"></a>Açıklamalar

**_Mbsdec** ve **_mbsdec_l** işlevleri, *Start*'ı içeren dizedeki hemen *sonra gelen çok* baytlı karakterin ilk baytına bir işaretçi döndürür.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) .  **_mbsdec** , kullanılmakta olan yerel ayara göre çok baytlı karakter dizilerini tanır, ancak bunun yerine geçirilen yerel ayar parametresini kullanması dışında **_mbsdec_l** aynı olduğunda. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Start* veya *Current* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **EINVAL** döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

> [!IMPORTANT]
> Bu işlevler, arabellek taşma tehditlerine karşı savunmasız olabilir. Arabellek taşmaları, sistem saldırıları için kullanılabilir ve bu ayrıcalıklar ayrıcalık yükselmesine neden olabilir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsdec**|**_strdec**|**_mbsdec**|**_wcsdec**|

**_strdec** ve **_wcsdec** , **_mbsdec** ve **_mbsdec_l**öğesinin tek baytlık karakter ve geniş karakterli sürümleridir. **_strdec** ve **_wcsdec** yalnızca bu eşleme için sağlanır ve aksi halde kullanılmamalıdır.

Daha fazla bilgi için bkz. [Genel metin eşlemelerini](../../c-runtime-library/using-generic-text-mappings.md) ve [Genel metin eşlemelerini](../../c-runtime-library/generic-text-mappings.md)kullanma.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_mbsdec**|\<mbstring. h >|\<Mbctype. h >|
|**_mbsdec_l**|\<mbstring. h >|\<Mbctype. h >|
|**_strdec**|\<Tchar. h >||
|**_wcsdec**|\<Tchar. h >||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek **_tcsdec**kullanımını gösterir.

```cpp
// crt_tcsdec.cpp
// Compile by using: cl /EHsc crt_tcsdec.cpp
#include <iostream>
#include <tchar.h>
using namespace std;

int main()
{
   const TCHAR *str = _T("12345");
   cout << "str: " << str << endl;

   const TCHAR *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   TCHAR *answer;
   answer = _tcsdec( str, str2 );
   cout << "answer: " << answer << endl;

   return (0);
}
```

Aşağıdaki örnek, **_mbsdec**kullanımını gösterir.

```cpp
// crt_mbsdec.cpp
// Compile by using: cl /EHsc crt_mbsdec.c
#include <iostream>
#include <mbstring.h>
using namespace std;

int main()
{
   char *str = "12345";
   cout << "str: " << str << endl;

   char *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   unsigned char *answer;
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));

   cout << "answer: " << answer << endl;

   return (0);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
