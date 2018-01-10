---
title: "nullptr (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be7fcc147a5f6f4b96f7bf7dd68376613489946c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nullptr--c-component-extensions"></a>nullptr (C++ Bileşen Uzantıları)
`nullptr` Anahtar sözcüğü temsil eden bir *null işaretçi değeri*. Boş işaretçi değeri bir nesneye bir nesne tanıtıcısı, iç işaretçi veya yerel işaretçi türü göstermiyor belirtmek için kullanın.  
  
 Kullanım `nullptr` yönetilen veya özgün kod ile. Derleyici yönetilen ve yerel null işaretçinin değerleri için uygun ancak farklı yönergeleri yayar. ISO standart C++ sürümü bu anahtar sözcük kullanma hakkında daha fazla bilgi için bkz: [nullptr](../cpp/nullptr.md).  
  
 `__nullptr` Sözcüktür aynı anlamı taşır Microsoft'a özgü anahtar sözcüğü `nullptr`, ancak yalnızca yerel koda geçerlidir. Kullanırsanız `nullptr` ile yerel C/C++ kod ve ile derleme [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği derleyici belirleyemiyor olup olmadığını `nullptr` yerel veya yönetilen null işaretçinin değeri gösterir. Derleyicinin temizleyin, amacınız yapmak için kullanın `nullptr` yönetilen bir değer belirtmek için veya `__nullptr` yerel bir değer belirtebilirsiniz.  
  
 `nullptr` Anahtar sözcüğü eşdeğerdir `Nothing` Visual Basic'te ve `null` C#.  
  
## <a name="usage"></a>Kullanım  
 `nullptr` Anahtar sözcüğü tanıtıcısı, yerel işaretçiden veya işlev bağımsız değişkeni kullanılabilir herhangi bir yerde kullanılabilir.  
  
 `nullptr` Anahtar sözcüğü bir tür değil ve ile kullanım için desteklenmez:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [TypeId](../cpp/typeid-operator.md)  
  
-   `throw nullptr`(ancak `throw (Object^)nullptr;` çalışır)  
  
 `nullptr` Anahtar sözcüğünü aşağıdaki İşaretçi türlerinin başlatma kullanılabilir:  
  
-   Yerel işaretçi  
  
-   Windows çalışma zamanı tanıtıcısı  
  
-   Yönetilen işleyici  
  
-   Yönetilen iç işaretçi  
  
 `nullptr` Anahtar sözcüğü, başvuru kullanılmadan önce bir işaretçi veya tanıtıcı başvurusu null ise test etmek için kullanılabilir.  
  
 İşlev çağrıları hata denetimi için null işaretçinin değerleri kullanan diller arasında doğru yorumlanması.  
  
 Sıfır için tanıtıcı başlatamıyor; yalnızca `nullptr` kullanılabilir. Bir nesneyi işlemek için sabit 0 atama üreten bir kutu `Int32` ve bir cast `Object^`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösteren `nullptr` anahtar sözcüğü bir tanıtıcı olduğunda, yerel işaretçiden kullanılabilir veya işlev bağımsız değişkeni kullanılabilir. Ve örnek gösteren `nullptr` anahtar sözcüğü, kullanılmadan önce bir başvuru denetlemek için kullanılabilir.  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## <a name="example"></a>Örnek  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `nullptr` ve sıfır kullanılabilir birbirinin yerine yerel işaretçilerde.  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **Output**  
  
```Output  
pMyClass == nullptr  
  
pMyClass == 0  
  
pMyClass == nullptr  
  
pMyClass == 0  
```  
  
## <a name="example"></a>Örnek  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `nullptr` herhangi bir tür için bir tanıtıcı veya herhangi bir tür için yerel bir işaretçi olarak yorumlanır. İşlev tanıtıcıları farklı türlere sahip olması durumunda aşırı yüklemesi, bir belirsizlik hata oluşturulur. `nullptr` Açıkça bir türe etmesi gerekir.  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## <a name="example"></a>Örnek  
 **Örnek**  
  
 Aşağıdaki kod örneği, atama gösterir `nullptr` izin verilir ve bir işaretçi veya tanıtıcı içeren cast türü döndürür `nullptr` değeri.  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## <a name="example"></a>Örnek  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `nullptr` işlevi parametre olarak kullanılabilir.  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **Output**  
  
```Output  
test  
```  
  
## <a name="example"></a>Örnek  
 **Örnek**  
  
 Aşağıdaki kod örneğinde tanıtıcıları bildirilir ve açıkça başlatıldı, bunlar için başlatılan varsayılan olduğunu gösteren `nullptr`.  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **Output**  
  
```Output  
NULL  
```  
  
## <a name="example"></a>Örnek  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `nullptr` ile derlerken için yerel bir işaretçi atanabilir **/CLR**.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: (gerekli; dahil olmak üzere tüm kod oluşturma seçenekleri tarafından desteklenen **/ZW** ve **/CLR**)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)