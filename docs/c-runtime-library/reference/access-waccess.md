---
description: 'Hakkında daha fazla bilgi edinin: _access _waccess'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: d8cb62050482f29be0bef2b8433a65c2730de2fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303745"
---
# <a name="_access-_waccess"></a>_access, _waccess

Bir dosyanın salt okunurdur olup olmadığını belirler. Daha güvenli sürümler kullanılabilir; bkz. [_access_s, _waccess_s](access-s-waccess-s.md).

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

*Yolun*<br/>
Dosya veya dizin yolu.

*modundaysa*<br/>
Okuma/yazma özniteliği.

## <a name="return-value"></a>Dönüş Değeri

Dosyada verilen mod varsa her işlev 0 döndürür. Adlandırılmış dosya yoksa veya verilen moda sahip değilse, işlev-1 değerini döndürür; Bu durumda, `errno` Aşağıdaki tabloda gösterildiği gibi ayarlanır.

| Değer | Açıklama |
|--|--|
| `EACCES` | Erişim reddedildi: dosyanın izin ayarı belirtilen erişime izin vermiyor. |
| `ENOENT` | Dosya adı veya yolu bulunamadı. |
| `EINVAL` | Geçersiz parametre. |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Dosyalarla birlikte kullanıldığında, **_access** işlevi, belirtilen dosya veya dizinin var olduğunu ve *mod* değeri tarafından belirtilen özniteliklere sahip olup olmadığını belirler. Dizinler ile kullanıldığında **_access** yalnızca belirtilen dizinin mevcut olup olmadığını belirler; Windows 2000 ve sonraki işletim sistemlerinde, tüm dizinlerin okuma ve yazma erişimi vardır.

|*mod* değeri|İçin dosyayı denetler|
|------------------|---------------------|
|00|Yalnızca varlık|
|02|Salt yazılır|
|04|Salt okunur|
|06|Okuma ve yazma|

Bu işlev yalnızca dosya ve dizinin salt okunurdur olup olmadığını denetler, dosya sistemi güvenlik ayarlarını denetlemez. İçin bir erişim belirtecine ihtiyacınız vardır. Dosya sistemi güvenliği hakkında daha fazla bilgi için bkz. [erişim belirteçleri](/windows/win32/SecAuthZ/access-tokens). Bu işlevi sağlamak için ATL sınıfı vardır; bkz. [CAccessToken sınıfı](../../atl/reference/caccesstoken-class.md).

**_waccess** , **_access** geniş karakterli bir sürümüdür; _waccess *yol* bağımsız değişkeni  , geniş karakterli bir dizedir. **_waccess** ve **_access** aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. *Yol* null veya *mod* geçerli bir mod belirtmezse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa işlev öğesini `errno` olarak ayarlar `EINVAL` ve-1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess`|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> veya \<io.h>|\<errno.h>|

## <a name="example"></a>Örnek

Aşağıdaki örnek, crt_ACCESS adlı dosyayı denetlemek için **_access** kullanır. C, varolup olmadığını ve yazma izni verilip verilmediğini görmek için.

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Işlevleri](stat-functions.md)
