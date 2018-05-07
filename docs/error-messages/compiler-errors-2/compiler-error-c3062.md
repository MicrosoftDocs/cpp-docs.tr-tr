---
title: Derleyici Hatası C3062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da507511cb5f091d5d9432bbfeb36951e3f43c6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3062"></a>Derleyici Hatası C3062
'enum': temel alınan türü 'type' olduğundan değer Numaralandırıcı gerektirir  
  
 Bir numaralandırma için bir temel alınan tür belirtebilirsiniz. Ancak, bazı türleri her Numaralandırıcı değerleri atamanızı gerektirir.  
  
 Numaralandırmalar hakkında daha fazla bilgi için bkz: [enum sınıfı](../../windows/enum-class-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3062 oluşturur:  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```