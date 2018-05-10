---
title: Platform, varsayılan ve cli ad alanları (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- lang
- cli
dev_langs:
- C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b466a94aba9f19907a5438a8b8e623d65aa0ac2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="platform-default-and-cli-namespaces--c-component-extensions"></a>Platform, varsayılan ve cli Ad Alanları (C++ Bileşen Uzantıları)
Bir ad alanı dil öğelerinin adlarını kaynak kod içindeki başka bir yerde benzer adlarla çakışmamaları için örtük olarak nitelendirir. Örneğin, bir ad çakışması derleyici tanımasını engel olabilecek [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md). Ad alanları derleyici tarafından kullanılır, ancak oluşturulmuş derlemede korunmaz.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Visual C++, projeyi oluşturduğunuzda projeniz için varsayılan bir ad alanı sağlar. Windows çalışma zamanı .winmd dosyasının adı kök ad alanı eşleşmesi gerekse de ad el ile yeniden adlandırabilirsiniz.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Daha fazla bilgi için bkz: [ad alanları ve türü görünürlük (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Sözdizimi**  
  
```  
using namespace cli;  
```  
  
 **Açıklamalar**  
  
 C + +/ CLI destekleyen `cli` ad alanı. İle derleme yapılırken **/CLR**, `using` deyimi sözdizimi bölümünde kapsanan.  
  
 Aşağıdaki dil özellikleri bulunan `cli` ad alanı:  
  
-   [Diziler](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde dosyasındaki bir simge kullanmak da mümkündür gösterilmektedir `cli` kodunuzu kullanıcı tanımlı sembol olarak ad alanı.  Ancak, bunu yaptıktan sonra başvurular açıkça veya örtük nitelemek gerekecek `cli` language öğesi aynı ada sahip.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)