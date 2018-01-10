---
title: "Derleyici Hatası C3140 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3140
dev_langs: C++
helpviewer_keywords: C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ebc5b182b7f4ae70fa2f767fbeae0a51b0507e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3140"></a>Derleyici Hatası C3140
birden çok 'module' öznitelikleri aynı derleme biriminde olamaz  
  
 [Modülü](../../windows/module-cpp.md) özniteliği yalnızca tanımlanabilir kez her projesi.  
  
 Aşağıdaki örnek C3140 oluşturur:  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```