---
title: _access_s, _waccess_s
ms.date: 11/04/2016
apiname:
- _access_s
- _waccess_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 17d19527323f3e97edecd22ca7c0a0262b1cfbad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541524"
---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s

Dosya okuma/yazma izinleri belirler. Bu bir sürümüdür [_erişim, _waccess](access-waccess.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

Dosyada belirtilen modu varsa her işlev 0 değerini döndürür. Adlandırılmış dosya yok veya verilen modunda erişilebilir değilse işlev bir hata kodu döndürür. Bu durumda, işlev kümesinden gibi bir hata kodu döndürür ve ayrıca ayarlar `errno` aynı değere.

|errno değeri|Koşul|
|-|-|
`EACCES`|Erişim reddedildi. Dosya izin ayarının belirtilen erişim izin vermez.
`ENOENT`|Dosya adı veya yolu bulunamadı.
`EINVAL`|Geçersiz parametre.

Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Dosyaları ile kullanıldığında **_access_s** işlevi, belirtilen dosyanın varolduğundan ve olarak erişilebilir olup olmadığını belirleyen değeri tarafından belirtilen *modu*. Dizinler ile kullanıldığında **_access_s** yalnızca belirtilen dizinin var olup olmadığını belirler. Windows 2000 ve sonraki işletim sistemleri, tüm dizinleri okuma ve yazma erişimi.

|mod değeri|Dosya için denetimleri|
|----------------|---------------------|
|00|Yalnızca varlığı.|
|02|Yazma izni.|
|04|Okuma izni.|
|06|Okuma ve yazma izni.|

Okuma veya dosyanın yazma izni bir dosyayı açma olanağı sağlamak yeterli değil. Bir dosyayı başka bir işlem tarafından kilitlenmişse, örneğin, bu olsa bile erişilebilir olmayabilir **_access_s** 0 döndürür.

**_waccess_s** geniş karakterli sürümüdür **_access_s**burada *yolu* bağımsız değişkeni **_waccess_s** geniş karakterli bir dizedir. Aksi takdirde, **_waccess_s** ve **_access_s** aynı şekilde davranır.

Bu işlevler kendi parametrelerini doğrular. Varsa *yolu* null veya *modu* geçerli bir moda belirtmiyor açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi `errno` için `EINVAL` ve dönüş `EINVAL`.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess_s`|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h >|\<errno.h >|
|**_waccess_s**|\<wchar.h > veya \<io.h >|\<errno.h >|

## <a name="example"></a>Örnek

Bu örnekte **_access_s** var olup ve yazma izin verilip verilmeyeceğini görmek için crt_access_s.c adlı dosyayı denetlemek için.

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
[_stat, _wstat işlevleri](stat-functions.md)