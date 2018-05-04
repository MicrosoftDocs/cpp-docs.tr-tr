---
title: memmove_s, wmemmove_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wmemmove_s
- memmove_s
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
- wmemmove_s
- memmove_s
dev_langs:
- C++
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39fde456dd2e45d38bdd1b6ba8d9d7eb9811dd05
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="memmoves-wmemmoves"></a>memmove_s, wmemmove_s

Bir arabellek diğerine taşır. Sürümleri bunlar [memmove, wmemmove](memmove-wmemmove.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t memmove_s(
   void *dest,
   size_t numberOfElements,
   const void *src,
   size_t count
);
errno_t wmemmove_s(
   wchar_t *dest,
   size_t numberOfElements,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Hedef nesne.

*numberOfElements*<br/>
Hedef arabellek boyutu.

*src*<br/>
Kaynak nesne.

*Sayısı*<br/>
Bayt sayısı (**memmove_s**) veya karakter (**wmemmove_s**) kopyalamak için.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatasında bir hata kodu

### <a name="error-conditions"></a>Hata koşulları

|*Hedef*|*numberOfElements*|*src*|Dönüş değeri|İçeriği *hedef*|
|------------|------------------------|-----------|------------------|------------------------|
|**NULL**|tüm|tüm|**EINVAL**|değiştirilmedi|
|tüm|tüm|**NULL**|**EINVAL**|değiştirilmedi|
|tüm|< *Sayısı*|tüm|**ERANGE**|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

Kopya *sayısı* karakterlerinden baytını *src* için *taşınmaya*. Kaynak alan ve hedef bazı bölümlerinin çakışırsa, **memmove_s** çakışan bölgede özgün kaynak bayt üzerine önce kopyalanır sağlar.

Varsa *taşınmaya* veya *src* null işaretçi ya da hedef dize çok küçük ise, bu işlevlerin bir geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **EINVAL** ve **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memmove_s**|\<String.h >|
|**wmemmove_s**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_memmove_s.c
//
// The program demonstrates the
// memmove_s function which works as expected
// for moving overlapping regions.

#include <stdio.h>
#include <string.h>

int main()
{
   char str[] = "0123456789";

   printf("Before: %s\n", str);

   // Move six bytes from the start of the string
   // to a new position shifted by one byte. To protect against
   // buffer overrun, the secure version of memmove requires the
   // the length of the destination string to be specified.

   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);

   printf_s(" After: %s\n", str);
}
```

### <a name="output"></a>Çıkış

```Output
Before: 0123456789
After: 0012345789
```

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
