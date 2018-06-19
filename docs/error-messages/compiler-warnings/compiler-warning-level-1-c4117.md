---
title: Derleyici Uyarısı (düzey 1) C4117 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4117
dev_langs:
- C++
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3087e7510e4a803d2a47de4a3c36eafdb86b8da8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278258"
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