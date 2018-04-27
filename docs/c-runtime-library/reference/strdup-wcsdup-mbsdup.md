---
title: _strdup, _wcsdup, _mbsdup | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _strdup
- _mbsdup
- _wcsdup
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
dev_langs:
- C++
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbbcc3be904cd643d1810bbe61f4869405364371
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strdup-wcsdup-mbsdup"></a>_strdup, _wcsdup, _mbsdup

Dizeleri çoğaltır.

> [!IMPORTANT]
> **_mbsdup** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_strdup(
   const char *strSource
);
wchar_t *_wcsdup(
   const wchar_t *strSource
);
unsigned char *_mbsdup(
   const unsigned char *strSource
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Sonlandırılmış kaynak dizesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir işaretçi kopyalanan dize için depolama konumunu döndürür veya **NULL** depolama ayırdığınızda.

## <a name="remarks"></a>Açıklamalar

**_Strdup** işlev çağrıları [malloc](malloc.md) kopyası için depolama alanı ayırmak için *strSource* ve ardından kopyalar *strSource* için ayrılmış alanı.

**_wcsdup** ve **_mbsdup** joker karakter ve çok baytlı karakter sürümleri **_strdup**. Bağımsız değişkenleri ve dönüş değerini **_wcsdup** joker karakter olan dizeleri; bu **_mbsdup** çok baytlı karakter dizeleri belirtilmiştir. Bu üç işlevler aynı şekilde aksi davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup**|**_strdup**|**_mbsdup**|**_wcsdup**|

Çünkü **_strdup** çağrıları **malloc** kopyası için depolama alanı ayırmak için *strSource*, her zaman çağrısıyaparakbubelleğiserbestiyibiruygulamadır[boş](free.md) çağrısı tarafından döndürülen işaretçi üzerinde rutin **_strdup**.

Varsa **_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanan **_strdup** ve **_wcsdup** yapılan çağrılar tarafından değiştirilen **_strdup_dbg**  ve **_wcsdup_dbg** bellek ayırmaları hata ayıklama için izin vermek için. Daha fazla bilgi için bkz: [_strdup_dbg, _wcsdup_dbg](strdup-dbg-wcsdup-dbg.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdup**|\<String.h >|
|**_wcsdup**|\<String.h > veya \<wchar.h >|
|**_mbsdup**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strdup.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is the buffer text";
   char *newstring;
   printf( "Original: %s\n", buffer );
   newstring = _strdup( buffer );
   printf( "Copy:     %s\n", newstring );
   free( newstring );
}
```

```Output
Original: This is the buffer text
Copy:     This is the buffer text
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
