---
title: "Başvurular (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4178d9d6a48e10510bb739bc2e1a55ecbe2714e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="references-c"></a>Başvurular (C++)
Bir işaretçi aşağıdakine benzer bir başvuru bellekte bir başka bir yerde bulunan nesnenin adresini depolar. Bir işaretçi başlatıldıktan sonra bir başvuru ayarlayın ya da farklı bir nesneye başvuruda kurulamıyor null. Başvuruları iki tür vardır: başvuran bir adlandırılmış değişken ve rvalue başvuru başvuran lvalue başvuru bir [geçici nesne](../cpp/temporary-objects.md). & İşleci güveninin lvalue başvuru ve & & işleci rvalue başvuru veya bağlam bağlı olarak Evrensel başvurusu (rvalue veya lvalue) olduğunu belirtir.  
  
 Aşağıdaki sözdizimini kullanarak başvurular bildirilen:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 Bir başvuru belirterek herhangi bir geçerli bildirimcisi kullanılabilir. Başvuru işlevi veya dizi türü bir başvuru değilse, aşağıdaki Basitleştirilmiş söz dizimi geçerlidir:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 Başvuruları aşağıdaki dizisi kullanılarak bildirilen:  
  
 1. Bildirim tanımlayıcıları:  
  
-   İsteğe bağlı bir depolama sınıfı tanımlayıcısı.  
  
-   İsteğe bağlı **const** ve/veya `volatile` niteleyicileri.  
  
-   Tür tanımlayıcısı: bir türünün adı.  
  
-   2. Bildirimcisi:  
  
-   Bir isteğe bağlı Microsoft belirli değiştiricisi. Daha fazla bilgi için bkz: [Microsoft'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).  
  
-   & İşleci veya & & işleci.  
  
-   İsteğe bağlı **const** ve/veya `volatile` qualifers.  
  
-   Tanımlayıcı.  
  
 3. İsteğe bağlı bir başlatıcı.  
  
 Daha karmaşık bildirimcisi forms dizileri ve işlev işaretçileri dizileri ve İşlevler, başvuruları da uygulamak için bkz: [işaretçileri](../cpp/pointers-cpp.md) ve [Bildirimciler](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
 Birden çok bildirimler ve başlatıcılar tek bildirimi belirleyici aşağıdaki virgülle ayrılmış bir listede görünebilir. Örneğin:  
  
```  
int &i;   
int &i, &j;   
```  
  
 Başvurular, işaretçiler ve nesnelerin araya bildirilen:  
  
```  
int &ref, *ptr, k;   
```  
  
 Bir başvuru nesnenin adresini tutar ancak sözdizimsel olarak bir nesne gibi davranır.  
  
 Aşağıdaki programında dikkat nesnesinin adını `Today`ve nesne başvurusunu `TodayRef`, aynı programlarda kullanılabilir:  
  
## <a name="example"></a>Örnek  
  
```  
// references.cpp  
#include <stdio.h>  
struct S {  
   short i;  
};  
  
int main() {  
   S  s;   // Declare the object.  
   S& SRef = s;   // Declare the reference.  
   s.i = 3;  
  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
  
   SRef.i = 4;  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
}  
```  
  
```Output  
3  
3  
4  
4  
```  
  
## <a name="comment"></a>Yorum  
 Bu bölümdeki konular:  
  
-   [Başvuru türü işlev bağımsız değişkenleri](../cpp/reference-type-function-arguments.md)  
  
-   [Başvuru türü işlev dönüşleri](../cpp/reference-type-function-returns.md)  
  
-   [İşaretçi başvuruları](../cpp/references-to-pointers.md)  
  
