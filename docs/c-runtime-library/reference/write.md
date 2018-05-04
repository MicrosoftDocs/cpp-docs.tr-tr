---
title: _Write | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _write
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
apitype: DLLExport
f1_keywords:
- _write
dev_langs:
- C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f800c42480b6518c7482c15bfa18646b1988dc8a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="write"></a>_write

Verileri bir dosyaya yazar.

## <a name="syntax"></a>Sözdizimi

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Dosya tanımlayıcısı dosyasının içine veriler yazılır.

*Arabellek*<br/>
Yazılacak veriler.

*Sayısı*<br/>
Bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_write** gerçekte yazılan bayt sayısını döndürür. Diskte kalan gerçek alan işlevi diske yazmak için çalışıyor arabellek boyutu küçükse **_write** başarısız olur ve herhangi bir arabellek İçindekiler diske temizleme değil. Dönüş değeri-1 hata gösterir. Geçersiz parametreler aktarılırsa, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevi -1 döndürür ve **errno** üç değerlerden birine ayarlayın: **EBADF**, yani dosya tanımlayıcısı geçersiz veya dosya yazma için; açılmadı **ENOSPC**, cihazda; işlemi için yeterli alan yok. anlamına sol veya **EINVAL**, anlamına *arabellek* null işaretçinin veya, bir tek *sayısı* bayt Unicode modda bir dosyaya yazılacak geçirildi.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dosya metin modunda açılırsa, her bir satır besleme karakteri bir satır başı - çıktıda satır besleme çifti ile değiştirilir. Değiştirme dönüş değeri etkilemez.

Dosya Unicode çeviri modunda açılır olduğunda — Örneğin, varsa *fd* kullanılarak açılmaktadır **_kurulum Aç** veya **_sopen** ve içeren bir mod parametresi **_O_ WTEXT**, **_O_U16TEXT**, veya **_O_U8TEXT**, veya kullanarak açılırsa **fopen** ve içeren bir mod parametresi **ccs = UNICODE**, **ccs UTF-16LE =**, veya **ccs = UTF-8**, veya modunu kullanarak bir Unicode çeviri modu değiştirilirse **_setmode**—*arabellek* bir dizi için bir işaretçi olarak yorumlanır **wchar_t** içeren **UTF-16** veri. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.

## <a name="remarks"></a>Açıklamalar

**_Write** işlev yazma *sayısı* baytlar *arabellek* ilişkili dosyasına *fd*. Dosya işaretçisini (varsa) geçerli konumunu verilen dosyayla ilişkili yazma işlemi başlar. Dosya ekleme için açık olduğunda, dosyanın geçerli sonunda işlemi başlar. Yazma işleminden sonra dosya işaretçisini tarafından gerçekten yazılan bayt sayısı artar.

Dosyalara metin modunda açılmış yazılırken **_write** CTRL + Z karakteri mantıksal son dosya değerlendirir. Bir cihaza yazılırken **_write** bir çıktı Sonlandırıcı olarak arabelleği CTRL + Z karakteri değerlendirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_write**|\<io.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occured
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
