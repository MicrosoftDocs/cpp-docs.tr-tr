---
description: 'Daha fazla bilgi edinin: yeniden adlandırma, _wrename'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 2a68bff031f321a2566c0da99aacc053ba475928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322504"
---
# <a name="rename-_wrename"></a>yeniden adlandır, _wrename

Bir dosyayı veya dizini yeniden adlandırın.

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

*OldName*<br/>
Eski ad işaretçisi.

*ad*<br/>
Yeni ad işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri başarılı olursa 0 döndürür. Bir hatada, işlev sıfır dışında bir değer döndürür ve **errno** değerini aşağıdaki değerlerden birine ayarlar:

|errno değeri|Koşul|
|-|-|
| **EACCES** | *Newname* tarafından belirtilen dosya veya dizin zaten var veya oluşturulamıyor (geçersiz yol); veya *OldName* bir dizindir ve *YeniAd* farklı bir yol belirtir. |
| **ENOENT** | *OldName* tarafından belirtilen dosya veya yol bulunamadı. |
| **EıNVAL** | Ad geçersiz karakterler içeriyor. |

Olası diğer dönüş değerleri için bkz. [_doserrno, _errno, syserrlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Rename işlevi, *OldName* tarafından belirtilen dosya veya dizini *YeniAd* tarafından verilen ada **yeniden** adlandırır. Eski ad, varolan bir dosyanın veya dizinin yolu olmalıdır. Yeni ad var olan bir dosyanın veya dizinin adı olmamalıdır. *Newname* bağımsız değişkeninde farklı bir yol vererek bir dosyayı bir dizinden veya cihazdan diğerine taşımak için **Yeniden Adlandır** ' a kullanabilirsiniz. Ancak, bir dizini taşımak için **yeniden adlandırma** kullanamazsınız. Dizinler yeniden adlandırılabilir, ancak taşınamaz.

**_wrename** , **_rename** geniş karakterli bir sürümüdür; **_wrename** bağımsız değişkenler geniş karakterli dizelerdir. **_wrename** ve **_rename** aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**Yeniden Adlandır**|**Yeniden Adlandır**|**_wrename**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Yeniden Adlandır**|\<io.h> veya \<stdio.h>|
|**_wrename**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
