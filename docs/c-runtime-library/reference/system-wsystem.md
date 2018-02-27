---
title: Sistem, _wsystem | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3d46fd4b4df463bfce940360744a0a548652e2b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="system-wsystem"></a>system, _wsystem
Bir komut yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `command`  
 Yürütülecek komutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `command` olan `NULL` ve komut yorumlayıcı bulunamadı, sıfır olmayan bir değer döndürür. Komut yorumlayıcı bulunmazsa 0 döndürür ve ayarlar `errno` için `ENOENT`. Varsa `command` değil `NULL`, `system` komut yorumlayıcı tarafından döndürülen değeri döndürür. Yalnızca komut yorumlayıcı 0 değerini döndürürse 0 değerini döndürür. Dönüş değeri - 1 bir hata gösterir ve `errno` aşağıdaki değerlerden birine ayarlayın:  
  
 `E2BIG`  
 (Sistem bağımlı olan) bağımsız değişken listesi çok büyük.  
  
 `ENOENT`  
 Komut yorumlayıcı bulunamıyor.  
  
 `ENOEXEC`  
 Komut yorumlayıcı dosya biçimi geçerli değil çünkü yürütülemez.  
  
 `ENOMEM`  
 Komutu yürütmek yeterli kullanılabilir bellek yok; veya kullanılabilir bellek bozuk; veya geçerli olmayan bir blok var, çağrıyı yapan işlem doğru şekilde ayrılmamış olduğunu gösterir.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bunlar hakkında daha fazla bilgi için dönüş kodları.  
  
## <a name="remarks"></a>Açıklamalar  
 `system` İşlev geçişleri `command` komut yorumlayıcı için hangi yürütür dize olarak bir işletim sistemi komutu. `system` kullanan `COMSPEC` ve `PATH` komut yorumlayıcı bulmak için ortam değişkenleri CMD.exe dosya. Varsa `command` olan `NULL`, işlevi yalnızca komut yorumlayıcı var olup olmadığını denetler.  
  
 Açıkça flush gerekir — kullanarak `fflush` veya `_flushall`— veya çağırmadan önce akış kapatmak `system`.  
  
 `_wsystem` bir joker karakter sürümü `system`; `command` bağımsız değişkeni `_wsystem` bir joker karakter dizesidir. Bu işlevler aynı şekilde aksi davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`system`|\<Process.h > veya \<stdlib.h >|  
|`_wsystem`|\<Process.h > veya \<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Bu örnekte `system` bir metin dosyası türü.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## <a name="input-crtsystemtxt"></a>Input: crt_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Çıkış  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)