---
title: "Derleyici Hatası C2142 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2142
dev_langs:
- C++
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91823d90eeefab73c271aab4eb716433e7dada05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2142"></a>Derleyici Hatası C2142
işlev bildirimleri farklılık gösterir, yalnızca bunlardan birinin içinde belirtilen değişken parametreleri  
  
 Bir işlevin bildirimi değişken parametre listesini içerir. Başka bir bildirim yoktur. ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) yalnızca.  
  
 Aşağıdaki örnek C2142 oluşturur:  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```