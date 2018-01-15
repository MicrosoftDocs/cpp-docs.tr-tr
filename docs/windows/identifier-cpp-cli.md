---
title: "__tanımlayıcı (c + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs: C++
helpviewer_keywords: __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4d68d21fc9436bff0e39fa474b97ec54138e15b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="identifier-ccli"></a>__tanımlayıcı (C++/CLI)
Visual C++ anahtar sözcükleri kullanımını tanımlayıcıları etkinleştirir.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
**Sözdizimi**  
  
```  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
**Açıklamalar**  
  
Kullanımı `__identifier` anahtar sözcükler değil tanımlayıcıları için izin verilen ancak stili sağlasa da, kesinlikle önerilmez.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnekte, adlı bir sınıf `template` C# içinde oluşturulur ve DLL olarak dağıtılmış. Kullanan Visual C++ programı `template` sınıfı, `__identifier` anahtar sözcüğü gizlendiğinden olgu, `template` standart bir C++ anahtardır.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 `__identifier` Anahtar sözcüğü ile geçerli **/CLR** derleyici seçeneği.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnekte, adlı bir sınıf `template` C# içinde oluşturulur ve DLL olarak dağıtılmış. Kullanan Visual C++ programı `template` sınıfı, `__identifier` anahtar sözcüğü gizlendiğinden olgu, `template` standart bir C++ anahtardır.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)   
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)