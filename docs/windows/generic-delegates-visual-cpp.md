---
title: Genel temsilciler (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5e1635afb2c11dbb7835244eae776fabdaea9c0
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="generic-delegates-visual-c"></a>Genel Temsilciler (Visual C++)
Genel tür parametreleri ile temsilcileri kullanabilirsiniz. Temsilciler üzerinde daha fazla bilgi için bkz: [temsilci (C++ bileşen uzantıları)](../windows/delegate-cpp-component-extensions.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[attributes]   
generic < [class | typename] type-parameter-identifiers>  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `attributes` (İsteğe bağlı)  
 Ek tanımlayıcı bilgiler. Öznitelikleri özniteliklerinin ve öznitelik sınıfları hakkında daha fazla bilgi için bkz.  
  
 *type-parameter-identifier(s)*  
 Tür parametreleri için tanımlayıcıları virgülle ayrılmış listesi.  
  
 `type-parameter-constraints-clauses`  
 Belirtilen formundadır [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *erişilebilirlik değiştiricileri* (isteğe bağlı)  
 Erişilebilirlik değiştiricileri (örneğin **ortak**, `private`).  
  
 *Sonuç türü*  
 Temsilci dönüş türü.  
  
 *identifier*  
 Temsilci adı.  
  
 *Resmi parametreleri* (isteğe bağlı)  
 Temsilci parametre listesi.  
  
## <a name="example"></a>Örnek  
 Temsilci türü parametreler temsilci nesne oluşturulduğu noktada belirtildi. Temsilci ve onunla ilişkili yöntemi aynı imzaya sahip olmalıdır. Genel temsilci bildirim bir örnek verilmiştir.  
  
```  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic <class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek gösterir  
  
-   Farklı oluşturulan türleriyle aynı temsilci nesnesini kullanamazsınız. Nesneler farklı türleri için farklı temsilci oluşturun.  
  
-   Genel temsilci ile genel yöntem ilişkili olabilir.  
  
-   Tür bağımsız değişkenleri belirtmeden genel yöntem çağrıldığında derleyici arama için tür bağımsız değişkenleri olarak Infer dener.  
  
```  
// generics_generic_delegate2.cpp  
// compile with: /clr  
generic <class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
  
generic <class ItemType>  
ref struct MyGenClass {  
   ItemType MyMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
ref struct MyClass {  
   generic <class ItemType>  
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
int main() {  
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();  
   GenDelegate<int>^ myDelegate1 =  
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   GenDelegate<double>^ myDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   GenDelegate<int>^ myDelegate =  
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, genel bir temsilci bildirir `GenDelegate<ItemType>`ve yönteme ilişkilendirerek başlatır `MyMethod` tür parametresi kullanan `ItemType`. (Bir tamsayı ve bir double) temsilci iki örneği oluşturulur ve çağrılır.  
  
```  
// generics_generic_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare generic delegate  
generic <typename ItemType>  
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);  
  
// Declare a generic class:  
generic <typename ItemType>  
ref class MyGenClass {  
public:  
   ItemType MyMethod(ItemType p1, ItemType% p2) {  
      p2 = p1;  
      return p1;  
    }  
};  
  
int main() {  
   int i = 0, j = 0;   
   double m = 0.0, n = 0.0;  
  
   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();   
  
   // Instantiate a delegate using int.  
   GenDelegate<int>^ MyDelegate1 =   
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   i = MyDelegate1(123, j);  
  
   Console::WriteLine(  
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);  
  
   // Instantiate a delegate using double.  
   GenDelegate<double>^ MyDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   m = MyDelegate2(0.123, n);  
  
   Console::WriteLine(  
      "Invoking the double delegate: m = {0}, n = {1}", m, n);  
}  
```  
  
```Output  
Invoking the integer delegate: i = 123, j = 123  
Invoking the double delegate: m = 0.123, n = 0.123  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](../windows/generics-cpp-component-extensions.md)