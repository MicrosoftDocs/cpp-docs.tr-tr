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
ms.openlocfilehash: f611a898018cee5edc031be1db2fd35af8857e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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