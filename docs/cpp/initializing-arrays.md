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
ms.openlocfilehash: e1ecb15cfc34ec518f46474497a3577a51b00c4e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408577"
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