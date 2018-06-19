---
title: Derleyici Hatası C2461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47aee3122dad3e875cf58d5a41bcadda297e1463
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197643"
---
# <a name="compiler-error-c2461"></a>Derleyici Hatası C2461
  
> '*sınıfı*': Oluşturucusu sözdizimi biçimsel parametresi eksik  
  
 Sınıf oluşturucusu resmi parametreleri belirtmiyor. Bir oluşturucu bildirimi biçimsel parametresi listesi belirtmelisiniz. Liste boş olabilir.  
  
Bu sorunu gidermek için bildirimi sonra parantez çifti eklemek *sınıfı*:: **sınıfı*.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek, C2461 düzeltmek gösterilmektedir:  
  
```cpp  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;     // C2461  
   C::C();   // OK  
};  
```