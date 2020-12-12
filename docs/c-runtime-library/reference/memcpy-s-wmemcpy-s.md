---
description: 'Hakkında daha fazla bilgi edinin: memcpy_s wmemcpy_s'
title: memcpy_s, wmemcpy_s
ms.date: 4/2/2020
api_name:
- memcpy_s
- wmemcpy_s
- _o_memcpy_s
- _o_wmemcpy_s
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
- wmemcpy_s
- memcpy_s
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
ms.openlocfilehash: 77c71e594d9a3853438987e85e43700d1f467718
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304758"
---
# <a name="memcpy_s-wmemcpy_s"></a>memcpy_s, wmemcpy_s

Baytları, arabellekler arasında kopyalar. Bunlar, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, wmemcpy ve güvenlik geliştirmeleriyle birlikte [, memckopyala](memcpy-wmemcpy.md) sürümlerindekilerle aynıdır.

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

*HD*<br/>
Yeni arabellek.

*Hedef boyutu*<br/>
Wmemcpy_s için memcpy_s ve geniş karakterler (wchar_t) için bayt cinsinden hedef arabelleğin boyutu.

*src*<br/>
Kopyalanacak arabellek.

*biriktirme*<br/>
Kopyalanacak karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*HD*|*Hedef boyutu*|*src*|*biriktirme*|Döndürülen değer|*Hedef* içeriği|
|------------|----------------|-----------|---|------------------|------------------------|
|herhangi biri|herhangi biri|herhangi biri|0|0|Değiştirilmedi|
|**DEĞER**|herhangi biri|herhangi biri|sıfır olmayan|**EıNVAL**|Değiştirilmedi|
|herhangi biri|herhangi biri|**DEĞER**|sıfır olmayan|**EıNVAL**|*hedef* sıfırlandı|
|herhangi biri|< *biriktirme*|herhangi biri|sıfır olmayan|**ERANGE**|*hedef* sıfırlandı|

## <a name="remarks"></a>Açıklamalar

**memcpy_s** , *src* 'den hedefe kadar olan *sayı* baytlarını *hedef*; **wmemcpy_s** kopya *sayısı* geniş karakter (iki bayt). Kaynak ve hedef çakıştığında **memcpy_s** davranışı tanımsızdır. Çakışan bölgeleri işlemek için **memmove_s** kullanın.

Bu işlevler, parametrelerini doğrular. *Count* değeri sıfır değilse ve *hedef* ya da *src* null işaretçisiyse veya *destsize* *Count* değerinden küçükse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EINVAL** veya **ERANGE** döndürür ve **errno** değerini döndürülen değere ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> veya \<string.h>|
|**wmemcpy_s**|\<wchar.h>|

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

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
