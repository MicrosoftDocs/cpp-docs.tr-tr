---
title: _setmode
ms.date: 11/04/2016
api_name:
- _setmode
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmode
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
ms.openlocfilehash: 7f14cc9451b93a9077916b8c650645990ba654a3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948589"
---
# <a name="_setmode"></a>_setmode

Dosya çevirisi modunu ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Dosya tanımlayıcısı.

*modundaysa*<br/>
Yeni çeviri modu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, önceki çeviri modunu döndürür.

Bu işleve geçersiz parametreler geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev-1 döndürür ve **errno** **, geçersiz**bir dosya tanımlayıcısı ya da geçersiz bir *mod* bağımsız değişkenini gösteren **EINVAL**.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Setmode** işlevi, *FD*tarafından verilen dosyanın çeviri modunu *mod* olarak belirler. **_O_text** *modunun mod* olarak geçirilmesi, metin (yani, çevrilmiş) modunu belirler. Satır başı satır besleme (CR-LF) birleşimleri, girişte tek satırlık bir akış karakteriyle çevrilir. Satır akış karakterleri, çıkışta CR-LF birleşimlerine çevrilir. **_O_binary** , bu çevirilerin gizlendiği ikili (çevrilmemiş) modu geçirme.

Ayrıca, bu belgenin devamındaki ikinci örnekte gösterildiği gibi, **_O_u16text**, **_O_U8TEXT**veya **_O_wtext** 'i Unicode modunu etkinleştirmek üzere geçirebilirsiniz.

> [!CAUTION]
> Unicode modu geniş yazdırma işlevlerine yöneliktir (örneğin, `wprintf`) ve dar yazdırma işlevlerinde desteklenmez. Bir UNICODE modundaki bir dar Print işlevinin kullanımı bir onaylama tetikler.

**_setmode** , genellikle **stdin** ve **stdout**varsayılan çeviri modunu değiştirmek için kullanılır, ancak bunu herhangi bir dosya üzerinde kullanabilirsiniz. Bir akışın dosya tanımlayıcısına **_setmode** uygularsanız, akışta herhangi bir giriş veya çıkış işlemini gerçekleştirmeden önce **_setmode** komutunu çağırın.

> [!CAUTION]
> Bir dosya akışına veri yazarsanız, modu değiştirmek için **_setmode** komutunu kullanmadan önce [fflush](fflush.md) kullanarak kodu açık bir şekilde temizleyin. Kodu temizlemeyin, beklenmeyen davranışlarla karşılaşabilirsiniz. Akışa veri yazmadınız, kodu temizlemeyin.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_setmode**|\<GÇ. h >|\<fcntl. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_setmode.c
// This program uses _setmode to change
// stdin from text mode to binary mode.

#include <stdio.h>
#include <fcntl.h>
#include <io.h>

int main( void )
{
   int result;

   // Set "stdin" to have binary mode:
   result = _setmode( _fileno( stdin ), _O_BINARY );
   if( result == -1 )
      perror( "Cannot set mode" );
   else
      printf( "'stdin' successfully changed to binary mode\n" );
}
```

```Output
'stdin' successfully changed to binary mode
```

## <a name="example"></a>Örnek

```C
// crt_setmodeunicode.c
// This program uses _setmode to change
// stdout to Unicode. Cyrillic and Ideographic
// characters will appear on the console (if
// your console font supports those character sets).

#include <fcntl.h>
#include <io.h>
#include <stdio.h>

int main(void) {
    _setmode(_fileno(stdout), _O_U16TEXT);
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
