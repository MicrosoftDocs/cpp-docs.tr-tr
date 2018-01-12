---
title: "Derleyici Hatası C3917 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3917
dev_langs: C++
helpviewer_keywords: C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bff35b18457035ea03035bd98d467dd20e1d34be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3917"></a>Derleyici Hatası C3917
'*özelliği*': kullanılmayan yapı bildirimi stili  
  
Bir özellik veya olay tanımı Visual Studio 2005 önce bir sürümünden sözdizimi kullanılır.  
  
Daha fazla bilgi için bkz: [özelliği](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
  
```cpp  
// C3917.cpp  
// compile with: /clr /c  
public ref class  C {  
private:  
   int m_length;  
public:  
   C() {  
      m_length = 0;  
   }  
  
   property int get_Length();   // C3917  
  
   // The correct property definition:  
   property int Length {  
      int get() {  
         return m_length;  
      }  
  
      void set( int i ) {  
         m_length = i;  
      }  
   }  
};  
```