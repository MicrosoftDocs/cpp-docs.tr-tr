---
description: 'Hakkında daha fazla bilgi edinin: _write'
title: _write
ms.date: 4/2/2020
api_name:
- _write
- _o__write
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: 15988f803b37f9ce128a49662c2311a4aa6ca8fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117165"
---
# <a name="_write"></a>_write

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

Başarılı olursa **_write** yazılan bayt sayısını döndürür. Diskte kalan gerçek alan, işlevin diske yazmaya çalıştığı arabelleğin boyutundan küçükse, **_write** başarısız olur ve arabelleğin herhangi bir içeriğini diske temizlemez. -1 ' in dönüş değeri bir hatayı gösterir. Geçersiz parametreler geçirilmemişse, bu işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlev-1 döndürür ve **errno** üç değerden birine ayarlanır: **EBADF**, bu, dosya tanımlayıcısının geçersiz olduğu veya dosyanın yazmak için açılmadığı anlamına gelir; **Enospc**, bu, cihazda işlem için yeterli alan olmadığı anlamına gelir; ya da **EINVAL**, bu, *arabelleğin* boş bir işaretçi olduğu veya Unicode modundaki bir dosyaya yazılması için tek bayt *sayısının* geçirildiği anlamına gelir.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dosya metin modunda açılırsa, her satır besleme karakteri çıkışdaki bir satır başı satır besleme çiftiyle değiştirilmiştir. Değişiklik, dönüş değerini etkilemez.

Dosya Unicode çeviri modunda açıldığında — Örneğin, *fd* **_open** veya **_sopen** kullanılarak açılırsa ve **_O_WTEXT** içeren bir mod parametresi, **_O_U16TEXT** veya **_O_U8TEXT** ya da **FOPEN** ve **CCS = UNICODE**, **CCS = UTF-16le** veya **CCS = UTF-8** içeren bir mod parametresi kullanılarak açılırsa veya mod, **_setmode** kullanarak bir Unicode çeviri moduna değiştiyse,*arabellek* **`wchar_t`** **UTF-16** verileri içeren bir dizinin işaretçisi olarak yorumlanır. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.

## <a name="remarks"></a>Açıklamalar

**_Write** işlevi *arabellekteki* *sayı* baytlarını *FD* ile ilişkili dosyaya yazar. Yazma işlemi, belirtilen dosyayla ilişkili dosya işaretçisinin (varsa) geçerli konumunda başlar. Dosya ekleme için açıksa, işlem dosyanın geçerli ucunda başlar. Yazma işleminden sonra, dosya işaretçisi yazılan bayt sayısıyla artar.

Metin modunda açılan dosyalara yazarken **_write** , bir CTRL + Z karakterini dosyanın mantıksal sonu olarak değerlendirir. Bir cihaza yazarken **_write** , ARABELLEKTEKI bir CTRL + Z karakterini çıkış Sonlandırıcı olarak değerlendirir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_write**|\<io.h>|

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
            // An unrelated error occurred
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
