---
title: memcpy_s, wmemcpy_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- wmemcpy_s
- memcpy_s
dev_langs:
- C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12bf97e596a7cb4e3befa4c0633a8ef2df29a6d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s

Arabellekler arasında kopyaları bayt sayısı. Sürümleri bunlar [memcpy, wmemcpy](memcpy-wmemcpy.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Hedef arabellek memcpy_s ve geniş karakterler (wchar_t) wmemcpy_s için için bayt cinsinden boyutu.

*src*<br/>
Kopyalanacak arabelleği.

*Sayısı*<br/>
Kopyalamak için karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatasında bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*Hedef*|*destSize*|*src*|*Sayısı*|Dönüş değeri|İçeriği *hedef*|
|------------|----------------|-----------|---|------------------|------------------------|
|tüm|tüm|tüm|0|0|değiştirilmedi|
|**NULL**|tüm|tüm|sıfır olmayan|**EINVAL**|değiştirilmedi|
|tüm|tüm|**NULL**|sıfır olmayan|**EINVAL**|*Hedef* sıfırlanmasını|
|tüm|< *Sayısı*|tüm|sıfır olmayan|**ERANGE**|*Hedef* sıfırlanmasını|

## <a name="remarks"></a>Açıklamalar

**memcpy_s** kopya *sayısı* baytlar *src* için *taşınmaya*; **wmemcpy_s** kopya *sayısı* geniş karakterler (iki bayt cinsinden). Kaynak ve hedef çakışma varsa, davranışını **memcpy_s** tanımlanmadı. Kullanım **memmove_s** çakışan bölgeler işlemek için.

Bu işlevler kendi parametreleri doğrulayın. Varsa *sayısı* sıfır değil ve *taşınmaya* veya *src* null işaretçinin veya *destSize* değerinden küçük *sayısı*, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **EINVAL** veya **ERANGE** ve **errno** dönüş değeri için.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcpy_s**|\<Memory.h > veya \<string.h >|
|**wmemcpy_s**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
