---
description: 'Daha fazla bilgi edinin: dosya sabitleri'
title: Dosya Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
ms.openlocfilehash: a174a9bd8924f4d209f937187614863ce7111b3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296608"
---
# <a name="file-constants"></a>Dosya Sabitleri

## <a name="syntax"></a>Syntax

```
#include <fcntl.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitlerden bir veya daha fazla oluşturulan tamsayı ifadesi, izin verilen okuma veya yazma işlemlerinin türünü belirler. Bir veya daha fazla sabit, bir çeviri modu sabiti ile birleştirilerek oluşturulur.

Dosya sabitleri aşağıdaki gibidir:

|Sabit|Açıklama|
|-|-|
| `_O_APPEND`  | Her yazma işleminden önce dosya işaretçisini dosyanın sonuna konumlandırır.  |
| `_O_CREAT`  | Yazmak için yeni bir dosya oluşturur ve açar; Dosya *adı* tarafından belirtilen dosya varsa, bu, hiçbir etkiye sahip değildir.  |
| `_O_EXCL`  | *Filename* tarafından belirtilen dosya varsa bir hata değeri döndürür. Yalnızca ile kullanıldığında geçerlidir `_O_CREAT` .  |
| `_O_RDONLY`  | Dosyayı salt okuma için açar; Bu bayrak verilirse, ne `_O_RDWR` de `_O_WRONLY` verilemez.  |
| `_O_RDWR`  | Dosyayı hem okuma hem de yazma için açar; Bu bayrak verilirse, ne `_O_RDONLY` de `_O_WRONLY` verilemez.  |
| `_O_TRUNC`  | Var olan bir dosyayı açar ve sıfır uzunluğa kırpar; dosya yazma iznine sahip olmalıdır. Dosyanın içeriği yok edilir. Bu bayrak verilirse, belirtemezsiniz `_O_RDONLY` .  |
| `_O_WRONLY`  | Dosyayı yalnızca yazma için açar; Bu bayrak verilirse, ne `_O_RDONLY` de `_O_RDWR` verilemez.  |

## <a name="see-also"></a>Ayrıca bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
