---
description: 'Daha fazla bilgi edinin: Işlev şablonları'
title: İşlev Şablonları
ms.date: 07/15/2019
helpviewer_keywords:
- function templates
- templates, function
- function templates, about function templates
ms.assetid: 59b56a4b-0689-4161-9c07-25021562e2a7
ms.openlocfilehash: f64041e2fdd8b9acc30a4f71e445d9f73bb7db37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341392"
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

Bu kod, bir bağımsız değişkenlerin değerlerini birbirleriyle değiştiren bir işlevler ailesini tanımlar. Bu şablondan, ve **`int`** **`long`** türlerini ve Kullanıcı tanımlı türleri de takamayacak işlevler oluşturabilirsiniz. `MySwap`, sınıfın kopya oluşturucu ve atama işleci düzgün bir şekilde tanımlanmışsa sınıfları bile birbirleriyle değiştirecektir.

Buna ek olarak, derleyici derleme zamanında *a* ve *b* parametrelerinin türlerini bildiğinden, işlev şablonu farklı türlerdeki nesneleri değiştirmeyi engeller.

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

Şablon bağımsız değişkenini açıkça belirtildiğinde, işlev bağımsız değişkenini ilgili işlev şablonu parametrelerine dönüştürmek için normal örtük dönüştürmeler gerçekleştirilir. Yukarıdaki örnekte, derleyici `j` türüne dönüştürülür **`char`** .

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../cpp/templates-cpp.md)<br/>
[İşlev şablonu örneklemesi](../cpp/function-template-instantiation.md)<br/>
[Açık örnek oluşturma](../cpp/explicit-instantiation.md)<br/>
[Işlev şablonlarının açık özelleştirmesi](../cpp/explicit-specialization-of-function-templates.md)
