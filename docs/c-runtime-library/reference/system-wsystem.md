---
title: Sistem, _wsystem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9043b5bb76c438ee640f298eeed3f41b84a7ca30
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="system-wsystem"></a>system, _wsystem

Bir komut yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*komutu*<br/>
Yürütülecek komutu.

## <a name="return-value"></a>Dönüş Değeri

Varsa *komutu* olan **NULL** ve komut yorumlayıcı bulunamadı, sıfır olmayan bir değer döndürür. Komut yorumlayıcı bulunmazsa 0 döndürür ve ayarlar **errno** için **ENOENT**. Varsa *komutu* değil **NULL**, **sistem** komut yorumlayıcı tarafından döndürülen değeri döndürür. Yalnızca komut yorumlayıcı 0 değerini döndürürse 0 değerini döndürür. Dönüş değeri - 1 bir hata gösterir ve **errno** aşağıdaki değerlerden birine ayarlayın:

|||
|-|-|
**E2BIG**|(Sistem bağımlı olan) bağımsız değişken listesi çok büyük.
**ENOENT**|Komut yorumlayıcı bulunamıyor.
**ENOEXEC**|Komut yorumlayıcı dosya biçimi geçerli değil çünkü yürütülemez.
**ENOMEM**|Komutu yürütmek yeterli kullanılabilir bellek yok; veya kullanılabilir bellek bozuk; veya geçerli olmayan bir blok var, çağrıyı yapan işlem doğru şekilde ayrılmamış olduğunu gösterir.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bunlar hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**Sistem** işlev geçişleri *komutu* komut yorumlayıcı için hangi yürütür dize olarak bir işletim sistemi komutu. **Sistem** kullanan **COMSPEC** ve **yolu** komut yorumlayıcı bulmak için ortam değişkenleri CMD.exe dosya. Varsa *komutu* olan **NULL**, işlevi yalnızca komut yorumlayıcı var olup olmadığını denetler.

Siz açıkça, kullanarak flush gerekir [fflush](fflush.md) veya [_flushall](flushall.md), veya çağırmadan önce akış kapatmak **sistem**.

**_wsystem** bir joker karakter sürümü **sistem**; *komutu* bağımsız değişkeni **_wsystem** bir joker karakter dizesidir. Bu işlevler aynı şekilde aksi davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**Sistem**|**Sistem**|**_wsystem**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Sistem**|\<Process.h > veya \<stdlib.h >|
|**_wsystem**|\<Process.h > veya \<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnekte **sistem** bir metin dosyası türü.

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
