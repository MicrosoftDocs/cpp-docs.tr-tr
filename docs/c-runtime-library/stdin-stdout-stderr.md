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
ms.openlocfilehash: f9ed1f842bd174c2b926572856152cd69ade5a56
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328025"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Stream g/ç](../c-runtime-library/stream-i-o.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
