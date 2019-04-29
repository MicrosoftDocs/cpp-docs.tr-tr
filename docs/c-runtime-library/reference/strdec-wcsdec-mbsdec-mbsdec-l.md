---
title: _strdec, _wcsdec, _mbsdec, _mbsdec_l
ms.date: 11/04/2016
apiname:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
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
ms.openlocfilehash: 7e88bcf5bf7ffc5eba6feecd545cda8f7950829c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353903"
---
# <a name="strdec-wcsdec-mbsdec-mbsdecl"></a>_strdec, _wcsdec, _mbsdec, _mbsdec_l

Bir dize işaretçisine bir karakter geri taşır.

> [!IMPORTANT]
> **mbsdec** ve **mbsdec_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Herhangi bir karaktere bir işaretçi (veya **_mbsdec** ve **mbsdec_l**, herhangi bir karakterin ilk baytı); kaynak dizede *Başlat* gelmelidir *geçerli* kaynak dizedeki.

*Geçerli*<br/>
Herhangi bir karaktere bir işaretçi (veya **_mbsdec** ve **mbsdec_l**, herhangi bir karakterin ilk baytı); kaynak dizede *geçerli* izlemelidir *Başlat* kaynak dizedeki.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsdec**, **mbsdec_l**, **_strdec**, ve **_wcsdec** her bir işaretçi döndürür hemen önce gelen karakterin *geçerli*; **_mbsdec** döndürür **NULL** varsa değerini *Başlat* büyük veya ona eşit olan *geçerli*. **_tcsdec** maps bu işlevler ve dönüş değerinin birine eşlemeye bağımlı.

## <a name="remarks"></a>Açıklamalar

**_Mbsdec** ve **mbsdec_l** işlevleri hemen önce gelen çok baytlı karakterin ilk baytına bir işaretçi döndürür *geçerli* içeren bir dize içinde *Başlat*.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için.  **_mbsdec** çok baytlı karakter sıralarını şu anda kullanılmakta olan yerel ayara göre tanır ancak **mbsdec_l** bunun yerine iletilen yerel ayar parametresini kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *Başlat* veya *geçerli* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

> [!IMPORTANT]
> Bu işlevler, arabellek taşma tehditlerine açık olabilir. Arabellek taşmaları, bir unwarranted ayrıcalık yükselmesine neden olabileceği için sistem saldırıları için kullanılabilir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsdec**|**_strdec**|**_mbsdec**|**_wcsdec**|

**_strdec** ve **_wcsdec** tek baytlık karakter ve geniş karakterli sürümleridir **_mbsdec** ve **mbsdec_l**. **_strdec** ve **_wcsdec** yalnızca bu eşleşmeye ilişkin sağlanırlar ve aksi takdirde kullanılmamalıdır.

Daha fazla bilgi için [genel metin eşlemelerini kullanma](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_mbsdec**|\<Mbstring.h >|\<Mbctype.h >|
|**_mbsdec_l**|\<Mbstring.h >|\<Mbctype.h >|
|**_strdec**|\<Tchar.h >||
|**_wcsdec**|\<Tchar.h >||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir. **_tcsdec**.

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

Aşağıdaki örnek, kullanımını gösterir. **_mbsdec**.

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
