---
title: "Derleyici Hatası C3062 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fa921df80f0740387217ec9b295cfa90e089d54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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