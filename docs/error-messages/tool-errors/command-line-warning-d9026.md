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
ms.openlocfilehash: 9e2d99573ee46c51178cc2fe995fa0f526b800f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9026"></a>Komut Satırı Uyarısı D9026
tüm komut satırı seçenekleri Uygula  
  
 Bir dosya adı belirtilmedi sonra bir seçenek komutu belirtildi. Seçeneği, onu öncesinde dosyanın uygulandı.  
  
 Örneğin, komut içinde  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 dosyanın VERDI.c /G4 varsayılan /G5 seçeneği kullanılarak derlenecek.  
  
 Bu davranış, uygulanan içinde VERDI.c kaynaklanan filename önce belirtilen seçenekleri kullanarak derlenmiş//G5 kullanarak G4 ve PUCCINI.c derlenmiş yalnızca bazı önceki sürümlerinde, farklıdır.