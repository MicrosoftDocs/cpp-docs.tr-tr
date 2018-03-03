---
title: "Derleyici Uyarısı (düzey 1) C4224 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4224
dev_langs:
- C++
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 618e0b12ed20b13d85a7198781d1bec0fea78456
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4224"></a>Derleyici Uyarısı (düzey 1) C4224
kullanılan standart olmayan uzantısı: biçimsel parametresi 'tanımlayıcısı' daha önce bir tür olarak tanımlanmıştı  
  
 Tanımlayıcı olarak daha önce kullanılmış bir `typedef`. Bu uyarı ANSI Uyumluluğu altında neden olur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Örnek  
  
```  
// C4224.cpp  
// compile with: /Za /W1 /LD  
typedef int I;  
void func ( int I );  // C4224  
```