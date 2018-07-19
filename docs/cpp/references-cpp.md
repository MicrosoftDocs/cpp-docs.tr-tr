---
title: Başvurular (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 174ab622b177766a33dd55f6b3c78ac38c26ded1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956599"
---
# <a name="references-c"></a>Başvurular (C++)
Bir işaretçi gibi bir başvuru bellekte başka bir yerde bulunan bir nesnenin adresini depolar. Bir işaretçi, başlatıldıktan sonra bir başvuru ayarlayın veya farklı bir nesneye başvurmak için yapılabilir duruma getirilemediğinden null. Başvuruları iki tür vardır: başvuran bir adlandırılmış değişkeni ve rvalue başvuruları başvuran lvalue başvuruları bir [geçici nesne](../cpp/temporary-objects.md). & İşleci, bir lvalue başvurusuna gösterir ve & & işlecini bir rvalue başvurusuna veya bağlama Evrensel başvurusu (rvalue veya lvalue) gösterir.  
  
 Başvuruları aşağıdaki sözdizimi kullanılarak bildirilebilir:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 Bir başvuru belirterek herhangi bir geçerli bildirimci kullanılabilir. Aşağıdaki Basitleştirilmiş söz dizimi, işlev veya dizi türü bir başvuru başvuru olmadığı sürece, geçerlidir:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 Başvuruları, aşağıdaki dizi kullanılarak bildirilir:  
  
 1. Bildirim tanımlayıcıları:  
  
-   İsteğe bağlı bir depolama sınıfı tanımlayıcısı.  
  
-   İsteğe bağlı **const** ve/veya **geçici** niteleyicileri.  
  
-   Tür belirticisi: bir tür adı.  
  
-   2. Bildirimci:  
  
-   Bir isteğe bağlı Microsoft'a özgü değiştirici. Daha fazla bilgi için [Microsoft'a özel değiştiriciler](../cpp/microsoft-specific-modifiers.md).  
  
-   & İşleci veya & & işleci.  
  
-   İsteğe bağlı **const** ve/veya **geçici** qualifers.  
  
-   Tanımlayıcı.  
  
 3. İsteğe bağlı bir başlatıcı.  
  
 Dizi ve işlev işaretçileri diziler ve İşlevler, başvurular için de geçerlidir. daha karmaşık bildirimci forms bakın [işaretçileri](../cpp/pointers-cpp.md).  
  
 Birden çok Bildirimciler ve başlatıcıları bir tek bir bildirim belirticisidir aşağıdaki virgülle ayrılmış bir listede görünebilir. Örneğin:  
  
```cpp 
int &i;   
int &i, &j;   
```  
  
 Başvurular, işaretçiler ve nesneleri birlikte bildirilebilir:  
  
```cpp 
int &ref, *ptr, k;   
```  
  
 Bir başvuru tutan bir nesnenin adresini ancak sözdizimsel olarak bir nesne gibi davranır.  
  
 Aşağıdaki programın dikkat nesnesinin adını `Today`ve nesneye başvuru `TodayRef`, aynı şekilde programlar kullanılabilir:  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
-   [Başvuru Türü İşlev Bağımsız Değişkenleri](../cpp/reference-type-function-arguments.md)  
  
-   [Başvuru Türü İşlev Dönüşleri](../cpp/reference-type-function-returns.md)  
  
-   [İşaretçi Başvuruları](../cpp/references-to-pointers.md)  
  
