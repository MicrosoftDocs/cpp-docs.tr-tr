---
title: system, _wsystem
ms.date: 4/2/2020
api_name:
- system
- _wsystem
- _o__wsystem
- _o_system
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tsystem
- _wsystem
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
ms.openlocfilehash: 21ce04d30da80a40a1162dce06ff378150008766
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362783"
---
# <a name="system-_wsystem"></a>system, _wsystem

Bir komut uyguluyor.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int system(
   const char *command
);
int _wsystem(
   const wchar_t *command
);
```

### <a name="parameters"></a>Parametreler

*Komut*<br/>
Yürütülecek komut.

## <a name="return-value"></a>Dönüş Değeri

*Komut* **NULL** ise ve komut yorumlayıcısı bulunursa, sıfır olmayan bir değer döndürür. Komut tercümanı bulunamazsa, 0 döndürür ve **ENOENT'e** **errno** ayarlar. *Komut* **NULL**değilse, **sistem** komut tercümanı tarafından döndürülen değeri döndürür. Yalnızca komut tercümanı 0 değerini döndürürse 0 değerini döndürür. - 1'in getiri değeri bir hatayı gösterir ve **errno** aşağıdaki değerlerden birine ayarlanır:

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi (sisteme bağımlı olan) çok büyük. |
| **Enoent** | Komut tercümanı bulunamıyor. |
| **ENOEXEC** | Biçim geçerli olmadığından komut tercüman dosyası yürütülemez. |
| **ENOMEM** | Komutu yürütmek için yeterli bellek kullanılamaz; veya kullanılabilir bellek bozuldu; veya geçerli olmayan bir blok vardır, bu da aramayı yapan işlemin doğru şekilde ayrılmadığını gösterir. |

Bu iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Sistem** işlevi *komutu,* dizeyi işletim sistemi komutu olarak çalıştıran komut yorumlayıcısına geçirir. **komut-tercüman** dosyası CMD.exe'yi bulmak için **COMSPEC** ve **PATH** ortam değişkenlerini kullanır. *Komut* **NULL**ise, işlev yalnızca komut yorumlayıcısının var olup olmadığını denetler.

Fflush veya [_flushall](flushall.md)kullanarak veya **sistemi**aramadan önce herhangi bir akışı kapatarak açıkça [sifonu](fflush.md) çekmeniz gerekir.

**_wsystem** **sistemin**geniş karakterli bir versiyonudur; **_wsystem** *komut* argümanı geniş karakterli bir dizedir. Bu işlevler aynı şekilde başka türlü çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**sistem**|**sistem**|**_wsystem**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sistem**|\<process.h> \<veya stdlib.h>|
|**_wsystem**|\<process.h> \<veya stdlib.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu örnek, bir metin dosyası yazmak için **sistemi** kullanır.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crt_systemtxt"></a>Giriş: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Line one.
Line two.
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec Fonksiyonlar](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
