---
title: memcpy_s, wmemcpy_s
ms.date: 11/04/2016
apiname:
- memcpy_s
- wmemcpy_s
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
- wmemcpy_s
- memcpy_s
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
ms.openlocfilehash: 802d75307096e649df15b1864b99699fba92a3a1
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210880"
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s

Arabellekler arasında bayt kopyalar. Bunlar sürümleridir [memcpy, wmemcpy](memcpy-wmemcpy.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t memcpy_s(
   void *dest,
   size_t destSize,
   const void *src,
   size_t count
);
errno_t wmemcpy_s(
   wchar_t *dest,
   size_t destSize,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Yeni bir arabellek.

*destSize*<br/>
Hedef arabelleğin memcpy_s ve geniş karakterler (wchar_t) wmemcpy_s için bayt cinsinden boyutu.

*src*<br/>
Arabellek kopyalayın.

*Sayısı*<br/>
Kopyalanacak karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*Hedef*|*destSize*|*src*|*Sayısı*|Dönüş değeri|İçeriğini *dest*|
|------------|----------------|-----------|---|------------------|------------------------|
|Tüm|Tüm|Tüm|0|0|değiştirilmedi|
|**NULL**|Tüm|Tüm|sıfır olmayan|**EINVAL**|değiştirilmedi|
|Tüm|Tüm|**NULL**|sıfır olmayan|**EINVAL**|*Hedef* sıfırlanıyor|
|Tüm|< *Sayısı*|Tüm|sıfır olmayan|**ERANGE**|*Hedef* sıfırlanıyor|

## <a name="remarks"></a>Açıklamalar

**memcpy_s** kopyaları *sayısı* bayt *src* için *dest*; **wmemcpy_s** kopyaları *sayısı* geniş karakterler (iki bayt). Kaynak ve hedef örtüştürürse davranışını **memcpy_s** tanımsızdır. Kullanım **memmove_s** çakışan bölgeleri işlemek için.

Bu işlevler kendi parametrelerini doğrular. Varsa *sayısı* sıfır değil ve *hedef* veya *src* bir null işaretçiyse veya *destSize* değerinden küçük *sayısı*, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EINVAL** veya **ERANGE** ayarlayıp **errno** dönüş değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcpy_s**|\<Memory.h > veya \<string.h >|
|**wmemcpy_s**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_memcpy_s.c
// Copy memory in a more secure way.

#include <memory.h>
#include <stdio.h>

int main()
{
   int a1[10], a2[100], i;
   errno_t err;

   // Populate a2 with squares of integers
   for (i = 0; i < 100; i++)
   {
      a2[i] = i*i;
   }

   // Tell memcpy_s to copy 10 ints (40 bytes), giving
   // the size of the a1 array (also 40 bytes).
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );
   if (err)
   {
      printf("Error executing memcpy_s.\n");
   }
   else
   {
     for (i = 0; i < 10; i++)
       printf("%d ", a1[i]);
   }
   printf("\n");
}
```

```Output
0 1 4 9 16 25 36 49 64 81
```

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
