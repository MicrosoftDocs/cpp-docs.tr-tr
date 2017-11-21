---
title: "Derleme (Modern C++) derleme zamanı kapsüllemesi için Pimpl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cfb333052b0f54ac241607ba7324dca920b8051
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)
*Derleme pimpl deyim* uygulaması, bağlantı en aza indirmek ve arabirimleri ayırmak için gizlemek için bir modern C++ tekniğidir. Derleme Pimpl kısaltması "uygulamasına." işaretçidir Zaten kavramına aşina ancak Cheshire kat veya derleyici güvenlik duvarı deyim gibi diğer adları tarafından biliyor.  
  
## <a name="why-use-pimpl"></a>Derleme pimpl neden kullanılır?  
 Derleme pimpl deyim yazılım geliştirme yaşam döngüsü nasıl artırabilir aşağıda verilmiştir:  
  
-   Derleme bağımlılıkları minimization.  
  
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
  
 Derleme pimpl deyim yeniden basamaklar ve kırılır nesne düzenleri önler. İyi (Geçişli) popüler türleri için de uygundur.  
  
## <a name="pimpl-implementation"></a>Derleme Pimpl uygulama  
 Tanımlamak `impl` .cpp dosyasındaki sınıfı.  
  
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
 Atma olmayan takas uzmanlık desteği eklenip eklenmeyeceğini göz önünde bulundurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)