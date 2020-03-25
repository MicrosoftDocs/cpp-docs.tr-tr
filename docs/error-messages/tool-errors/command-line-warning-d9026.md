---
title: Komut Satırı Uyarısı D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 59dfcdc97fb9caf60a018cb20583ee6fca3dcb27
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196709"
---
# <a name="command-line-warning-d9026"></a>Komut Satırı Uyarısı D9026

seçenekler tüm komut satırına uygulanır

Bir dosya adı belirtilmişse komut üzerinde bir seçenek belirtildi. Bu seçenek, önce gelen dosyasına uygulandı.

Örneğin, komutunda

```
CL verdi.c /G5 puccini.c
```

VERDI. c dosyası/G4 varsayılan değer değil,/G5 seçeneği kullanılarak derlenir.

Bu davranış, yalnızca dosya adından önce belirtilen seçenekleri uygulayan, VERDI. c ' nin,/G4 ve PUCCINI. c kullanılarak derlenmesi 5 kullanılarak Derlenmekte olan önceki sürümlerden farklıdır.
