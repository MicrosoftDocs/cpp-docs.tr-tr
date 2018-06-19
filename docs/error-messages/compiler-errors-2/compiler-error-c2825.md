---
title: Derleyici Hatası C2825 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2825
dev_langs:
- C++
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5352901d50e011229ed9aa4715923881c26a8fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237243"
---
# <a name="compiler-error-c2825"></a>Derleyici Hatası C2825
var: bir sınıf veya tarafından izlendiğinde ad olmalıdır '::'  
  
 Başarısız bir tam ad oluşturmak için çalışıldı.  
  
 Örneğin, kodunuzu işlev adı ile başladığı bir işlev bildirimi içermediğinden emin olun::.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2825 oluşturur:  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```