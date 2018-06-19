---
title: Derleyici Hatası C3923 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3923
dev_langs:
- C++
helpviewer_keywords:
- C3923
ms.assetid: db8838e9-6344-4cd6-83e0-a8abeb12c4c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d93ff388ae4ba1a97f9a194df1ca1006e05eb51
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275155"
---
# <a name="compiler-error-c3923"></a>Derleyici Hatası C3923
'member': yerel sınıf, yapı veya birleşim tanımları WinRT ya da yönetilen sınıf üye işlevi içinde izin verilmez  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3923 oluşturur.  
  
```  
// C3923.cpp  
// compile with: /clr /c  
ref struct x {  
   void Test() {  
      struct a {};   // C3923  
      class b {};   // C3923  
      union c {};   // C3923  
   }  
};  
```