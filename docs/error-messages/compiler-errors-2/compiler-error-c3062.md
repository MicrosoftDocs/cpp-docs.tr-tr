---
title: "Derleyici Hatası C3062 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3062
dev_langs: C++
helpviewer_keywords: C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1eebf751c267e9688eebb8c679fe801f77cfa4c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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