---
description: 'Hakkında daha fazla bilgi edinin: Command-Line Warning D9026'
title: Komut Satırı Uyarısı D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 910471215d350f266319f5e14b7bb1a62f641028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115488"
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
