---
title: "Derleyici Uyarısı (düzey 1) C4228 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4228
dev_langs: C++
helpviewer_keywords: C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac01b49a45a64d1a4e1480a64410726c61975c51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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