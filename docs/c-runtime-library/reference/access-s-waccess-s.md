---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 7f16951b99eb29bcb8c39499c29be1018cb86616
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349132"
---
# <a name="_access_s-_waccess_s"></a>_access_s, _waccess_s

Dosya okuma/yazma izinlerini belirler. Bu, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleriyle [_waccess _access](access-waccess.md) bir sürümüdür.

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

*Yolu*<br/>
Dosya veya dizin yolu.

*Modu*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Dosyaverilen modu varsa her işlev 0 döndürür. Adlandırılmış dosya yoksa veya verilen modda erişilemezse işlev bir hata kodu döndürür. Bu durumda, işlev aşağıdaki gibi kümeden bir hata `errno` kodu döndürür ve aynı değere ayarlar.

|errno değeri|Koşul|
|-|-|
`EACCES`|Erişim reddedildi. Dosyanın izin ayarı belirtilen erişime izin vermez.
`ENOENT`|Dosya adı veya yol bulunamadı.
`EINVAL`|Geçersiz parametre.

Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Açıklamalar

Dosyalarla birlikte kullanıldığında, **_access_s** işlevi belirtilen dosyanın var olup olmadığını belirler ve *mod*değeri tarafından belirtildiği gibi erişilebilir. Dizinlerle kullanıldığında, **_access_s** yalnızca belirtilen dizinin var olup olmadığını belirler. Windows 2000 ve daha sonraki işletim sistemlerinde, tüm dizinler okuma ve yazma erişimine sahiptir.

|mod değeri|Dosyayı denetler|
|----------------|---------------------|
|00|Sadece varoluş.|
|02|İzin yaz.|
|04|İzin okuyun.|
|06|İzin okuma ve yazma.|

Dosyayı okuma veya yazma izni, dosyayı açma özelliğini sağlamak için yeterli değildir. Örneğin, bir dosya başka bir işlem tarafından kilitlenmişse, **_access_s** 0 döndürse bile dosyaya erişilemeyebilir.

**_waccess_s,** **_waccess_s** *yol* bağımsız değişkeninin geniş karakterli bir dize olduğu **_access_s**geniş karakterli bir sürümüdür. Aksi takdirde, **_waccess_s** ve **_access_s** aynı şekilde çalışır.

Bu işlevler parametrelerini doğrular. *Yol* NULL ise veya *mod* geçerli bir mod belirtmiyorsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmedevam etmesine izin verilirse, `errno` `EINVAL` bu `EINVAL`işlevler ayarlanır ve döndürün.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess_s`|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> \<veya io.h>|\<errno.h>|

## <a name="example"></a>Örnek

Bu örnekte, crt_access_s.c adlı dosyanın var olup olmadığını ve yazmaya izin verilip verilmediğini görmek için **_access_s** kullanır.

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Fonksiyonlar](stat-functions.md)
