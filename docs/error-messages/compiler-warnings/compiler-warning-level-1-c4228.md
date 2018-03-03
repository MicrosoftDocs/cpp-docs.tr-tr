---
title: "Derleyici Uyarısı (düzey 1) C4228 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4228
dev_langs:
- C++
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e924a89b6da03f9ae14baabb222a7baa87dd120
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4228"></a>Derleyici Uyarısı (düzey 1) C4228
kullanılan standart olmayan uzantısı: bildirimcisi listesinde virgülle sonra niteleyicileri yok sayılır  
  
 Niteleyiciler kullanımını ister **const** veya `volatile` değişkenleri bildirirken virgül bir Microsoft uzantısı sonra ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Örnek  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```