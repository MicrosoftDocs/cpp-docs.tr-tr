---
title: _umask_s
ms.date: 11/04/2016
apiname:
- _umask_s
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
ms.openlocfilehash: 878a22cb2884c36e792ff8dead1453582addb5b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480677"
---
# <a name="umasks"></a>_umask_s

Varsayılan dosya izni maskesi ayarlar. Bir sürümünü [_umask](umask.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Önceki izin ayarının değeri.

## <a name="return-value"></a>Dönüş Değeri

Bir hata kodu döndürür *modu* geçerli bir mod belirtmiyor veya *pOldMode* işaretçisi **NULL**.

### <a name="error-conditions"></a>Hata koşulları

|*Modu*|*pOldMode*|Dönüş değeri|İçeriğini *pOldMode*|
|------------|----------------|----------------------|--------------------------------|
|Tüm|**NULL**|**EINVAL**|değiştirilmedi|
|Geçersiz mod|Tüm|**EINVAL**|değiştirilmedi|

Yukarıdaki koşullar meydana gelirse, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **_umask_s** döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Umask_s** işlevi geçerli işlemin dosya izni maskesi tarafından belirtilen modu ayarlar *modu*. Dosya izni maskesi tarafından oluşturulan yeni dosyaları izin ayarını değiştirir **_creat**, **_aç**, veya **_sopen**. Bir bit maskesi 1 ise, karşılık gelen bit dosyanın istenen izin değeri 0 (izin verilmeyen) olarak ayarlanır. Bir bit maskesi 0 ise, karşılık gelen bit bırakılır değişmez. Dosya ilk kez kapatılana kadar yeni bir dosya için izin ayarının ayarlanmadı.

Tamsayı ifadesini *pmode* birini veya her ikisini SYS\STAT tanımlanan aşağıdaki bildirim sabitleri içerir. Y:

|*pmode*||
|-|-|
|**_S_IWRITE**|Yazma izin verilir.|
|**_S_IREAD**|Okuma izin verilir.|
|**_S_IREAD** \| **_S_IWRITE**|Okuma ve yazma izin verilir.|

Her iki sabitleri verildiğinde, bit düzeyinde OR işleci ile birleştirilir ( **|** ). Varsa *modu* bağımsız değişkeni **_s_ıread**, okuma izin verilmiyor (dosyayı salt yazılır). Varsa *modu* bağımsız değişkeni **_s_ıwrıte**, yazma izin verilmiyor (dosya salt okunur). Örneğin, yazma bit maskesi ayarlarsanız, tüm yeni dosyalar salt okunur olacaktır. MS-DOS ile Windows işletim sistemleri, tüm dosyaları okunabilir olduğunu unutmayın; Salt yazma izni vermek mümkün değildir. Bu nedenle, salt okunur bit ile ayarlama **_umask_s** dosyanın modları üzerinde hiçbir etkisi olmaz.

Varsa *pmode* bildirim sabitlerinden birini birleşimi değil veya alternatif bir kümesini içerir, sabitleri işlevi yalnızca bu göz ardı eder.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_umask_s**|\<io.h > ve \<sys/stat.h > ve \<sys/types.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>
