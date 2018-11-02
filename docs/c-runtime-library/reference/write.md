---
title: _write
ms.date: 11/04/2016
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: b3fa53b21d4ea23c5f8e59de673f4074deedb505
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519255"
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
Verilerin üzerine yazılacağını dosyasının dosya tanımlayıcısı.

*Arabellek*<br/>
Yazılacak veriler.

*Sayısı*<br/>
Bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_write** gerçekte yazılan bayt sayısını döndürür. Diskte kalan gerçek alan işlev diske yazmak için çalışıyor arabellek boyutu altındaysa **_write** başarısız olur ve herhangi bir arabellek içeriği diske temizleme değil. -1 dönüş değeri bir hata olduğunu gösterir. Geçersiz parametreler, bu işlev geçersiz parametre işleyicisi açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse işlev -1 döndürür ve **errno** üç değerlerden birine ayarlanır: **EBADF**, yani dosya tanımlayıcısı geçersiz veya dosya; yazma için açılmadı **ENOSPC**, operation;'için cihazda yeterli alan yok anlamına gelen sol veya **EINVAL**, anlamına *arabellek* null bir işaretçi ya da, bir tek *sayısı* bayt Unicode modunda bir dosyaya yazılacak geçirildi.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dosyayı metin modunda açıldıysa, her bir satır besleme karakteri bir satır başı - Çıkışta satır besleme çifti ile değiştirilir. Bu değişiklik, dönüş değeri etkilemez.

Dosya Unicode çeviri modunda açılır olduğunda — Örneğin, varsa *fd* kullanılarak açılmaktadır **_aç** veya **_sopen** ve içeren bir mode parametresi **_O_ WTEXT**, **_O_U16TEXT**, veya **_O_U8TEXT**, ya da kullanarak açıldığında **fopen** ve içeren bir mode parametresi **ccs = UNICODE**, **ccs UTF-16LE =**, veya **ccs = UTF-8**, veya modu kullanılarak bir Unicode çeviri moduna değiştirilirse **_setmode**—*arabellek* bir dizi için bir işaretçi olarak yorumlanır **wchar_t** içeren **UTF-16** veri. Bu modda tek sayıda bayt yazma girişimi, bir parametre doğrulama hatasına neden olur.

## <a name="remarks"></a>Açıklamalar

**_Write** işlevi *sayısı* bayt *arabellek* ilişkili dosyasına *fd*. Belirtilen dosya ile ilgili dosya işaretçisini (varsa) geçerli konumu yazma işlemi başlar. Dosya ekleme için açık değilse, geçerli dosyanın sonunda işlemi başlar. Sonra yazma işlemi, dosya işaretçisini gerçekte yazılan bayt sayısına göre artar.

Metin modunda açılan dosyalar için yazarken **_write** CTRL + Z karakterini mantıksal-dosya sonu değerlendirir. Bir cihaz için yazarken **_write** CTRL + Z karakterini arabelleğindeki çıkış Sonlandırıcı olarak değerlendirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_write**|\<io.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
