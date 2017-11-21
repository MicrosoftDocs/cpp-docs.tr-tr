---
title: "Derleyici Hatası C2142 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2142
dev_langs: C++
helpviewer_keywords: C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3a7e3a8950718ef50c8a497847d72a371f592e59
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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