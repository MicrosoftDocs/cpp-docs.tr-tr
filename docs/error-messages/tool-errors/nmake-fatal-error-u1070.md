---
title: NMAKE önemli hatası U1070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe39a5d6f6074596561cd8e32f7b9428bc60f6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE Önemli Hatası U1070
Makro tanımı 'makroadı' döngüsü  
  
 Verilen makro tanımı verilen makro tanımlarını içeren bir makro içeriyor. Döngüsel makro tanımı geçersiz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki makrosu tanımları  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 Aşağıdaki hata neden:  
  
```  
cycle in macro definition 'TWO'  
```