---
title: "Özet (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs:
- C++
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b935aabeb048d955941a41f6a50735897a53009
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="abstract--c-component-extensions"></a>soyut (C++ Bileşen Uzantıları)
`abstract` Anahtar sözcüğü ya da bildirir:  
  
-   Bir tür bir taban türü kullanılabilir, ancak türü örneği oluşturulamıyor.  
  
-   Tür üye işlevi yalnızca türetilmiş bir tür tanımlanabilir.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 **Sözdizimi**  
  
```  
  
      class-declaration  
      class-identifier  
      abstract {}  
virtualreturn-typemember-function-identifier() abstract ;  
  
```  
  
 **Açıklamalar**  
  
 İlk örnek sözdizimi soyut bir sınıf bildirir. *Sınıf bildirimi* bileşeni, bir ya da bir yerel C++ bildirimi olabilir (`class` veya `struct`), ya da C++ uzantısı bildirimi (`ref class` veya `ref struct`) varsa **/ZW** veya **/CLR** derleyici seçeneği belirtildi.  
  
 İkinci örnek sözdizimi soyut için sanal üye işlevi bildirir. Bir işlev soyuttur saf sanal işlevi bildirme aynı bildirme. Üye işlevi Özet de soyut belirtilecek kapsayan sınıfı neden bildirme.  
  
 `abstract` Anahtar sözcüğü, yerel ve platforma özgü kodu desteklenir; diğer bir deyişle, onu ile veya olmadan derlenebilir **/ZW** veya **/CLR** derleyici seçeneği.  
  
 Bir tür ile soyut ise derleme zamanında algılayabilir `__is_abstract(type)` türü ayırdedici nitelik. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `abstract` Sözcüktür bağlama duyarlı geçersiz kılma tanımlayıcısı. Bağlama duyarlı anahtar sözcükler hakkında daha fazla bilgi için bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md). Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz: [nasıl yapılır: yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Daha fazla bilgi için bkz: [Ref sınıflar ve yapılar](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde bir hata oluşturur çünkü sınıf `X` işaretlenmiş `abstract`.  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneği, bir hata oluşturur, çünkü işaretlenmiş yerel bir sınıf başlatır `abstract`. Bu hata ile veya olmadan oluşacaktır **/CLR** derleyici seçeneği.  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneğinde bir hata oluşturur çünkü işlevi `f` bir tanımı içerir ancak işaretlenmiş `abstract`. Örnekte son deyim soyut bir sanal işlev bildirme saf sanal işlevi bildirmek için eşdeğer olduğunu gösterir.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)