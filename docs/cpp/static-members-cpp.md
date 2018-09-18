---
title: Statik üyeleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class members [C++], static
- instance constructors, static members
- class members [C++], shared
- members [C++], static data members
- static members [C++], data members
- static data members [C++]
- data members [C++], static data members
- class instances [C++], shared members
- instance constructors, shared members
- class instances [C++], static members
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fba58883db0f5936a8f3dedc1e0c4a19fb0aafa9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086206"
---
# <a name="static-members-c"></a>Statik Üyeler [C++]

Sınıflar, statik üye verileri ve üye işlevleri içerebilir. Ne zaman veri üyesi olarak bildirilen **statik**, sınıfın tüm nesneleri için verileri yalnızca bir kopyası saklanır.

Statik veri üyeleri, belirli bir sınıf türü nesneleri bir parçası değildir. Sonuç olarak, bir statik veri üyesi bildirimi bir tanım dikkate alınmaz. Veri üyesi, sınıf kapsamında bildirilen, ancak tanımı dosya kapsamında gerçekleştirilir. Bu statik üyeleri dış bağlantısı vardır. Aşağıdaki örnek bunu göstermektedir:

```cpp
// static_data_members.cpp
class BufferedOutput
{
public:
   // Return number of bytes written by any object of this class.
   short BytesWritten()
   {
      return bytecount;
   }

   // Reset the counter.
   static void ResetCount()
   {
      bytecount = 0;
   }

   // Static member declaration.
   static long bytecount;
};

// Define bytecount in file scope.
long BufferedOutput::bytecount;

int main()
{
}
```

Önceki kodda, üye `bytecount` sınıfta bildirilen `BufferedOutput`, ancak sınıf bildirimi dışında tanımlanmış olması gerekir.

Statik veri üyeleri, sınıf türünden bir nesneye başvuruda bulunmadan bulunulabilir. Kullanılarak yazılan bayt sayısı `BufferedOutput` nesneleri gibi edinilebilir:

```cpp
long nBytes = BufferedOutput::bytecount;
```

Statik üye var sınıf türünün herhangi bir nesne bulunduğunu gerekli değildir. Statik üyeleri de erişilebilir kullanarak üye seçimi (**.** ve **->**) işleçleri. Örneğin:

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

Yukarıdaki durumda, bir nesneye başvuru (`Console`) değerlendirilmez; döndürülen değer statik nesne olan `bytecount`.

Statik veri üyeleri sınıf üyesine erişim kurallarına tabidir olduğundan statik veri üyeleri için özel erişim yalnızca sınıf üyesi işlevleri ve arkadaş için izin verilir. Bu kurallar, şurada açıklanan [üye erişim denetimi](../cpp/member-access-control-cpp.md). Bu statik veri üyeleri kendi erişim kısıtlamaları bağımsız olarak dosya kapsamı tanımlanmalıdır istisnadır. Açıkça başlatılması için veri üyesi ise, bir başlatıcı tanımıyla sağlanmalıdır.

Statik bir üyenin türü ve sınıf adıyla yeterli değil. Bu nedenle, türü `BufferedOutput::bytecount` olduğu **uzun**.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)