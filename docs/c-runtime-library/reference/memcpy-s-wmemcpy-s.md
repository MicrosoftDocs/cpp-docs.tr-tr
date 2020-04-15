---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: dc5e49115b65b6883e55df13d0610231a87c1c55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333334"
---
# <a name="memcpy_s-wmemcpy_s"></a>memcpy_s, wmemcpy_s

Arabellekler arasındaki baytkopyaları. Bunlar [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [memcpy, wmemcpy](memcpy-wmemcpy.md) sürümleridir.

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

*Dest*<br/>
Yeni arabellek.

*destSize*<br/>
Hedef arabelleğin boyutu, memcpy_s için baytlar ve wmemcpy_s için geniş karakterler (wchar_t).

*src*<br/>
Kopyalanması gereken arabellek.

*Sayısı*<br/>
Kopyalanması gereken karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*Dest*|*destSize*|*src*|*Sayısı*|Döndürülen değer|*Dest'in* içindekiler|
|------------|----------------|-----------|---|------------------|------------------------|
|herhangi bir|herhangi bir|herhangi bir|0|0|Değiştirilmedi|
|**Null**|herhangi bir|herhangi bir|sıfır olmayan|**Eınval**|Değiştirilmedi|
|herhangi bir|herhangi bir|**Null**|sıfır olmayan|**Eınval**|*dest* sıfırlanır|
|herhangi bir|< *Sayısı*|herhangi bir|sıfır olmayan|**Erange**|*dest* sıfırlanır|

## <a name="remarks"></a>Açıklamalar

**memcpy_s** kopyaları *src* den *dest*bayt *sayılır;* **wmemcpy_s** kopyaları geniş karakterleri (iki bayt) *sayar.* Kaynak ve hedef çakışıyorsa, **memcpy_s** davranışı tanımsızdır. Çakışan bölgeleri işlemek için **memmove_s** kullanın.

Bu işlevler parametrelerini doğrular. *Sayım* sıfır olmayan ve *dest* veya *src* bir null işaretçiise veya *destSize* *sayımdan*daha küçükse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** veya **ERANGE** döndürecek ve **errno'yu** döndürecek değere ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> \<veya string.h>|
|**wmemcpy_s**|\<wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Arabellek Manipülasyonu](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
