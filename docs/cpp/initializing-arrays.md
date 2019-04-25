---
title: Dizileri Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
ms.openlocfilehash: e055e7759865fc151176097c6f0afd9ee237f4c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183433"
---
# <a name="initializing-arrays"></a>Dizileri Başlatma

Bir sınıfın oluşturucusu varsa, bu sınıfın dizileri oluşturucu tarafından başlatılır. Başlatıcıda dizideki öğelerden daha az öğe varsa, kalan öğeler için varsayılan oluşturucu kullanılır. Sınıf için varsayılan oluşturucu tanımlanmamışsa, başlatıcı listesi eksiksiz olmalı, yani dizideki her öğe için bir başlatıcı olmalıdır.

İki oluşturucu tanımlayan `Point` sınıfını göz önünde bulundurun:

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

İlk `aPoint` öğesi `Point( int, int )` oluşturucusu kullanılarak oluşturulur; kalan iki öğe varsayılan oluşturucu kullanılarak oluşturulur.

Statik üye dizileri (olmadığını **const** veya değil) (dışında sınıf bildiriminin) tanımlarında başlatılabilir. Örneğin:

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```