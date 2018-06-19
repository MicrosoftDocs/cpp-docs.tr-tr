---
title: Derleyici Uyarısı (düzey 1) C4079 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4079
dev_langs:
- C++
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc6c58649c16365d1bbeb22dcf0676947d5d8ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276574"
---
# <a name="compiler-warning-level-1-c4079"></a>Derleyici Uyarısı (düzey 1) C4079
beklenmeyen belirteç 'belirteci'  
  
 Beklenmeyen ayırıcı belirteci pragma bağımsız değişken listesinde oluşur. Pragma kalanı yoksayıldı.  
  
 Aşağıdaki örnek C4079 oluşturur:  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```