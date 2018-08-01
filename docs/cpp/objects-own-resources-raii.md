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
ms.openlocfilehash: 265eccc4c1a9f51a03e5a84433a9f7e9cc6d6a92
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402142"
---
# <a name="objects-own-resources-raii"></a>Nesnelerin Kaynakları (RAII)
Kendi kaynaklarını nesnelerin emin olun. Bu ilke olarak da bilinen "kaynak alımı başlatma" ise veya "RAII."  
  
## <a name="example"></a>Örnek  
 "Yeni" her nesne (hemen her zaman unique_ptr) sahip başka bir adlandırılmış nesnesi bir oluşturucu bağımsız değişken olarak geçirin.  
  
```cpp  
void f() {  
    unique_ptr<widget> p( new widget() );  
    my_class x( new widget() );  
    // ...  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"  
```  
  
 Her zaman hemen yeni bir kaynak sahibi başka bir nesneye geçirin.  
  
```cpp  
void g() {  
    other_class y( OpenFile() );  
    // ...  
} // automatic closing and release for file resource  
  // automatic exception safety, as if "finally { y.file.dispose(); }"  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)