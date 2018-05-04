---
title: Nesnelerin kaynakları (RAII) sahibi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfd3f1df54e5b5881ed15efeb98a6e6070f400a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="objects-own-resources-raii"></a>Nesnelerin Kaynakları (RAII)
Kendi kaynaklarını nesneler emin olun. Bu ilke olarak da bilinen "kaynak edinme başlatma" değil veya "RAII."  
  
## <a name="example"></a>Örnek  
 "Yeni" her nesne oluşturucu bağımsız değişkeni bir (neredeyse her zaman unique_ptr) sahip başka bir adlandırılmış nesneyi geçirin.  
  
```cpp  
void f() {  
    unique_ptr<widget> p( new widget() );  
    my_class x( new widget() );  
    // ...  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"  
```  
  
 Her zaman hemen yeni bir kaynak sahip başka bir nesneye geçirin.  
  
```cpp  
void g() {  
    other_class y( OpenFile() );  
    // ...  
} // automatic closing and release for file resource  
  // automatic exception safety, as if "finally { y.file.dispose(); }"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)