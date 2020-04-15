---
title: yeniden adlandır, _wrename
ms.date: 4/2/2020
api_name:
- rename
- _wrename
- _o__wrename
- _o_rename
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
- _wrename
- _trename
- Rename
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
ms.openlocfilehash: 730458c5027f8f690e8238b29cbdb1056f09ed68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338113"
---
# <a name="rename-_wrename"></a>yeniden adlandır, _wrename

Dosyayı veya dizini yeniden adlandırın.

## <a name="syntax"></a>Sözdizimi

```C
int rename(
   const char *oldname,
   const char *newname
);
int _wrename(
   const wchar_t *oldname,
   const wchar_t *newname
);
```

### <a name="parameters"></a>Parametreler

*oldname*<br/>
Eski isme işaretçi.

*Yeniad*<br/>
Yeni ad için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri 0 döndürür. Bir hatada, işlev sıfır olmayan bir değer döndürür ve aşağıdaki değerlerden birine **errno** ayarlar:

|errno değeri|Koşul|
|-|-|
| **EACCES** | *Yeni adla* belirtilen dosya veya dizin zaten var veya oluşturulamadı (geçersiz yol); veya *oldname* bir dizin ve *yeni ad* farklı bir yol belirtir. |
| **Enoent** | *Eski adla* belirtilen dosya veya yol bulunamadı. |
| **Eınval** | Ad geçersiz karakterler içerir. |

Diğer olası iade değerleri için [_doserrno, _errno, syserrlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Yeniden adlandırma** işlevi, *eski adla* belirtilen dosyayı veya dizini *yeni adla*verilen ada yeniden adlandırır. Eski ad, varolan bir dosyanın veya dizinin yolu olmalıdır. Yeni ad, varolan bir dosyanın veya dizinin adı olmamalıdır. *Yeni ad* bağımsız değişkeninde farklı bir yol vererek bir dosyayı bir dizin veya aygıttan diğerine taşımak için **yeniden adlandırmayı** kullanabilirsiniz. Ancak, bir dizini taşımak için **yeniden adlandırmak** kullanamazsınız. Dizinler yeniden adlandırılabilir, ancak taşınamaz.

**_wrename** **_rename**geniş karakterli bir versiyonudur; **_wrename** bağımsız değişkenleri geniş karakterli dizeleridir. **_wrename** ve **_rename** aynı şekilde aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**Yeni -den adlandırmak**|**Yeni -den adlandırmak**|**_wrename**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Yeni -den adlandırmak**|\<io.h> \<veya stdio.h>|
|**_wrename**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_renamer.c
/* This program attempts to rename a file named
* CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation
* to succeed, a file named CRT_RENAMER.OBJ must exist and
* a file named CRT_RENAMER.JBO must not exist.
*/

#include <stdio.h>

int main( void )
{
   int  result;
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";

   /* Attempt to rename file: */
   result = rename( old, new );
   if( result != 0 )
      printf( "Could not rename '%s'\n", old );
   else
      printf( "File '%s' renamed to '%s'\n", old, new );
}
```

### <a name="output"></a>Çıktı

```Output
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
