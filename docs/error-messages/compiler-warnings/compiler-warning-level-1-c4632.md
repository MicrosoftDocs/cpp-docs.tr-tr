---
title: "Derleyici Uyarısı (düzey 1) C4632 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4632
dev_langs: C++
helpviewer_keywords: C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b8a4257428a3259665da0ac9bdcd6bac38ceda5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4632"></a>Derleyici Uyarısı (düzey 1) C4632
XML belge açıklaması: dosya - erişim reddedildi: nedeni  
  
 .Xdc dosyasının yolunu (`file`) geçerli değil ve hiçbir .xdc dosyası oluşturulur.  
  
 Aşağıdaki örnek C4632 oluşturur:  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```