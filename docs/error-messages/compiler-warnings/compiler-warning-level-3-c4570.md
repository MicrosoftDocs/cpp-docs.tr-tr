---
title: "Derleyici Uyarısı (Düzey 3) C4570 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4570
dev_langs: C++
helpviewer_keywords: C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8bd962f6d8ada4a1241758b6c4ed726c7950159f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4570"></a>Derleyici Uyarısı (Düzey 3) C4570
'type': soyut ancak soyut işlevleri taşıdığından açıkça bildirilmedi  
  
 İçeren bir türü [soyut](../../windows/abstract-cpp-component-extensions.md) işlevleri kendisini işaretlenir soyut olarak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4570 oluşturur.  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```