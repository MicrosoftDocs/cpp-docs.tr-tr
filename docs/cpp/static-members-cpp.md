---
title: Statik üyeler (C++) | Microsoft Docs
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
ms.openlocfilehash: ca75d2e54c951e20de842b984f8619dc6639dc00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32421077"
---
# <a name="static-members-c"></a>Statik Üyeler [C++]
Sınıfları, statik üye verilerini ve üye işlevleri içerebilir. Ne zaman veri üyesi bildirilen olarak **statik**, verilerin yalnızca bir kopyasını sınıfın tüm nesneleri için saklanır.
  
 Statik veri üyeleri verilen sınıf türü nesneleri parçası değildir. Sonuç olarak, bir statik veri üyesi bildirimi bir tanımını dikkate alınmaz. Veri üyesi sınıfı kapsamda bildirilmiş ancak tanım dosyası kapsamda gerçekleştirilir. Bu statik üyeleri dış bağlantı vardır. Aşağıdaki örnekte bu gösterilmektedir:  
  
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
  
 Önceki kodda, üye `bytecount` sınıfında tanımlanan `BufferedOutput`, ancak sınıf bildiriminin dışında tanımlanmış olması gerekir.  
  
 Statik veri üyeleri için bir sınıf türü nesneye başvuran olmadan belirtilebilir. Kullanılarak yazılan bayt sayısı `BufferedOutput` nesneleri gibi edinilebilir:  
  
```cpp  
long nBytes = BufferedOutput::bytecount;  
```  
  
 Statik üye bulunmasını sınıf türü herhangi bir nesne var olduğundan gerekli değildir. Statik üyeler da erişilebilir üye seçimi kullanarak (**.** ve **->**) işleçler. Örneğin:  
  
```cpp  
BufferedOutput Console;  
  
long nBytes = Console.bytecount;  
```  
  
 Önceki durumda, nesne başvurusunu (`Console`) değerlendirilmez; statik nesnesinin döndürülen değer olan `bytecount`.  
  
 Statik veri üyeleri için özel erişim yalnızca sınıf üyesi işlevleri ve arkadaş izin statik veri üyeleri sınıf üyesi erişim tabi, kurallardır. Bu kurallar açıklanan [üye erişim denetimi](../cpp/member-access-control-cpp.md). Bu statik veri üyeleri dosya kapsamı bunların erişim kısıtlamaları bağımsız olarak tanımlanmalıdır istisnadır. Açıkça başlatılması için veri üyesi ise, bir başlatıcı tanımıyla sağlanmalıdır.  
  
 Statik üye türü sınıfı adıyla yeterli değil. Bu nedenle, türü `BufferedOutput::bytecount` olan `long`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)