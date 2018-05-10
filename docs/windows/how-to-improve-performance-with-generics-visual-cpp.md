---
title: 'Nasıl yapılır: genel türler (Visual C++) ile performansı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, C++
- Visual C++, performance
- Visual C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da74cce5f41c3399fb102180cfdfe8c1215c8bf9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-improve-performance-with-generics-visual-c"></a>Nasıl yapılır: Genel Türlerle Performansı Artırma (Visual C++)
Genel türler ile bir tür parametresi temelinde yeniden kullanılabilir kod oluşturabilirsiniz. Tür parametresi gerçek türü, istemci kodu tarafından adlı kadar ertelenir. Genel türler hakkında daha fazla bilgi için bkz: [genel türler](../windows/generics-cpp-component-extensions.md).  
  
 Bu makalede, genel türler koleksiyonları kullanan bir uygulama performansını artırmaya nasıl yardımcı olabileceğini ele alınacaktır.  
  
## <a name="example"></a>Örnek  
 .NET Framework içinde birçok koleksiyon sınıfları ile gelir <xref:System.Collections?displayProperty=fullName> ad alanı. Bu koleksiyonları çoğunu türündeki nesneler üzerinde çalışan <xref:System.Object?displayProperty=fullName>. Bu .NET Framework, hatta değer türleri, içindeki tüm türler türetmek beri herhangi bir türü depolamak koleksiyonları sağlar <xref:System.Object?displayProperty=fullName>. Ancak, bu yaklaşımın iki dezavantajları vardır.  
  
 İlk olarak, koleksiyon değer türleri tamsayılar gibi depolanıyorsa değeri koleksiyona eklenmeden önce Kutulu ve gerekir değeri koleksiyondan alındığında sarmalanmamış. Maliyeti yüksek işlemler şunlardır.  
  
 İkinci olarak, hangi tür bir koleksiyona eklenebilir denetlemek için bir yolu yoktur. Bu büyük olasılıkla ne tasarlanmıştır olsa bile bir tamsayı ve bir dize aynı koleksiyona eklemek için mükemmel daha uygundur. Bu nedenle, kodunuz türüne güvenli olması için sırayla koleksiyondan alınan türü gerçekten beklenen olup olmadığını denetleyin gerekir.  
  
 Aşağıdaki kod örneğinde genel türler önce .NET Framework koleksiyonların iki ana dezavantajları gösterilmektedir.  
  
```  
// perf_pre_generics.cpp  
// compile with: /clr  
  
using namespace System;  
using namespace System::Collections;  
  
int main()  
{  
    // This Stack can contain any type.  
    Stack ^s = gcnew Stack();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
  
    // Push a String to the same Stack.  
    // The Stack now contains two different data types.  
    s->Push("Seven");  
  
    // Pop the items off the Stack.  
    // The item is returned as an Object, so a cast is  
    // necessary to convert it to its proper type.  
    while (s->Count> 0)  
    {  
        Object ^o = s->Pop();  
        if (o->GetType() == Type::GetType("System.String"))  
        {  
            Console::WriteLine("Popped a String: {0}", (String ^)o);  
        }  
        else if (o->GetType() == Type::GetType("System.Int32"))  
        {  
            Console::WriteLine("Popped an int: {0}", (int)o);  
        }  
        else  
        {  
            Console::WriteLine("Popped an unknown type!");  
        }  
    }  
}  
```  
  
```Output  
Popped a String: Seven  
Popped an int: 7  
```  
  
## <a name="example"></a>Örnek  
 Yeni <xref:System.Collections.Generic?displayProperty=fullName> ad alanında bulunan aynı koleksiyonları çoğunu <xref:System.Collections?displayProperty=fullName> genel tür parametreleri kabul etmek için ad alanı, ancak bunlar değiştirildi. Bu iki genel olmayan koleksiyonları eksileri ortadan kaldırır: kutulama ve kutudan çıkarma değer türleri ve türlerini belirtme yeteneğinin koleksiyonlardaki depolanacak. İki koleksiyon üzerinde işlemler aynıdır; Bunlar yalnızca nasıl bunlar örneği oluşturulmadan içinde farklılık gösterir.  
  
 Yukarıdaki genel kullanan bu örnek ile yazılmış örnek karşılaştırmak <xref:System.Collections.Generic.Stack%601> koleksiyonu. Sık erişilen büyük koleksiyonlar üzerinde bu örnek performansını önceki örnekte önemli ölçüde daha büyük olacaktır.  
  
```  
// perf_post_generics.cpp  
// compile with: /clr  
  
#using <System.dll>  
  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main()  
{  
    // This Stack can only contain integers.  
    Stack<int> ^s = gcnew Stack<int>();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
    s->Push(14);  
  
    // You can no longer push a String to the same Stack.  
    // This will result in compile time error C2664.  
    //s->Push("Seven");  
  
    // Pop an item off the Stack.  
    // The item is returned as the type of the collection, so no  
    // casting is necessary and no unboxing is performed for  
    // value types.  
    int i = s->Pop();  
    Console::WriteLine(i);  
  
    // You can no longer retrieve a String from the Stack.  
    // This will result in compile time error C2440.  
    //String ^str = s->Pop();  
}  
```  
  
```Output  
14  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](../windows/generics-cpp-component-extensions.md)