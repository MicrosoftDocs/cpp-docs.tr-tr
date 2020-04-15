---
title: _umask
ms.date: 4/2/2020
api_name:
- _umask
- _o__umask
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
- _umask
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
ms.openlocfilehash: b451f979f2925a31f5baaac52351c5d2c0a76da0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362017"
---
# <a name="_umask"></a>_umask

Varsayılan dosya izni maskesini ayarlar. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. _umask_s.](umask-s.md)

## <a name="syntax"></a>Sözdizimi

```C
int _umask( int pmode );
```

### <a name="parameters"></a>Parametreler

*pmode*<br/>
Varsayılan izin ayarı.

## <a name="return-value"></a>Dönüş Değeri

**_umask** *pmode*önceki değerini döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

**_umask** işlevi, geçerli işlemin dosya izin maskesini *pmode*tarafından belirtilen moda ayarlar. Dosya izin maskesi, **_creat**, **_open**veya **_sopen**tarafından oluşturulan yeni dosyaların izin ayarını değiştirir. Maskedeki bir bit 1 ise, dosyanın istenen izin değerindeki karşılık gelen bit 0 (izin verilmez) olarak ayarlanır. Maskedeki bir bit 0 ise, karşılık gelen bit değişmeden bırakılır. Yeni bir dosyaiçin izin ayarı, dosya ilk kez kapatılana kadar ayarlanmaz.

İnteger ifade *pmode* sys\STAT tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini içerir. H:

|*pmode*| |
|-|-|
| **_S_IWRITE** | Yazmaya izin verilir. |
| **_S_IREAD** | Okumaya izin verilir. |
| **_S_IREAD** &#124; **_S_IWRITE** | Okuma ve yazmaya izin verilir. |

Her iki sabit de verildiğinde, bitwise-OR işleci **(&#124;)** ile birleştirilir. *Pmode* bağımsız **değişkeni _S_IREAD**ise, okumaya izin verilmez (dosya yalnızca yazmadır). *Pmode* bağımsız **değişkeni _S_IWRITE**ise, yazmaya izin verilmez (dosya salt okunur). Örneğin, yazma biti maskede ayarlanmışsa, yeni dosyalar salt okunur. MS-DOS ve Windows işletim sistemleri ile tüm dosyaların okunabilir olduğunu unutmayın; yalnızca yazma izni vermek mümkün değildir. Bu nedenle, okuma bitini **_umask** ayarlamak dosyanın modları üzerinde hiçbir etkiye sahip değildir.

*Pmode,* bildirim sabitlerinden birinin bir birleşimi değilse veya alternatif bir sabit kümesi içeriyorsa, işlev bunları yok sayacaktır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_umask**|\<io.h>, \<sys/stat.h \<>, sys/types.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_umask.c
// compile with: /W3
// This program uses _umask to set
// the file-permission mask so that all future
// files will be created as read-only files.
// It also displays the old mask.
#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask;

   /* Create read-only files: */
   oldmask = _umask( _S_IWRITE ); // C4996
   // Note: _umask is deprecated; consider using _umask_s instead
   printf( "Oldmask = 0x%.4x\n", oldmask );
}
```

```Output
Oldmask = 0x0000
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
