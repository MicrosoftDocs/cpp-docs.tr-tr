---
title: "Derleyici Uyarısı (düzey 4) C4212 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4212
dev_langs: C++
helpviewer_keywords: C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9573a6e29ce20a87fb75aa5810ebf4d696695a45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4212"></a>Derleyici Uyarısı (düzey 4) C4212
kullanılan standart olmayan uzantısı: işlev bildirimi kullanılan üç nokta  
  
 İşlev prototipi değişken sayıda bağımsız değişken vardır. İşlev tanımı içermiyor.  
  
 Aşağıdaki örnek C4212 oluşturur:  
  
```  
// C4212.c  
// compile with: /W4 /Ze /c  
void f(int , ...);  
void f(int i, int j) {}  
```