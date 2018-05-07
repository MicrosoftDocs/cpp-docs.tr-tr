---
title: Derleyici Hatası C3388 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3388
dev_langs:
- C++
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 481096aa870d7e66df032f4d297c652417a7b487
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3388"></a>Derleyici Hatası C3388
'type': 'ref class' varsayılarak kısıtlama olarak izin verilmiyor ayrıştırma devam etmek için  
  
 Bir kısıtlama üzerinde genel bir tür belirtildi, ancak kısıtlaması doğru şekilde belirtilmedi. Bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3388 oluşturur.  
  
```  
// C3388.cpp  
// compile with: /clr /c  
interface class AA {};  
  
generic <class T>  
where T : interface class   // C3388  
ref class C {};  
  
// OK  
generic <class T>  
where T : AA  
ref class D {};  
```