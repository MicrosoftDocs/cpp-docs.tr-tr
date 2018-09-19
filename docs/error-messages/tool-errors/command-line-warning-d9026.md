---
title: Komut satırı uyarısı D9026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07be633e56dad6c8f0b304a3c88c1b9919221d4a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079160"
---
# <a name="command-line-warning-d9026"></a>Komut Satırı Uyarısı D9026

Seçenekler tüm komut satırına uygulanır

Bir dosya adı belirtildi sonra komutu bir seçenek belirtildi. Seçeneği, onu öncesinde bir dosyaya uygulandı.

Örneğin, komut

```
CL verdi.c /G5 puccini.c
```

' % s'dosyası VERDI.c /G4 varsayılan /G5 seçeneği kullanılarak derlenir.

Bu davranış, uygulanan VERDI.c bunun sonucunda dosya önce belirtilen seçenekleri kullanarak derlenen/G4 ve PUCCINI.c /G5 kullanarak derlenen yalnızca önceki bazı sürümlerinde farklılık gösterir.