---
title: Derleyici Uyarısı (düzey 1) C4224 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4224
dev_langs:
- C++
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91f74aee988264706d5c74e94c8198a448f66465
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276717"
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