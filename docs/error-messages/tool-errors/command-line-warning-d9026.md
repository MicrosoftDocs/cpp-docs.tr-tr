---
title: Komut Satırı Uyarısı D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 3fd8d442dfabaf2f03d8b564c9fdfb1537f6ff28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599440"
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