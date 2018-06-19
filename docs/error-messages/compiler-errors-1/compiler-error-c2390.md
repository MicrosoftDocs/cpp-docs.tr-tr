---
title: Derleyici Hatası C2390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a32a9ca77ba43e5f2866baed91b99103224dbc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198722"
---
# <a name="compiler-error-c2390"></a>Derleyici Hatası C2390
'tanımlayıcısı': 'tanımlayıcısı' yanlış depolama sınıfı  
  
 Depolama sınıfı genel kapsam tanımlayıcısı geçerli değil. Varsayılan depolama sınıfı geçersiz sınıf yerine kullanılır.  
  
 Olası çözümler:  
  
-   Tanımlayıcı bir işlev ise, kendisiyle bildirme `extern` depolama.  
  
-   Tanımlayıcı biçimsel parametresi veya yerel değişken ise, otomatik depolama ile bildirin.  
  
-   Tanımlayıcı genel değişkeni ise hiçbir depolama sınıfı (otomatik depolama) bildirin.  
  
## <a name="example"></a>Örnek  
  
-   Aşağıdaki örnek C2390 oluşturur:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```