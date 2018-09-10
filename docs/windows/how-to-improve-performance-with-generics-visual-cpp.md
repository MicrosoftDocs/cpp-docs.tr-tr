---
title: 'Nasıl yapılır: (Visual C++) türlerle performansı artırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, C++
- C++, performance
- C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9f946970f78b432774a5e4c7ba20fd15a00ae654
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318532"
---
# <a name="how-to-improve-performance-with-generics-visual-c"></a>Nasıl yapılır: Genel Türlerle Performansı Artırma (Visual C++)

Genel türler ile bir tür parametresine bağlı yeniden kullanılabilir kod oluşturabilirsiniz. Gerçek türü tür parametresi, istemci kodu tarafından çağrılan kadar ertelenir. Genel türler hakkında daha fazla bilgi için bkz. [genel türler](../windows/generics-cpp-component-extensions.md).

Bu makalede, genel türler koleksiyonları kullanan bir uygulama performansını artırmaya nasıl yardımcı olabileceğini ele alınacaktır.

## <a name="example"></a>Örnek

.NET Framework, pek çok koleksiyon sınıflarını birlikte <xref:System.Collections?displayProperty=fullName> ad alanı. Bu koleksiyonların çoğu türündeki nesneler üzerinde çalışan <xref:System.Object?displayProperty=fullName>. Herhangi bir türü türetilen tüm türler bile değer türleri, .NET Framework'teki bu yana depolamak koleksiyon böylece <xref:System.Object?displayProperty=fullName>. Ancak, bu yaklaşımın iki dezavantajları vardır.

İlk olarak, tamsayılar gibi değer türleri koleksiyonu depolanıyorsa, değer koleksiyona eklenmeden önce Kutulu ve gerekir değeri koleksiyondan alındığında kutudan çıkarılır. Bu pahalı işlemlerdir.

İkinci olarak, hangi türlerin bir koleksiyona eklenebilir denetlemek için hiçbir yolu yoktur. Bu büyük olasılıkla ne hedeflenen olsa bile bir dize ve tamsayı aynı koleksiyona eklemek için mükemmel bir şekilde daha uygundur. Bu nedenle, kod tür bakımından güvenli olması için sırada koleksiyondan alınan tür gerçekten beklenen olup olmadığını denetleyin sahip.

Aşağıdaki kod örneği, genel türler önce .NET Framework koleksiyonları iki ana dezavantajları gösterilmektedir.

```cpp
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

Yeni <xref:System.Collections.Generic?displayProperty=fullName> ad alanı bulunan aynı koleksiyonları birçoğunu içerir <xref:System.Collections?displayProperty=fullName> genel tür parametreleri kabul etmek için ad alanı, ancak değiştirilmiş. Bu iki genel olmayan koleksiyon dezavantajları ortadan kaldırır: kutulama ve değer türleri ve türlerini belirtmek için yükleyememesine koleksiyonlarında depolanacak kutudan çıkarma. İki koleksiyon üzerinde işlemler aynıdır; Bunlar yalnızca nasıl bunlar örneği oluşturulur farklı.

Yukarıdaki genel kullanan bu örnek ile yazılmış örnek karşılaştırma <xref:System.Collections.Generic.Stack%601> koleksiyonu. Bu örnek performansını sık erişilen büyük koleksiyonlarda önceki örnekte önemli ölçüde daha büyük olacaktır.

```cpp
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