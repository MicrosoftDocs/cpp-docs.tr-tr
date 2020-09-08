---
title: _umask
description: _Umask için API başvurusu; Varsayılan dosya izni maskesini ayarlar.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 3735ecd7ba194009945d3717982d7828ecee3c1e
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554935"
---
# <a name="_umask"></a>_umask

Varsayılan dosya izni maskesini ayarlar. Bu işlevin daha güvenli bir sürümü için bkz. [_umask_s](umask-s.md) . "

## <a name="syntax"></a>Söz dizimi

```C
int _umask( int pmode );
```

### <a name="parameters"></a>Parametreler

*pmode*<br/>
Varsayılan izin ayarı.

## <a name="return-value"></a>Dönüş Değeri

**_umask** , *pmode*'ın önceki değerini döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**_Umask** işlevi, geçerli işlemin dosya izni maskesini *pmode*tarafından belirtilen moda ayarlar. Dosya izni maskesi, **_creat**, **_open**veya **_sopen**tarafından oluşturulan yeni dosyaların izin ayarını değiştirir. Maskede bir bit 1 ise, dosyanın istenen izin değerindeki karşılık gelen bit 0 olarak ayarlanır (izin verilmez). Maskede bir bit 0 ise, karşılık gelen bit değişmeden bırakılır. Yeni bir dosyanın izin ayarı, dosya ilk kez kapatılana kadar ayarlanamaz.

*Pmode* tamsayı ifadesi, sys\statiçinde tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini içerir. Olsun

|*pmode*| |
|-|-|
| **_S_IWRITE** | Yazma izni veriliyor. |
| **_S_IREAD** | Okuma izni verildi. |
| **_S_IREAD** &#124; **_S_IWRITE** | Okuma ve yazma izni verildi. |

Her iki sabit de verildiğinde, bit düzeyinde OR işleci ( **&#124;** ) ile birleştirilir. *Pmode* bağımsız değişkeni **_S_IREAD**, okumaya izin verilmez (dosya salt yazılır olur). *Pmode* bağımsız değişkeni **_S_IWRITE**, yazmaya izin verilmez (dosya salt okunurdur). Örneğin, maskede yazma biti ayarlandıysa, tüm yeni dosyalar salt okunurdur. MS-DOS ve Windows işletim sistemlerinde tüm dosyaların okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, okuma bitinin **_umask** olarak ayarlanması, dosyanın modlarında hiçbir etkiye sahip değildir.

*Pmode* , bildirim sabitlerinden birinin bir birleşimi değilse veya diğer bir sabitler kümesini içeriyorsa, işlev bunları yok sayacaktır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_umask**|\<io.h>, \<sys/stat.h>, \<sys/types.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
