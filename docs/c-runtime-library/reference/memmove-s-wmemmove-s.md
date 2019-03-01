---
title: memmove_s, wmemmove_s
ms.date: 11/04/2016
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemmove_s
- memmove_s
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
ms.openlocfilehash: 28d879a205790d1f132caca1022d0740e317c342
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210607"
---
# <a name="memmoves-wmemmoves"></a>memmove_s, wmemmove_s

Bir arabellek diğerine taşır. Bunlar sürümleridir [memmove, wmemmove](memmove-wmemmove.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Hedef arabelleğin boyutu.

*src*<br/>
Kaynak nesne.

*Sayısı*<br/>
Bayt sayısı (**memmove_s**) veya karakterleri (**wmemmove_s**) kopyalamak için.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu

### <a name="error-conditions"></a>Hata koşulları

|*Hedef*|*numberOfElements*|*src*|Dönüş değeri|İçeriğini *dest*|
|------------|------------------------|-----------|------------------|------------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|değiştirilmedi|
|Tüm|Tüm|**NULL**|**EINVAL**|değiştirilmedi|
|Tüm|< *Sayısı*|Tüm|**ERANGE**|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

Kopya *sayısı* karakterlerinden bayt *src* için *dest*. Bazı kaynak alanını ve hedef bölgelerini çakışırsa, **memmove_s** üzerine önce çakışan bölgede özgün kaynak bayt kopyalanır sağlar.

Varsa *dest* veya *src* null bir işaretçiyse veya hedef dize çok küçükse, bu işlevler geçersiz parametre işleyicisini de açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EINVAL** ayarlayıp **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memmove_s**|\<String.h >|
|**wmemmove_s**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
