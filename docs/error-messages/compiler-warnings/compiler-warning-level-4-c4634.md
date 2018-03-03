---
title: "Derleyici Uyarısı (düzey 4) C4634 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4634
dev_langs:
- C++
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f2812675fd47c72bc0825f9afb870af2451731d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4634"></a>Derleyici Uyarısı (düzey 4) C4634
XML belge açıklaması: uygulanamaz: nedeni  
  
 XML belge etiketleri için tüm C++ değil uygulanabilir oluşturur.  Örneğin, bir ad alanı veya şablon için bir belge açıklama ekleyemezsiniz.  
  
 Daha fazla bilgi için bkz: [XML belgeleri](../../ide/xml-documentation-visual-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4634 oluşturur.  
  
```  
// C4634.cpp  
// compile with: /W4 /doc /c  
/// This is a namespace.   // C4634  
namespace hello {  
   class MyClass  {};  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4634 oluşturur.  
  
```  
// C4634_b.cpp  
// compile with: /W4 /doc /c  
/// This is a template.   // C4634  
template <class T>  
class MyClass  {};  
```