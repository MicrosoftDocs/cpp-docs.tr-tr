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
ms.openlocfilehash: 032bf332caee09fbe17d58eeae16ab44b98402d3
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376296"
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
Verilerin yazıldığı dosyanın dosya tanımlayıcısı.

*arabelleğin*<br/>
Yazılacak veriler.

*biriktirme*<br/>
Bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_write** yazılan bayt sayısını döndürür. Diskte kalan gerçek alan, işlevin diske yazmaya çalıştığı arabelleğin boyutundan daha azsa, **_yazma** başarısız olur ve arabelleğin içeriğini diske temizlemez. -1 ' in dönüş değeri bir hatayı gösterir. Geçersiz parametreler geçirilmemişse, bu işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlev-1 döndürür ve **errno** üç değerden birine ayarlanır: **EBADF**, dosya tanımlayıcısının geçersiz olması veya dosyanın yazma için açılmadığı anlamına gelir; **Enospc**, bu, cihazda işlem için yeterli alan olmadığı anlamına gelir; ya da **EINVAL**, bu, *arabelleğin* boş bir işaretçi olduğu veya Unicode modundaki bir dosyaya yazılması için tek bayt *sayısının* geçirildiği anlamına gelir.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dosya metin modunda açılırsa, her satır besleme karakteri çıkışdaki bir satır başı satır besleme çiftiyle değiştirilmiştir. Değişiklik, dönüş değerini etkilemez.

Dosya Unicode çeviri modunda açıldığında — Örneğin, *FD* **_open** veya **_Sopen** kullanılarak açıldıysa ve **_O_WTEXT**, **_O_u16text**veya **_O_U8TEXT**içeren bir mode parametresi veya kullanılarak açılırsa  **CCS = UNICODE**, **CCS = UTF-16LE**, veya **CCS = UTF-8**içeren bir mod parametresi veya mod, **_setmode**kullanarak bir UNICODE çeviri moduna değiştirildiyse,*arabellek* bir işaretçi olarak yorumlanır **UTF-16** verileri içeren **wchar_t** dizisi. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.

## <a name="remarks"></a>Açıklamalar

**_Write** işlevi *arabellekteki* *sayı* baytlarını *FD*ile ilişkili dosyaya yazar. Yazma işlemi, belirtilen dosyayla ilişkili dosya işaretçisinin (varsa) geçerli konumunda başlar. Dosya ekleme için açıksa, işlem dosyanın geçerli ucunda başlar. Yazma işleminden sonra, dosya işaretçisi yazılan bayt sayısıyla artar.

Metin modunda açılan dosyalara yazarken, **_write** , dosyanın mantıksal sonu olarak bir CTRL + Z karakteri uygular. Bir cihaza yazarken, **_write** ARABELLEĞE bir CTRL + Z karakteri ile çıkış Sonlandırıcı olarak davranır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_write**|\<GÇ. h >|

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

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
