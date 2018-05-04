---
title: _strdec, _wcsdec, _mbsdec, mbsdec_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c73813c406011eaadd540398d3364ec183f8deaf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strdec-wcsdec-mbsdec-mbsdecl"></a>_strdec, _wcsdec, _mbsdec, _mbsdec_l

Bir dize işaretçi bir karakter geriye taşır.

> [!IMPORTANT]
> **mbsdec** ve **mbsdec_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Başlat*<br/>
Herhangi bir karakter işaretçisine (veya **_mbsdec** ve **mbsdec_l**, herhangi bir birden çok baytlı karakter ilk baytını) kaynak dizesinde; *Başlat* gelmelidir *geçerli* kaynak dizesi içinde.

*Geçerli*<br/>
Herhangi bir karakter işaretçisine (veya **_mbsdec** ve **mbsdec_l**, herhangi bir birden çok baytlı karakter ilk baytını) kaynak dizesinde; *geçerli* izlemelisiniz *Başlat* kaynak dizesi içinde.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsdec**, **mbsdec_l**, **_strdec**, ve **_wcsdec** hemen önce gelen karakter her iade bir işaretçi *geçerli*; **_mbsdec** döndürür **NULL** varsa değerini *Başlat* büyük veya eşit *geçerli*. **_tcsdec** bu işlevleri ve dönüş değerini birine eşlemeleri eşlemesini bağlıdır.

## <a name="remarks"></a>Açıklamalar

**_Mbsdec** ve **mbsdec_l** işlevler hemen önce gelen birden çok baytlı karakter ilk bayta kalan için bir işaretçi döndürür *geçerli* içeren dize olarak *Başlat*.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için.  **_mbsdec** şu anda kullanımda olan yerel göre çok baytlı karakter sıralarının tanıdığı sırada **mbsdec_l** yerine geçirilen yerel ayar parametresi kullanır dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *Başlat* veya *geçerli* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

> [!IMPORTANT]
> Bu işlevler taşması tehditlerine karşı savunmasız olabilir. Arabellek aşırı çalıştırmaları unwarranted ayrıcalıkların nedeni sistem saldırıları için kullanılabilir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsdec**|**_strdec**|**_mbsdec**|**_wcsdec**|

**_strdec** ve **_wcsdec** tek bayt karakter ve joker karakter sürümleri **_mbsdec** ve **mbsdec_l**. **_strdec** ve **_wcsdec** yalnızca bu eşleme için sağlanır ve aksi durumda kullanılmamalıdır.

Daha fazla bilgi için bkz: [kullanarak genel metin eşlemeleri](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_mbsdec**|\<Mbstring.h >|\<Mbctype.h >|
|**_mbsdec_l**|\<Mbstring.h >|\<Mbctype.h >|
|**_strdec**|\<Tchar.h >||
|**_wcsdec**|\<Tchar.h >||

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir kullanımını gösterir **_tcsdec**.

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

Aşağıdaki örnek, bir kullanımını gösterir **_mbsdec**.

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
