---
title: Derleyici Hatası C2142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2142
dev_langs:
- C++
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11fd3cd62b236daa93424f53a0896888a89fe33d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170404"
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