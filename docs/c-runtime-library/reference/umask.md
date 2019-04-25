---
title: _umask
ms.date: 11/04/2016
apiname:
- _umask
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
- _umask
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
ms.openlocfilehash: 113bf97b0fe93204cd41de20bc36a8be080a88b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155426"
---
# <a name="umask"></a>_umask

Varsayılan dosya izni maskesi ayarlar. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [_umask_s](umask-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _umask( int pmode );
```

### <a name="parameters"></a>Parametreler

*pmode*<br/>
Varsayılan izin ayarı.

## <a name="return-value"></a>Dönüş Değeri

**_umask** önceki değerini döndürür *pmode*. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

**_Umask** işlevi geçerli işlemin dosya izni maskesi tarafından belirtilen modu ayarlar *pmode*. Dosya izni maskesi tarafından oluşturulan yeni dosyaları izin ayarını değiştirir **_creat**, **_aç**, veya **_sopen**. Bir bit maskesi 1 ise, karşılık gelen bit dosyanın istenen izin değeri 0 (izin verilmeyen) olarak ayarlanır. Bir bit maskesi 0 ise, karşılık gelen bit bırakılır değişmez. Dosya ilk kez kapatılana kadar yeni bir dosya için izin ayarının ayarlanmadı.

Tamsayı ifadesini *pmode* birini veya her ikisini SYS\STAT tanımlanan aşağıdaki bildirim sabitleri içerir. Y:

|*pmode*| |
|-|-|
| **_S_IWRITE** | Yazma izin verilir. |
| **_S_IREAD** | Okuma izin verilir. |
| **_S_IREAD** &#124; **_S_IWRITE** | Okuma ve yazma izin verilir. |

Her iki sabitleri verildiğinde, bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ). Varsa *pmode* bağımsız değişkeni **_s_ıread**, okuma izin verilmiyor (dosyayı salt yazılır). Varsa *pmode* bağımsız değişkeni **_s_ıwrıte**, yazma izin verilmiyor (dosya salt okunur). Örneğin, yazma bit maskesi ayarlarsanız, tüm yeni dosyalar salt okunur olacaktır. MS-DOS ile Windows işletim sistemleri, tüm dosyaları okunabilir olduğunu unutmayın; Salt yazma izni vermek mümkün değildir. Bu nedenle, salt okunur bit ile ayarlama **_umask** dosyanın modları üzerinde hiçbir etkisi olmaz.

Varsa *pmode* bildirim sabitlerinden birini birleşimi değil veya alternatif bir kümesini içerir, sabitleri işlevi yalnızca bu göz ardı eder.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_umask**|\<io.h >, \<sys/stat.h >, \<sys/types.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
