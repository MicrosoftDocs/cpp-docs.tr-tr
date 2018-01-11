---
title: "(Modern C++) ABI sınırlarında taşınabilirlik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06cb6c97580b4c4c9a6c961cb76f2c4d84d841ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="portability-at-abi-boundaries-modern-c"></a>ABI Sınırlarında Taşınabilirlik (Modern C++)
İkili arabirimi sınırlarında yeterince Taşınabilir türler ve kuralları kullanın. Bir "taşınabilir" C yerleşik bir tür ya da yalnızca C yerleşik türler içeren yapı türüdür. Sınıf türleri yalnızca arama kuralı, vb. düzenini, çağıran ve çağrılan kabul ettiğinde kullanılabilir. Bu yalnızca her ikisi de aynı derleyici ve derleyici ayarları derlendiğinde mümkündür.  
  
## <a name="how-to-flatten-a-class-for-c-portability"></a>C taşınabilirliği için bir sınıf düzleştirmek nasıl  
 Ne zaman arayanlar başka bir derleyici/dili ile derlenmiş, ardından "düzleştirmek" bir **extern "C"** API'si belirli bir arama kuralı ile:  
  
```cpp  
// class widget {  
//   widget();  
//   ~widget();  
//   double method( int, gadget& );  
// };  
extern "C" {        // functions using explicit "this"  
   struct widget;   // opaque type (forward declaration only)  
   widget* STDCALL widget_create();      // constructor creates new "this"  
   void STDCALL widget_destroy(widget*); // destructor consumes "this"  
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)