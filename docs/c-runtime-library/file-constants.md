---
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
ms.openlocfilehash: 672297b2a1d6466f28a7addf74b8d88e2460b15e
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517594"
---
# <a name="file-constants"></a>Dosya Sabitleri

## <a name="syntax"></a>Sözdizimi

```

#include <fcntl.h>
```

## <a name="remarks"></a>Açıklamalar

Bir tamsayı ifade oluşturulmuş ya da bu sabitlerin daha fazla okuma veya yazma işlemlerini izin türünü belirler. Bir veya daha fazla sabit bir çeviri modu sabit ile birleştirerek oluşturulur.

Dosya sabitleri aşağıdaki gibidir:

|Sabit|Açıklama|
|-|-|
| `_O_APPEND`  | Dosya işaretçisini dosyanın her yazma işleminden önce sonuna yeniden konumlandırır.  |
| `_O_CREAT`  | Oluşturur ve yeni bir dosya yazma için açar. dosyayı tarafından belirtilen Bunun hiçbir etkisi *filename* bulunmaktadır.  |
| `_O_EXCL`  | Belirtilen dosya bir hata değeri döndürür *filename* bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir `_O_CREAT`.  |
| `_O_RDONLY`  | Yalnızca okuma için dosyayı açar; Bu bayrak, diğerinden belirtilmezse `_O_RDWR` ya da `_O_WRONLY` verilebilir.  |
| `_O_RDWR`  | Dosyayı hem okuma ve yazma için açar; Bu bayrak, diğerinden belirtilmezse `_O_RDONLY` ya da `_O_WRONLY` verilebilir.  |
| `_O_TRUNC`  | Açılır ve uzunluğu sıfır olarak mevcut bir dosyayı keser; Dosya yazma iznine sahip olmalıdır. Dosyanın içeriği yok edilir. Bu bayrak verilen varsa belirtemezsiniz `_O_RDONLY`.  |
| `_O_WRONLY`  | Yalnızca yazma dosyayı açar; Bu bayrak, diğerinden belirtilmezse `_O_RDONLY` ya da `_O_RDWR` verilebilir.  |

## <a name="see-also"></a>Ayrıca Bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)