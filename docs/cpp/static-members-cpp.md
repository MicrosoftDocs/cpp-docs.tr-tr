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
ms.openlocfilehash: b79b65ab3cbf4565f31ad6717f8163c678697c9c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213196"
---
# <a name="static-members-c"></a>Statik Üyeler [C++]

Sınıflar statik üye verisi ve üye işlevleri içerebilir. Bir veri üyesi olarak bildirildiğinde **`static`** , sınıfın tüm nesneleri için verilerin yalnızca bir kopyası korunur.

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

Önceki kodda, üye `bytecount` sınıfında bildirildiği `BufferedOutput` , ancak sınıf bildiriminin dışında tanımlanmalıdır.

Statik veri üyelerine, sınıf türündeki bir nesneye başvurulmadan başvurulabilir. Nesneleri kullanarak yazılan bayt sayısı `BufferedOutput` aşağıdaki şekilde elde edilebilir:

```cpp
long nBytes = BufferedOutput::bytecount;
```

Statik üyenin mevcut olması için, sınıf türündeki nesnelerin mevcut olması gerekmez. Statik üyelere Ayrıca üye seçimi (**.** ve **->** ) işleçlerini. Örnek:

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

Önceki durumda, nesnesine başvuru ( `Console` ) değerlendirilmez; döndürülen değer statik nesnenin değeridir `bytecount` .

Statik veri üyeleri sınıf üye erişim kurallarına tabidir, bu nedenle statik veri üyelerine özel erişime yalnızca sınıf üyesi işlevleri ve arkadaşlar için izin verilir. Bu kurallar [üye Access Control](../cpp/member-access-control-cpp.md)açıklanmaktadır. Özel durum, statik veri üyelerinin, erişim kısıtlamalarından bağımsız olarak dosya kapsamında tanımlanması gerekir. Veri üyesinin Açık olarak başlatılması gerekiyorsa, tanımıyla birlikte bir başlatıcısının sağlanması gerekir.

Statik üyenin türü, sınıf adı tarafından nitelendirilmez. Bu nedenle, türü `BufferedOutput::bytecount` **`long`** .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../cpp/classes-and-structs-cpp.md)
