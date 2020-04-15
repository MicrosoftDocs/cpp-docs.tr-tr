---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a616df570d266c335337d897da59a2a0ec69b40e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367388"
---
# <a name="_write"></a>_write

Bir dosyaya veri yazar.

## <a name="syntax"></a>Sözdizimi

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Verilerin yazıldığı dosya tanımlayıcısı.

*Arabellek*<br/>
Yazılacak veriler.

*Sayısı*<br/>
Bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_write** yazılan bayt sayısını döndürür. Diskte kalan gerçek alan arabelleğe boyutundan küçükse, işlev diske yazmaya çalışıyorsa, **_write** başarısız olur ve arabellin içindekileri diske yıkamaz. -1'in geri dönüş değeri bir hatayı gösterir. Geçersiz parametreler geçirilirse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, işlev -1 döndürür ve **errno** üç değerden birine ayarlanır: **EBADF**, dosya tanımlayıcısı geçersiz veya dosya yazmak için açılmaz anlamına gelir; **ENOSPC**, bu işlem için cihazda yeterli alan kalmadığını anlamına gelir; veya **EINVAL**, *arabellek* null işaretçi si veya bayt tek *bir sayı* Unicode modunda bir dosyaya yazılacak geçirilir anlamına gelir.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [errno, _doserrno, _sys_errlist ve _sys_nerr'a](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

Dosya metin modunda açılırsa, her satır besleme karakteri çıktıdaki bir satır satır besleme çiftiyle değiştirilir. Değiştirme iade değerini etkilemez.

Dosya Unicode çeviri modunda açıldığında—örneğin, *fD* **_open** veya **_sopen** ve **_O_WTEXT**, **_O_U16TEXT**veya **_O_U8TEXT**içeren bir mod parametresi kullanılarak açılırsa veya **fopen** ve **ccs=UNICODE**, **ccs=UTF-16LE**veya **ccs=UTF-8**içeren bir mod parametresi kullanılarak açılırsa veya mod **_setmode**kullanılarak Unicode çeviri moduna değiştirilirse —*buffer* **UTF 16-veri** içeren bir **wchar_t** diziiçin işaretçi olarak yorumlanır. Bu modda tek sayıda bayt yazma girişimi parametre doğrulama hatasına neden olur.

## <a name="remarks"></a>Açıklamalar

**_write** işlevi *fd*ile ilişkili dosyaya *arabellekten* *sayma* baytları yazar. Yazma işlemi, verilen dosyayla ilişkili dosya işaretçisinin (varsa) geçerli konumunda başlar. Dosya ek için açıksa, işlem dosyanın geçerli ucundan başlar. Yazma işleminden sonra, dosya işaretçisi yazılan bayt sayısına göre artırılır.

Metin modunda açılan dosyalara yazarken, **_write** CTRL+Z karakterini dosyanın mantıksal sonu olarak ele verir. Bir aygıta **yazarken, _write** arabellekteki CTRL+Z karakterini çıktı sonlandırıcısı olarak ele alır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_write**|\<io.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
