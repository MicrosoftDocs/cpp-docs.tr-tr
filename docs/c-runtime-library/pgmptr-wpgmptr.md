---
title: _pgmptr, _wpgmptr
ms.date: 11/04/2016
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
ms.openlocfilehash: 6991dfe90e58352b26d7c914e1601a68674b8a5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289084"
---
# <a name="pgmptr-wpgmptr"></a>_pgmptr, _wpgmptr

Yürütülebilir dosyanın yolu. Kullanım dışı; kullanma [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) ve [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).

## <a name="syntax"></a>Sözdizimi

```
extern char *_pgmptr;
extern wchar_t *_wpgmptr;
```

## <a name="remarks"></a>Açıklamalar

Komut yorumlayıcı (Cmd.exe), bir program çalıştırıldığında `_pgmptr` yürütülebilir dosyanın tam yolunu otomatik olarak başlatılır. Hello.exe C:\BIN ve C:\BIN Örneğin, yol ise `_pgmptr` yürüttüğünüzde C:\BIN\Hello.exe için ayarlanır:

```
C> hello
```

Bir program komut satırından çalıştırdığınızda değil, `_pgmptr` program adına (dosya adı uzantısı olmadan dosyanın temel adı) veya bir dosya adı, göreli yol ya da tam yol başlatılmış.

`_wpgmptr` geniş karakter karşılığı olan `_pgmptr` ile kullanmak için kullanan programlar `wmain`.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="requirements"></a>Gereksinimler

|Değişken|Gerekli başlık|
|--------------|---------------------|
|`_pgmptr`, `_wpgmptr`|\<stdlib.h >|

## <a name="example"></a>Örnek

Aşağıdaki program kullanımını gösteren `_pgmptr`.

```
// crt_pgmptr.c
// compile with: /W3
// The following program demonstrates the use of _pgmptr.
//
#include <stdio.h>
#include <stdlib.h>
int main( void )
{
   printf("The full path of the executing program is : %Fs\n",
     _pgmptr); // C4996
   // Note: _pgmptr is deprecated; use _get_pgmptr instead
}
```

Kullanabileceğinizi `_wpgmptr` değiştirerek `%Fs` için `%S` ve `main` için `wmain`.

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)
