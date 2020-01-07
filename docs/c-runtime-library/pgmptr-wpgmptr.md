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
ms.openlocfilehash: beff0401d0aa2aa21819e58618ef4c02795d4393
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300163"
---
# <a name="_pgmptr-_wpgmptr"></a>_pgmptr, _wpgmptr

Yürütülebilir dosyanın yolu. Kullanım dışı [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) ve [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md)kullanın.

## <a name="syntax"></a>Sözdizimi

```
extern char *_pgmptr;
extern wchar_t *_wpgmptr;
```

## <a name="remarks"></a>Açıklamalar

Komut yorumlayıcısından (cmd. exe) bir program çalıştırıldığında, `_pgmptr` otomatik olarak yürütülebilir dosyanın tam yolu olarak başlatılır. Örneğin, Hello. exe C:\BIN ' dir ve C:\BIN yolunda ise, şunu çalıştırdığınızda `_pgmptr` C:\BIN\Hello.exe olarak ayarlanır:

```
C> hello
```

Bir program komut satırından çalıştırılmadıkça, `_pgmptr` program adına (dosya adı uzantısı olmadan dosyanın temel adı) veya bir dosya adı, göreli yol veya tam yol olarak başlatılabilir.

`_wpgmptr`, `wmain`kullanan programlarla kullanım için `_pgmptr` geniş karakterli bir karşıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="requirements"></a>Gereksinimler

|Değişken|Gerekli başlık|
|--------------|---------------------|
|`_pgmptr`, `_wpgmptr`|\<Stdlib. h >|

## <a name="example"></a>Örnek

Aşağıdaki program `_pgmptr`kullanımını gösterir.

```c
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

`%Fs` `%S` ve `wmain``main` olarak değiştirerek `_wpgmptr` kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)
