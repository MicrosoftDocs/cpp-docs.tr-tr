---
title: system, _wsystem
ms.date: 11/04/2016
apiname:
- system
- _wsystem
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 46c4949fcc8cfbe4a3477e66b57d8fc6fc97ed73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259098"
---
# <a name="system-wsystem"></a>system, _wsystem

Bir komutu yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Komutu*<br/>
Yürütülecek komut.

## <a name="return-value"></a>Dönüş Değeri

Varsa *komut* olduğu **NULL** ve komut yorumlayıcı bulundu, sıfır olmayan bir değer döndürür. Komut yorumlayıcı bulunmazsa, 0 döndürür ve ayarlar **errno** için **ENOENT**. Varsa *komut* değil **NULL**, **sistem** komut yorumlayıcı tarafından döndürülen değeri döndürür. Yalnızca komut yorumlayıcı 0 değerini döndürürse, 0 değerini döndürür. Dönüş değeri - 1 hata gösterir ve **errno** aşağıdaki değerlerden birine ayarlayın:

|||
|-|-|
| **E2BIG** | (Sistem bağımlı olan) bağımsız değişken listesi çok büyük. |
| **ENOENT** | Komut yorumlayıcı nebyla nalezena. |
| **ENOEXEC** | Komut yorumlayıcı dosya biçimi geçersiz olduğundan yürütülemez. |
| **ENOMEM** | Komutu yürütmek yeterli bellek yok; veya kullanılabilir bellek bozulmuş; veya geçerli olmayan bir blok yok, çağrıyı yapan işlemi düzgün ayrılmamış olduğunu gösterir. |

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bunlar hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**Sistem** işlev geçişleri *komut* komut yorumlayıcıya, dize olarak bir işletim sistemi komutu yürütür. **Sistem** kullanan **COMSPEC** ve **yolu** komut yorumlayıcı bulmak için ortam değişkenlerini CMD.exe dosya. Varsa *komut* olduğu **NULL**, işlev, yalnızca komut yorumlayıcı mevcut olup olmadığını denetler.

Siz açıkça, kullanarak temizleme gerekir [fflush](fflush.md) veya [_flushall](flushall.md), veya çağırmadan önce herhangi bir akışı Kapat **sistem**.

**_wsystem** geniş karakterli sürümüdür **sistem**; *komut* bağımsız değişkeni **_wsystem** geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**Sistem**|**Sistem**|**_wsystem**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Sistem**|\<Process.h > veya \<stdlib.h >|
|**_wsystem**|\<Process.h > veya \<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnekte **sistem** bir metin dosyası yazmak için.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crtsystemtxt"></a>Giriş: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Line one.
Line two.
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
