---
title: Dizileri başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eacd447d27f3dd8bd2d2d88e6d975cdb29a82026
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="initializing-arrays"></a>Dizileri Başlatma
Bir sınıfın oluşturucusu varsa, bu sınıfın dizileri oluşturucu tarafından başlatılır. Başlatıcıda dizideki öğelerden daha az öğe varsa, kalan öğeler için varsayılan oluşturucu kullanılır. Sınıf için varsayılan oluşturucu tanımlanmamışsa, başlatıcı listesi eksiksiz olmalı, yani dizideki her öğe için bir başlatıcı olmalıdır.  
  
 İki oluşturucu tanımlayan `Point` sınıfını göz önünde bulundurun:  
  
```  
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
  
 Statik üye dizileri (olup olmadığını **const** veya değil) tanımlarını (dışında sınıf bildirimi) başlatılabilir. Örneğin:  
  
```  
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
  
