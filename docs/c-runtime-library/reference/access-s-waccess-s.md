---
description: 'Hakkında daha fazla bilgi edinin: _access_s _waccess_s'
title: _access_s, _waccess_s
ms.date: 4/2/2020
api_name:
- _access_s
- _waccess_s
- _o__access_s
- _o__waccess_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- waccess_s
- access_s
- _waccess_s
- _access_s
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
ms.openlocfilehash: cf46f3996005584a8f17b25baac60b9c5683ed19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303849"
---
# <a name="_access_s-_waccess_s"></a>_access_s, _waccess_s

Dosya okuma/yazma izinlerini belirler. Bu, _access bir sürümüdür [ve](access-waccess.md) [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan güvenlik geliştirmeleriyle _waccess.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _access_s(
   const char *path,
   int mode
);
errno_t _waccess_s(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Parametreler

*Yolun*<br/>
Dosya veya dizin yolu.

*modundaysa*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Dosyada verilen mod varsa her işlev 0 döndürür. Adlandırılmış dosya yoksa veya verilen modda erişilebilir değilse işlev bir hata kodu döndürür. Bu durumda, işlev kümeden aşağıdaki gibi bir hata kodu döndürür ve ayrıca `errno` aynı değere ayarlanır.

|errno değeri|Koşul|
|-|-|
`EACCES`|Erişim reddedildi. Dosyanın izin ayarı belirtilen erişime izin vermiyor.
`ENOENT`|Dosya adı veya yolu bulunamadı.
`EINVAL`|Geçersiz parametre.

Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Dosyalarla birlikte kullanıldığında, **_access_s** işlevi belirtilen dosyanın mevcut olup olmadığını ve *mod* değeri tarafından belirtilen şekilde erişilebilir olup olmayacağını belirler. Dizinler ile kullanıldığında, **_access_s** yalnızca belirtilen dizinin mevcut olup olmadığını belirler. Windows 2000 ve sonraki işletim sistemlerinde, tüm dizinlerin okuma ve yazma erişimi vardır.

|mod değeri|İçin dosyayı denetler|
|----------------|---------------------|
|00|Yalnızca varlık.|
|02|Yazma izni.|
|04|Okuma izni.|
|06|Okuma ve yazma izni.|

Dosyayı okuma veya yazma izni, bir dosyayı açabildiğinizden emin olmak için yeterli değil. Örneğin, bir dosya başka bir işlem tarafından kilitlenmişse, **_access_s** 0 döndürdüğünden bile erişilebilir olmayabilir.

**_waccess_s** , **_waccess_s** *yol* bağımsız değişkeninin geniş karakterli bir dize olduğu **_access_s** geniş karakterli bir sürümüdür. Aksi takdirde, **_waccess_s** ve **_access_s** aynı şekilde davranır.

Bu işlevler, parametrelerini doğrular. *Yol* null veya *mod* geçerli bir mod belirtmezse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler öğesini `errno` olarak ayarlar `EINVAL` ve döndürür `EINVAL` .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess_s`|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> veya \<io.h>|\<errno.h>|

## <a name="example"></a>Örnek

Bu örnek, varolup olmadığını ve yazmaya izin verilip verilmeyeceğini görmek için crt_access_s. c adlı dosyayı denetlemek üzere **_access_s** kullanır.

```C
// crt_access_s.c

#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    errno_t err = 0;

    // Check for existence.
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )
    {
        printf_s( "File crt_access_s.c exists.\n" );

        // Check for write permission.
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )
        {
            printf_s( "File crt_access_s.c does have "
                      "write permission.\n" );
        }
        else
        {
            printf_s( "File crt_access_s.c does not have "
                      "write permission.\n" );
        }
    }
    else
    {
        printf_s( "File crt_access_s.c does not exist.\n" );
    }
}
```

```Output
File crt_access_s.c exists.
File crt_access_s.c does not have write permission.
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Işlevleri](stat-functions.md)
