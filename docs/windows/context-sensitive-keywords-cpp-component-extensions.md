---
title: "Bağlama duyarlı anahtar sözcükler (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: internal_CPP
dev_langs: C++
helpviewer_keywords: context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68ff63d5b596d575f26ec0f56a3ac7a568c8471e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>Bağlama Duyarlı Anahtar Sözcükler (C++ Bileşen Uzantıları)
*Bağlama duyarlı anahtar sözcükler* yalnızca belirli bağlamlarda tanınır dil öğeleridir. Belirli bağlamı dışında kullanıcı tanımlı bir simge bağlama duyarlı anahtar sözcüğü olabilir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 Bağlama duyarlı anahtar sözcükler listesi aşağıdadır:  
  
-   [Özet](../windows/abstract-cpp-component-extensions.md)  
  
-   [temsilci seçme](../windows/delegate-cpp-component-extensions.md)  
  
-   [Olay](../windows/event-cpp-component-extensions.md)  
  
-   [Son olarak](../dotnet/finally.md)  
  
-   [her biri için](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [değişmez değer](../windows/literal-cpp-component-extensions.md)  
  
-   [geçersiz kılma](../windows/override-cpp-component-extensions.md)  
  
-   [özelliği](../windows/property-cpp-component-extensions.md)  
  
-   [korumalı](../windows/sealed-cpp-component-extensions.md)  
  
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
  
 **Çıktı**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)