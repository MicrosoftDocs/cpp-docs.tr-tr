---
title: _setmode
ms.date: 4/2/2020
api_name:
- _setmode
- _o__setmode
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
- _setmode
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
ms.openlocfilehash: 36d2130d4039f1f87f7f54fc26ad02cb8d519b4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353830"
---
# <a name="_setmode"></a>_setmode

Dosya çeviri modunu ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Dosya tanımlayıcısı.

*Modu*<br/>
Yeni çeviri modu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, önceki çeviri modunu döndürür.

Geçersiz parametreler bu işleve aktarılırsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse, bu işlev -1 döndürür ve geçersiz bir dosya tanımlayıcısı veya Geçersiz *mod* bağımsız değişkenini gösteren **EBADF'a** **EINVAL** **errno** ayarlar.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_setmode** işlevi *fd*tarafından verilen dosyanın çeviri modunu *moduna* ayarlar. *Kip* olarak **_O_TEXT** geçme metni ayarlar (yani, çevrilmiş) modu. Taşıma satır beslemesi (CR-LF) kombinasyonları girişte tek bir satır besleme karakterine dönüştürülür. Satır besleme karakterleri çıktıda CR-LF kombinasyonlarına çevrilir. Geçen **_O_BINARY** bu çevirilerin bastırıldığı ikili (çevrilmemiş) modu belirler.

Ayrıca, bu belgede daha sonra ikinci örnekte gösterildiği gibi Unicode modunu etkinleştirmek için **_O_U16TEXT,** **_O_U8TEXT**veya **_O_WTEXT** geçirebilirsiniz.

> [!CAUTION]
> Unicode modu geniş yazdırma işlevleri içindir (örneğin, `wprintf`) ve dar yazdırma işlevleri için desteklenmez. Unicode modu akışında dar bir yazdırma işlevinin kullanılması bir ileri sözletetikler.

**_setmode** genellikle **stdin** ve **stdout**varsayılan çeviri modunu değiştirmek için kullanılır, ancak herhangi bir dosya üzerinde kullanabilirsiniz. Akış için dosya tanımlayıcısına **_setmode** uygularsanız, akışta herhangi bir giriş veya çıktı işlemi gerçekleştirmeden önce **_setmode** arayın.

> [!CAUTION]
> Bir dosya akışına veri yazarsanız, modu değiştirmek için **_setmode** kullanmadan önce [fflush](fflush.md) kullanarak kodu açıkça temizleyin. Kodu sifonu çekmezseniz, beklenmeyen davranışlar alabilirsiniz. Akışa veri yazmadıysanız, kodu temizlemeniz gerekmez.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe Bağlı Üstbilgi|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
