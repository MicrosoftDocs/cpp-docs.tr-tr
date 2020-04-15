---
title: _access, _waccess
ms.date: 4/2/2020
api_name:
- _access
- _waccess
- _o__access
- _o__waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
ms.openlocfilehash: 98726726e14aacec75ed99adfa33016b40affd17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350868"
---
# <a name="_access-_waccess"></a>_access, _waccess

Bir dosyanın salt okunur olup olmadığını belirler. Daha güvenli sürümler mevcuttur; [bkz _access_s, _waccess_s](access-s-waccess-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _access(
   const char *path,
   int mode
);
int _waccess(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Parametreler

*Yolu*<br/>
Dosya veya dizin yolu.

*Modu*<br/>
Öznitelik okuma/yazma.

## <a name="return-value"></a>Dönüş Değeri

Dosyaverilen modu varsa her işlev 0 döndürür. Adlandırılmış dosya yoksa veya verilen modu yoksa işlev -1 döndürür; bu durumda, `errno` aşağıdaki tabloda gösterildiği gibi ayarlanır.

|||
|-|-|
`EACCES`|Erişim reddedildi: dosyanın izin ayarı belirtilen erişime izin vermez.
`ENOENT`|Dosya adı veya yol bulunamadı.
`EINVAL`|Geçersiz parametre.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

Dosyalarla birlikte kullanıldığında, **_access** işlevi belirtilen dosya veya dizin var olup olmadığını belirler ve *mod*değeri tarafından belirtilen özniteliklere sahiptir. Dizinlerle kullanıldığında, **_access** yalnızca belirtilen dizinin var olup olmadığını belirler; Windows 2000 ve daha sonraki işletim sistemlerinde, tüm dizinler okuma ve yazma erişimine sahiptir.

|*mod* değeri|Dosyayı denetler|
|------------------|---------------------|
|00|Yalnızca varoluş|
|02|Yalnızca yazma|
|04|Salt okunur|
|06|Okuma ve yazma|

Bu işlev yalnızca dosya nın ve dizinin salt okunur olup olmadığını denetler, dosya sistemi güvenlik ayarlarını denetlemez. Bunun için bir erişim belirteci gerekir. Dosya sistemi güvenliği hakkında daha fazla bilgi için [Erişim Belirteçleri'ne](/windows/win32/SecAuthZ/access-tokens)bakın. Bu işlevselliği sağlamak için bir ATL sınıfı vardır; [bkz: CAccessToken Sınıfı.](../../atl/reference/caccesstoken-class.md)

**_waccess** **_access**geniş karakterli bir versiyonudur; **_waccess** *yol* bağımsız değişkeni geniş karakterli bir dizedir. **_waccess** ve **_access** aynı şekilde davranan.

Bu işlev parametrelerini doğrular. *Yol* NULL ise veya *mod* geçerli bir mod belirtmiyorsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin verilirse, işlev -1'e `errno` `EINVAL` ayarlar ve döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess`|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> \<veya io.h>|\<errno.h>|

## <a name="example"></a>Örnek

Aşağıdaki örnekte crt_ACCESS adlı dosyayı denetlemek için **_access** kullanır. C var olup olmadığını ve yazmaya izin verilip verilmediğini görmek için.

```C
// crt_access.c
// compile with: /W1
// This example uses _access to check the file named
// crt_ACCESS.C to see if it exists and if writing is allowed.

#include  <io.h>
#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    // Check for existence.
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )
    {
        printf_s( "File crt_ACCESS.C exists.\n" );

        // Check for write permission.
        // Assume file is read-only.
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );
    }
}
```

```Output
File crt_ACCESS.C exists.
File crt_ACCESS.C does not have write permission.
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Fonksiyonlar](stat-functions.md)
