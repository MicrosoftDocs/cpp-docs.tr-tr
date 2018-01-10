---
title: "Derleyici Uyarısı (düzey 1) C4117 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4117
dev_langs: C++
helpviewer_keywords: C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dfa9fbe5295db86e4ea4c70bda6d93679393a1b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4117"></a>Derleyici Uyarısı (düzey 1) C4117
Makro adı 'name' ayrılmıştır; 'Komutu göz ardı'  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Tanımlamak veya önceden tanımlanmış makrosu tanımsız çalışılıyor.  
  
2.  Tanımlamak veya önişlemci işleci tanımsız çalışılırken **tanımlanan**.  
  
 Aşağıdaki örnek C4117 oluşturur:  
  
```  
// C4117.cpp  
// compile with: /W1  
#define __FILE__ test         // C4117. __FILE__ is a predefined macro  
#define ValidMacroName test   // ok  
  
int main() {  
}  
```