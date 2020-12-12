---
description: 'Daha fazla bilgi edinin: stdin, stdout, stderr'
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
ms.openlocfilehash: ba31487c472bd714560e919f45ec9e9aa5acd717
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235729"
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr

## <a name="syntax"></a>Syntax

```
FILE *stdin;
FILE *stdout;
FILE *stderr;
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bunlar giriş, çıkış ve hata çıktısı için standart akışlardır.

Standart giriş, standart çıktı ve standart hata ekranda yazdırıldığında varsayılan olarak klavyeden okunurdur.

Aşağıdaki akış işaretçileri standart akışlara erişmek için kullanılabilir:

|İşaretçi|Akış|
|-------------|------------|
|`stdin`|Standart giriş|
|`stdout`|Standart çıktı|
|`stderr`|Standart hata|

Bu işaretçiler, işlevlerde bağımsız değişkenler olarak kullanılabilir. [GetChar](../c-runtime-library/reference/getchar-getwchar.md) ve [putchar](../c-runtime-library/reference/putchar-putwchar.md)gibi bazı işlevler, `stdin` ve `stdout` otomatik olarak kullanılır.

Bu işaretçiler sabittir ve yeni değerler atanamaz. [Serbest aç](../c-runtime-library/reference/freopen-wfreopen.md) işlevi, akışları disk dosyalarına veya diğer cihazlara yeniden yönlendirmek için kullanılabilir. İşletim sistemi, bir programın standart giriş ve çıkışını komut düzeyinde yeniden yönlendirmenize olanak tanır.

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../c-runtime-library/stream-i-o.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
