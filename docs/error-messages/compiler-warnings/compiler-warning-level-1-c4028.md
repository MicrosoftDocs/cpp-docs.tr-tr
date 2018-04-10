---
title: Derleyici Uyarısı (düzey 1) C4028 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 757db68ce894f82064f1635451255a266747a14d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4028"></a>Derleyici Uyarısı (düzey 1) C4028
biçimsel parametresi 'numara' bildiriminden farklı  
  
 Biçimsel parametresi türü bildirimi içinde karşılık gelen bir parametre ile kabul kaydedilmeyecek. Özgün bildiriminde türü kullanılır.  
  
 Bu uyarı yalnızca C kaynak kodu için geçerli olur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4028 oluşturur.  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```