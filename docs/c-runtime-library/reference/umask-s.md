---
title: _umask_s
ms.date: 4/2/2020
api_name:
- _umask_s
- _o__umask_s
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
- unmask_s
- _umask_s
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
ms.openlocfilehash: d590910d5f5092a78ad64c8f9ef0aa259211e226
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362175"
---
# <a name="_umask_s"></a>_umask_s

Varsayılan dosya izni maskesini ayarlar. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [_umask](umask.md) bir sürümü.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _umask_s(
   int mode,
   int * pOldMode
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Varsayılan izin ayarı.

*pOldMode*<br/>
İzin ayarının önceki değeri.

## <a name="return-value"></a>Dönüş Değeri

*Mod* geçerli bir mod belirtmezse veya *pOldMode* işaretçisi **NULL**ise bir hata kodu verir.

### <a name="error-conditions"></a>Hata Koşulları

|*Modu*|*pOldMode*|Döndürülen değer|*pOldMode* içeriği|
|------------|----------------|----------------------|--------------------------------|
|herhangi bir|**Null**|**Eınval**|değiştirilmemiş|
|geçersiz mod|herhangi bir|**Eınval**|değiştirilmemiş|

Yukarıdaki koşullardan biri oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **_umask_s** **EINVAL** döndürür ve **EINVAL** **için errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**_umask_s** işlevi, geçerli işlemin dosya izin maskesini *modtarafından*belirtilen moda ayarlar. Dosya izin maskesi, **_creat**, **_open**veya **_sopen**tarafından oluşturulan yeni dosyaların izin ayarını değiştirir. Maskedeki bir bit 1 ise, dosyanın istenen izin değerindeki karşılık gelen bit 0 (izin verilmez) olarak ayarlanır. Maskedeki bir bit 0 ise, karşılık gelen bit değişmeden bırakılır. Yeni bir dosyaiçin izin ayarı, dosya ilk kez kapatılana kadar ayarlanmaz.

İnteger ifade *pmode* sys\STAT tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini içerir. H:

|*pmode*||
|-|-|
|**_S_IWRITE**|Yazmaya izin verilir.|
|**_S_IREAD**|Okumaya izin verilir.|
|**_S_IREAD** \| **_S_IWRITE**|Okuma ve yazmaya izin verilir.|

Her iki sabit verildiğinde, bitwise-OR işleci ( **|** ) ile birleştirilir. *Mod* bağımsız değişkeni **_S_IREAD**ise, okumaya izin verilmez (dosya yalnızca yazmadır). *Mod* bağımsız değişkeni **_S_IWRITE**ise, yazmaya izin verilmez (dosya salt okunur). Örneğin, yazma biti maskede ayarlanmışsa, yeni dosyalar salt okunur. MS-DOS ve Windows işletim sistemleri ile tüm dosyaların okunabilir olduğunu unutmayın; yalnızca yazma izni vermek mümkün değildir. Bu nedenle, okuma bitini **_umask_s** ayarlamak dosyanın modları üzerinde hiçbir etkiye sahip değildir.

*Pmode,* bildirim sabitlerinden birinin bir birleşimi değilse veya alternatif bir sabit kümesi içeriyorsa, işlev bunları yok sayacaktır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_umask_s**|\<io.h> \<ve sys/stat.h> ve \<sys/types.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_umask_s.c
/* This program uses _umask_s to set
* the file-permission mask so that all future
* files will be created as read-only files.
* It also displays the old mask.
*/

#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask, err;

   /* Create read-only files: */
   err = _umask_s( _S_IWRITE, &oldmask );
   if (err)
   {
      printf("Error setting the umask.\n");
      exit(1);
   }
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
[_umask](umask.md)<br/>
