---
title: Statik Üyeler [C++]
ms.date: 11/04/2016
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
ms.openlocfilehash: c18b29cf69c2f899fbf06c7cb75ebbd2242ab427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178567"
---
# <a name="static-members-c"></a>Statik Üyeler [C++]

Sınıflar statik üye verisi ve üye işlevleri içerebilir. Bir veri üyesi **statik**olarak bildirildiğinde, sınıfın tüm nesneleri için verilerin yalnızca bir kopyası korunur.

Statik veri üyeleri, belirli bir sınıf türünün nesnelerinin bir parçası değildir. Sonuç olarak, bir statik veri üyesinin bildirimi tanım olarak kabul edilmez. Veri üyesi sınıf kapsamında bildiriliyor, ancak tanım dosya kapsamında yapılır. Bu statik üyelerin dış bağlantısı vardır. Aşağıdaki örnekte bu gösterilmektedir:

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

Yukarıdaki kodda, üye `bytecount` sınıf `BufferedOutput`olarak bildirildiği halde sınıf bildiriminin dışında tanımlanmalıdır.

Statik veri üyelerine, sınıf türündeki bir nesneye başvurulmadan başvurulabilir. `BufferedOutput` nesneleri kullanılarak yazılan bayt sayısı aşağıdaki şekilde elde edilebilir:

```cpp
long nBytes = BufferedOutput::bytecount;
```

Statik üyenin mevcut olması için, sınıf türündeki nesnelerin mevcut olması gerekmez. Statik üyelere Ayrıca üye seçimi ( **.** ve **->** ) işleçleri. Örneğin:

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

Önceki durumda, nesnesine başvuru (`Console`) değerlendirilmez; döndürülen değer `bytecount`statik nesne.

Statik veri üyeleri sınıf üye erişim kurallarına tabidir, bu nedenle statik veri üyelerine özel erişime yalnızca sınıf üyesi işlevleri ve arkadaşlar için izin verilir. Bu kurallar [üye Access Control](../cpp/member-access-control-cpp.md)açıklanmaktadır. Özel durum, statik veri üyelerinin, erişim kısıtlamalarından bağımsız olarak dosya kapsamında tanımlanması gerekir. Veri üyesinin Açık olarak başlatılması gerekiyorsa, tanımıyla birlikte bir başlatıcısının sağlanması gerekir.

Statik üyenin türü, sınıf adı tarafından nitelendirilmez. Bu nedenle `BufferedOutput::bytecount` türü **uzun**olur.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
