---
title: memmove_s, wmemmove_s
ms.date: 4/2/2020
api_name:
- wmemmove_s
- memmove_s
- _o_wmemmove_s
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemmove_s
- memmove_s
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
ms.openlocfilehash: baec33046f891f64c04adeccf21f41d3eec7b814
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333148"
---
# <a name="memmove_s-wmemmove_s"></a>memmove_s, wmemmove_s

Bir arabelleği diğerine taşır. Bunlar [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [memmove, wmemmove](memmove-wmemmove.md) sürümleridir.

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

*Dest*<br/>
Hedef nesnesi.

*numberOfElements*<br/>
Hedef arabelleğe boyutu.

*src*<br/>
Kaynak nesne.

*Sayısı*<br/>
Kopyalanması gereken bayt **(memmove_s)** veya karakter **(wmemmove_s)** sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu

### <a name="error-conditions"></a>Hata Koşulları

|*Dest*|*numberOfElements*|*src*|Döndürülen değer|*Dest'in* içindekiler|
|------------|------------------------|-----------|------------------|------------------------|
|**Null**|herhangi bir|herhangi bir|**Eınval**|değiştirilmemiş|
|herhangi bir|herhangi bir|**Null**|**Eınval**|değiştirilmemiş|
|herhangi bir|< *Sayısı*|herhangi bir|**Erange**|değiştirilmemiş|

## <a name="remarks"></a>Açıklamalar

Kopyalar *src* den *dest*karakter baytsayısı . *count* Kaynak alanın bazı bölgeleri ve hedef çakışıyorsa, **memmove_s** çakışan bölgedeki orijinal kaynak baytlarının üzerine yazılmadan önce kopyalanmasını sağlar.

*Dest* veya *src* null işaretçisi ise veya hedef dize çok küçükse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** döndürün ve **EINVAL** **için errno** ayarlayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memmove_s**|\<string.h>|
|**wmemmove_s**|\<wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

### <a name="output"></a>Çıktı

```Output
Before: 0123456789
After: 0012345789
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Manipülasyonu](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
