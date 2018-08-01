---
title: Derleme (Modern C++) derleme zamanı kapsüllemesi için Pimpl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e80c4bd86cd4c7400e3937fcb8d164fe6b14106
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404661"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)
*Derleme pimpl deyim* bağlantısından en aza indirmek ve arabirimleri ayırmak için uygulama gizlemek için modern bir C++ Teknik. Derleme Pimpl kısaltması "uygulaması." işaretçisidir Zaten kavramı hakkında bilgi sahibi olmanız ancak Cheshire Cat veya derleyici güvenlik duvarı deyim gibi diğer adlarıyla bildirin.  
  
## <a name="why-use-pimpl"></a>Derleme pimpl neden kullanmalısınız?  
 Derleme pimpl deyim yazılım geliştirme yaşam döngüsünün nasıl geliştireceğiniz aşağıda verilmiştir:  
  
-   Derleme bağımlılıkları küçültme.  
  
-   Arabirim ve uygulama ayrılması.  
  
-   Taşınabilirlik.  
  
## <a name="pimpl-header"></a>Derleme Pimpl üstbilgisi  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
```  
  
 Derleme pimpl deyim yeniden basamaklar ve kırılgan nesne düzeni önler. De (Geçişli) popüler türleri için de uygundur.  
  
## <a name="pimpl-implementation"></a>Derleme Pimpl uygulama  
 Tanımlama `impl` .cpp dosyası sınıfta.  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>Önerilen uygulamalar  
 Oluşturmayan takas özelleştirmesi için destek eklenip eklenmeyeceğini göz önünde bulundurun.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)