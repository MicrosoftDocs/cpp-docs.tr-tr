---
description: 'Hakkında daha fazla bilgi edinin: _pgmptr _wpgmptr'
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
ms.openlocfilehash: 70902be4f1c9686839a958439116fc3e28a2a315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213448"
---
# <a name="_pgmptr-_wpgmptr"></a>_pgmptr, _wpgmptr

Yürütülebilir dosyanın yolu. Kullanım dışı [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) ve [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md)kullanın.

## <a name="syntax"></a>Syntax

```
extern char *_pgmptr;
extern wchar_t *_wpgmptr;
```

## <a name="remarks"></a>Açıklamalar

Komut yorumlayıcısından (Cmd.exe) bir program çalıştırıldığında, `_pgmptr` yürütülebilir dosyanın tam yolu otomatik olarak başlatılır. Örneğin, Hello.exe C:\BIN ' dir ve C:\BIN yolunda yer alıyorsa, şunu çalıştırdığınızda `_pgmptr` C:\BIN\Hello.exe olarak ayarlanır:

```
C> hello
```

Bir program komut satırından `_pgmptr` çalıştırılmadıkça, program adına (dosya adı uzantısı olmadan dosyanın temel adı) veya bir dosya adı, göreli yol veya tam yol olarak başlatılabilir.

`_wpgmptr` , `_pgmptr` tarafından kullanılan programlarla kullanım için geniş karakterli karşıdır `wmain` .

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="requirements"></a>Gereksinimler

|Değişken|Gerekli başlık|
|--------------|---------------------|
|`_pgmptr`, `_wpgmptr`|\<stdlib.h>|

## <a name="example"></a>Örnek

Aşağıdaki program kullanımını gösterir `_pgmptr` .

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

İle ve arasında `_wpgmptr` geçiş yaparak `%Fs` kullanabilirsiniz `%S` `main` `wmain` .

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler](../c-runtime-library/global-variables.md)
