---
title: _umask_s
ms.date: 11/04/2016
api_name:
- _umask_s
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
ms.openlocfilehash: 21d9ba194f85e40c3c5a4d67d16ebca9721f68f8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945992"
---
# <a name="_umask_s"></a>_umask_s

Varsayılan dosya izni maskesini ayarlar. [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_umask](umask.md) sürümü.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _umask_s(
   int mode,
   int * pOldMode
);
```

### <a name="parameters"></a>Parametreler

*modundaysa*<br/>
Varsayılan izin ayarı.

*pOldMode*<br/>
İzin ayarının önceki değeri.

## <a name="return-value"></a>Dönüş Değeri

*Mod* geçerli bir mod belirtmezse veya *pOldMode* işaretçisi **null**olduğunda bir hata kodu döndürür.

### <a name="error-conditions"></a>Hata koşulları

|*modundaysa*|*pOldMode*|Dönüş değeri|*POldMode* içeriği|
|------------|----------------|----------------------|--------------------------------|
|Kaydedilmemiş|**DEĞER**|**EINVAL**|değiştirilmedi|
|Geçersiz mod|Kaydedilmemiş|**EINVAL**|değiştirilmedi|

Yukarıdaki koşullardan biri gerçekleşirse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **_Umask_s** **EINVAL** döndürür ve **errno** öğesini **EINVAL**olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**_Umask_s** işlevi, geçerli işlemin dosya izni maskesini *mod*tarafından belirtilen moda ayarlar. Dosya izni maskesi, **_creat**, **_open**veya **_sopen**tarafından oluşturulan yeni dosyaların izin ayarını değiştirir. Maskede bir bit 1 ise, dosyanın istenen izin değerindeki karşılık gelen bit 0 olarak ayarlanır (izin verilmez). Maskede bir bit 0 ise, karşılık gelen bit değişmeden bırakılır. Yeni bir dosyanın izin ayarı, dosya ilk kez kapatılana kadar ayarlanamaz.

*Pmode* tamsayı ifadesi, sys\statiçinde tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini içerir. Olsun

|*pmode*||
|-|-|
|**_S_IWRITE**|Yazma izni veriliyor.|
|**_S_IREAD**|Okuma izni verildi.|
|**_S_İREAD** \| **_S_İWRİTE**|Okuma ve yazma izni verildi.|

Her iki sabit de verildiğinde, bit düzeyinde OR işleci ( **|** ) ile birleştirilir. *Mode* bağımsız değişkeni **_S_iread**ise, okumaya izin verilmez (dosya salt yazılır olur). *Mode* bağımsız değişkeni **_S_iwrite**ise, yazmaya izin verilmez (dosya salt okunurdur). Örneğin, maskede yazma biti ayarlandıysa, tüm yeni dosyalar salt okunurdur. MS-DOS ve Windows işletim sistemlerinde tüm dosyaların okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, okuma bitinin **_umask_s** ile ayarlanması, dosyanın modlarını etkilemez.

*Pmode* , bildirim sabitlerinden birinin bir birleşimi değilse veya diğer bir sabitler kümesini içeriyorsa, işlev bunları yok sayacaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_umask_s**|\<GÇ. h > ve \<sys/stat. h > ve \<sys/Types. h >|

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
[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>
