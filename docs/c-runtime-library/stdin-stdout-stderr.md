---
title: stdin, stdout, stderr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a36d5fd60a19222e6f802e5a14037fb01ff865f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071984"
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
|**STDOUT**|Standart çıktı|
|`stderr`|Standart hata|

Bu işaretçiler, işlev bağımsız değişkenleri olarak kullanılabilir. Gibi bazı işlevler **getchar** ve `putchar`, kullanın `stdin` ve **stdout** otomatik olarak.

Bu işaretçileri sabittir ve yeni değerler atanamaz. `freopen` İşlevi, disk dosyaları veya diğer cihazlar için akışları yönlendirmek için kullanılabilir. İşletim sistemi, bir programın standart giriş ve çıkış komut düzeyinde yönlendirmenizi sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Stream g/ç](../c-runtime-library/stream-i-o.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)