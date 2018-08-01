---
title: ABI sınırlarında taşınabilirlik (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb9ce8012db8617afc7af3183bd7439ddeb8fab7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402357"
---
# <a name="portability-at-abi-boundaries-modern-c"></a>ABI Sınırlarında Taşınabilirlik (Modern C++)
İkili arabirimi sınırlarında yeterince Taşınabilir türler ve kuralları kullanın. Bir "taşınabilir" C yerleşik bir tür ya da yalnızca C yerleşik türler içeren bir yapı türüdür. Sınıf türleri yalnızca çağırma kuralı, vb. Düzen, çağıran ve çağrılan kabul ettiğinizde kullanılabilir. Bu yalnızca her ikisi de aynı derleyici ve derleyici ayarları ile derlendiğinde mümkündür.  
  
## <a name="how-to-flatten-a-class-for-c-portability"></a>Bir sınıf C taşınabilirliği için düzleştirilecek nasıl  
 Ne zaman çağıranlar başka bir derleyici/dili ile derlenmiş ve ardından "dönüştürme" bir **extern "C"** API'si ile belirli bir çağırma kuralı:  
  
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)