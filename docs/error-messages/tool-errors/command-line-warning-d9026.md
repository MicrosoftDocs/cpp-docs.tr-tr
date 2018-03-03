---
title: "Komut satırı uyarısı D9026 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9127ad1887d476e5460798f806c2db1ff3144de3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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