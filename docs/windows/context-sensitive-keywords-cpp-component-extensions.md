---
title: "Bağlama duyarlı anahtar sözcükler (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d5af53c04c6ff9ec28e7b83cd3a8f9bce8307c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>Bağlama Duyarlı Anahtar Sözcükler (C++ Bileşen Uzantıları)
*Bağlama duyarlı anahtar sözcükler* yalnızca belirli bağlamlarda tanınır dil öğeleridir. Belirli bağlamı dışında kullanıcı tanımlı bir simge bağlama duyarlı anahtar sözcüğü olabilir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 Bağlama duyarlı anahtar sözcükler listesi aşağıdadır:  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [değişmez değer](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [property](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where`(parçası [genel türler](../windows/generics-cpp-component-extensions.md))  
  
 Okunabilirlik için kullanıcı tanımlı simgeler olarak bağlama duyarlı anahtar sözcükler kullanımınız sınırlamak isteyebilirsiniz.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 (Bu özellik için hiçbir platforma özgü açıklamalar vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 (Bu özellik için hiçbir platforma özgü açıklamalar vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneği, uygun bağlamda gösterir `property` bağlama duyarlı anahtar sözcük, bir özellik ve bir değişkeni tanımlamak için kullanılabilir.  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **Output**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)