---
title: "İşlev şablonları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates
- templates, function
- function templates, about function templates
ms.assetid: 59b56a4b-0689-4161-9c07-25021562e2a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 721e466e5d7e77592e66aa3ebacb3ad59eb89bb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-templates"></a>İşlev Şablonları
Sınıf şablonları, örneği oluşturulduktan sonra sınıfa geçirilen tür bağımsız değişkenlerini temel alan ilgili sınıflar ailesini tanımlar. İşlev şablonları sınıf şablonlarına benzer, ancak bir işlevler ailesi tanımlar. İşlev şablonlarıyla, aynı kodu temel alan, ancak farklı türler veya sınıflar üzerinde işlem yapan bir işlevler kümesi belirtebilirsiniz. Aşağıdaki işlev şablonu iki öğeyi birbirleriyle değiştirir:  
  
```cpp
// function_templates1.cpp  
template< class T > void MySwap( T& a, T& b ) {  
   T c(a);   
   a = b;   
   b = c;  
}  
int main() {  
}  
```  
  
 Bu kod, bir bağımsız değişkenlerin değerlerini birbirleriyle değiştiren bir işlevler ailesini tanımlar. Bu şablondan değiştireceksiniz işlevleri oluşturabilir **int** ve **uzun** türleri ve ayrıca kullanıcı tanımlı türler. `MySwap`, sınıfın kopya oluşturucu ve atama işleci düzgün bir şekilde tanımlanmışsa sınıfları bile birbirleriyle değiştirecektir.  
  
 Ayrıca, derleyici derleme zamanında `a` ve `b` parametrelerinin türlerini bildiği için işlev şablonu farklı türden nesneleri birbirleriyle değiştirmenizi önleyecektir.  
  
 Bu işlev şablonu oluşturulmamış bir işlev tarafından gerçekleştirilebilse de, şablon sürümü void işaretçileri kullanılırsa typesafe olabilir. Aşağıdaki çağrıları göz önünde bulundurun:  
  
```cpp
int j = 10;  
int k = 18;  
CString Hello = "Hello, Windows!";  
MySwap( j, k );          //OK  
MySwap( j, Hello );      //error  
```  
  
 İkinci `MySwap` çağrısı, derleyici farklı türlerden parametrelerle bir `MySwap` işlevi oluşturamadığı için bir derleme zamanı hatası tetikler. Void işaretçiler kullanıldıysa, her iki işlev çağrısı da doğru bir şekilde derlenir, ancak işlev çalışma zamanında düzgün bir şekilde çalışmaz.  
  
 Bir işlev şablonu için şablon bağımsız değişkenlerinin açık belirtimine izin verilir. Örneğin:  
  
```cpp
// function_templates2.cpp  
template<class T> void f(T) {}  
int main(int j) {  
   f<char>(j);   // Generate the specialization f(char).  
   // If not explicitly specified, f(int) would be deduced.  
}  
```  
  
 Şablon bağımsız değişkenini açıkça belirtildiğinde, işlev bağımsız değişkenini ilgili işlev şablonu parametrelerine dönüştürmek için normal örtük dönüştürmeler gerçekleştirilir. Yukarıdaki örnekte derleyici dönüştürecek `char j` yazmak için `int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şablonları](../cpp/templates-cpp.md)   
 [İşlev şablonu örneklemesi](../cpp/function-template-instantiation.md)   
 [Açık örnekleme](../cpp/explicit-instantiation.md)   
 [İşlev Şablonlarının Açık Alt Uzmanlaşması](../cpp/explicit-specialization-of-function-templates.md)
