---
title: "sizeof işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: sizeof_cpp
dev_langs: C++
helpviewer_keywords: sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 244af2a6afe87757c6a242c8a750f1bc3c99e557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sizeof-operator"></a>sizeof İşleci
Kendi işleneninin türü boyutuna göre boyutu ortaya çıkarır `char`.  
  
> [!NOTE]
>  Hakkında bilgi için `sizeof ...` işleci, bkz: [üç nokta ve Variadic şablonları](../cpp/ellipses-and-variadic-templates.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sonucu `sizeof` işlecidir türü `size_t`, tanımlanan içerme dosyası STDDEF tamsayı türü. H. Bu işleç, makine bağımlı veri boyutları programlarınıza belirtmekten kaçının olanak sağlar.  
  
 İşlenenin `sizeof` şunlardan biri olabilir:  
  
-   Tür adı. Kullanılacak `sizeof` bir tür adıyla adı parantez içine alınmalıdır.  
  
-   Bir ifade. Bir ifade ile kullanıldığında `sizeof` ile veya parantezler olmadan belirtilebilir. İfade değerlendirilmez.  
  
 Zaman `sizeof` işleci türünde bir nesneye uygulanan `char`, 1 verir. Zaman `sizeof` işleci için bir dizi uygulandığında, bu diziyi değil dizi tanımlayıcı tarafından gösterilen işaretçi boyutunu bayt toplam sayısını verir. Dizi tanımlayıcı tarafından gösterilen işaretçi boyutunu elde etmek için bu parametre olarak kullanan bir işleve geçirme `sizeof`. Örneğin:  
  
## <a name="example"></a>Örnek  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Zaman `sizeof` işleci uygulanan bir `class`, `struct`, veya `union` türü, sonuç bu türdeki bir nesne bayt sayısıdır. artı word sınırları üyelerinde hizalamak için herhangi bir doldurmaya eklendi. Sonuç mutlaka tek tek üyeleri depolama gereksinimlerini ekleyerek hesaplanan boyutu karşılık gelmiyor. [/Zp](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ve [paketi](../preprocessor/pack.md) pragma üyeleri için hizalama sınırları etkiler.  
  
 `sizeof` İşleci hiçbir zaman boş bir sınıf için bile 0 verir.  
  
 `sizeof` İşleci aşağıdaki işlenenleri ile birlikte kullanılamaz:  
  
-   İşlevler. (Ancak, `sizeof` işlev işaretçileri uygulanır.)  
  
-   Bit alanları.  
  
-   Tanımsız sınıflar.  
  
-   Türü `void`.  
  
-   Dinamik olarak ayrılan diziler.  
  
-   Dış diziler.  
  
-   Eksik türler.  
  
-   Eksik türler parantez içine alınmış adları.  
  
 Zaman `sizeof` işleci başvuru uygulandığında, sonuç aynıdır gibi `sizeof` nesneye uygulanır.  
  
 Boyutsuz bir dizi bir yapının son öğesi ise, `sizeof` işleci dizi olmadan yapının boyutunu döndürür.  
  
 `sizeof` İşleci genellikle biçiminde bir ifade kullanarak bir dizide öğe sayısını hesaplamak için kullanılır:  
  
```  
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)