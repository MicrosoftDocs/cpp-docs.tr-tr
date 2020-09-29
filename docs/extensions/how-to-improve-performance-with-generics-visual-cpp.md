---
title: 'Nasıl yapılır: Genel Türlerle Performansı Artırma (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- performance, C++
- C++, performance
- C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
ms.openlocfilehash: 039c5b069351249e51d961d9d1757ed6b09ef99c
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414171"
---
# <a name="how-to-improve-performance-with-generics-ccli"></a>Nasıl yapılır: Genel Türlerle Performansı Artırma (C++/CLI)

Genel türler ile, bir tür parametresine bağlı olarak yeniden kullanılabilir kod oluşturabilirsiniz. Tür parametresinin gerçek türü, istemci kodu tarafından çağrılana kadar ertelenir. Genel türler hakkında daha fazla bilgi için bkz. [Genel türler](generics-cpp-component-extensions.md).

Bu makalede, genel türlerin koleksiyonlar kullanan bir uygulamanın performansını artırmaya nasıl yardımcı olduğu ele alınmaktadır.

## <a name="example-two-main-drawbacks-of-net-framework-collections"></a>Örnek: .NET Framework koleksiyonlarının Iki ana sakıncaları

.NET Framework, ad alanındaki birçok koleksiyon sınıfıyla birlikte gelir <xref:System.Collections?displayProperty=fullName> . Bu koleksiyonların çoğu türündeki nesneler üzerinde çalışır <xref:System.Object?displayProperty=fullName> . Bu, koleksiyon.NET Framework lardaki tüm türler, hatta değer türleri, öğesinden türetildiklerinden, koleksiyonların herhangi bir tür depolamasına izin verir <xref:System.Object?displayProperty=fullName> . Ancak, bu yaklaşımın iki Sakıncaı vardır.

İlk olarak, koleksiyon tamsayılar gibi değer türlerini depoladığında, değer koleksiyona eklenmeden önce paketlenmeli ve değer koleksiyondan alındıktan sonra kutulanmamış olmalıdır. Bunlar pahalı işlemlerdir.

İkincisi, bir koleksiyona hangi türlerin eklenebileceği kontrol etmenin bir yolu yoktur. Büyük olasılıkla amaçlanan gibi olmasa da, aynı koleksiyona bir tamsayı ve bir dize eklemek mükemmel bir şeydir. Bu nedenle, kodunuzun güvenli olması için, koleksiyondan alınan türün gerçekten beklenen şeydir olduğunu denetlemeniz gerekir.

Aşağıdaki kod örneği, genel türler öncesinde .NET Framework koleksiyonlarının iki ana dezavantajın gösterir.

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

## <a name="example-benefit-of-using-generic-collection"></a>Örnek: genel koleksiyon kullanmanın avantajı

Yeni ad alanı, <xref:System.Collections.Generic?displayProperty=fullName> ad alanında bulunan birçok koleksiyonu içerir <xref:System.Collections?displayProperty=fullName> , ancak genel tür parametrelerini kabul edecek şekilde değiştirilmiştir. Bu, genel olmayan koleksiyonların iki dezavantajunu ortadan kaldırır: değer türlerinin kutulama ve kutudan çıkarma ve koleksiyonlarda depolanacak türleri belirtmeme. İki koleksiyon üzerindeki işlemler aynıdır; Bunlar yalnızca nasıl örneklendikleri gibi farklılık gösterir.

Yukarıda yazılmış örneği, genel bir koleksiyon kullanan bu örnekle karşılaştırın <xref:System.Collections.Generic.Stack%601> . Sık erişilen büyük koleksiyonlarda, bu örneğin performansı önceki örnekten önemli ölçüde daha büyük olacaktır.

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

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
