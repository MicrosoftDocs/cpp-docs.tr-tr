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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 04f920543c4f6a3d433e6426a96d617a3608a270
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914091"
---
# <a name="memmove_s-wmemmove_s"></a>memmove_s, wmemmove_s

Bir arabelleği diğerine gider. Bu sürümler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [memmove](memmove-wmemmove.md) 'in sürümleridir.

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

*HD*<br/>
Hedef nesne.

*numberOfElements*<br/>
Hedef arabelleğin boyutu.

*src*<br/>
Kaynak nesne.

*biriktirme*<br/>
Kopyalanacak bayt (**memmove_s**) veya karakterlerin (**wmemmove_s**) sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu

### <a name="error-conditions"></a>Hata koşulları

|*HD*|*numberOfElements*|*src*|Döndürülen değer|*Hedef* içeriği|
|------------|------------------------|-----------|------------------|------------------------|
|**DEĞER**|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|değiştirilmedi|
|kaydedilmemiş|kaydedilmemiş|**DEĞER**|**EıNVAL**|değiştirilmedi|
|kaydedilmemiş|< *biriktirme*|kaydedilmemiş|**ERANGE**|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

*Src* 'den *hedefe*kadar olan karakter *sayısını* kopyalar. Kaynak alanın ve hedefin bazı bölgeleri çakışırsa **memmove_s** , çakışan bölgedeki özgün kaynak baytlarının üzerine yazılmadan önce kopyalanmasını sağlar.

Hedef *veya* *kaynak* boş bir işaretçisiyse veya hedef dize çok küçükse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md) açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EINVAL** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memmove_s**|\<String. h>|
|**wmemmove_s**|\<wchar. h>|

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

### <a name="output"></a>Çıktı

```Output
Before: 0123456789
After: 0012345789
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
