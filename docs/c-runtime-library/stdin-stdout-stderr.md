---
title: stdin, stdout, stderr
ms.date: 10/23/2018
f1_keywords:
- stdin
- stderr
- stdout
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
ms.openlocfilehash: 5de1ff01282f30ad133f909cb87f5d7c8d521ae5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267760"
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr

## <a name="syntax"></a>Sözdizimi

```
FILE *stdin;
FILE *stdout;
FILE *stderr;
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu giriş, çıkış ve hata çıktısı için standart akışlarıdır.

Standart çıktı ve standart hata ekrana yazdırılır sırasında varsayılan olarak, standart giriş klavyeden okunur.

Aşağıdaki akış işaretçiler standart akışları erişmek kullanılabilir:

|İşaretçi|Akış|
|-------------|------------|
|`stdin`|Standart giriş|
|`stdout`|Standart çıktı|
|`stderr`|Standart hata|

Bu işaretçiler, işlev bağımsız değişkenleri olarak kullanılabilir. Gibi bazı işlevler [getchar](../c-runtime-library/reference/getchar-getwchar.md) ve [putchar](../c-runtime-library/reference/putchar-putwchar.md), kullanın `stdin` ve `stdout` otomatik olarak.

Bu işaretçileri sabittir ve yeni değerler atanamaz. [Freopen](../c-runtime-library/reference/freopen-wfreopen.md) işlevi, disk dosyaları veya diğer cihazlar için akışları yönlendirmek için kullanılabilir. İşletim sistemi, bir programın standart giriş ve çıkış komut düzeyinde yönlendirmenizi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../c-runtime-library/stream-i-o.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
