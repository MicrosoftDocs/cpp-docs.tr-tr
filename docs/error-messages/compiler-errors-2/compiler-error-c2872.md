---
title: "Derleyici Hatası C2872 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2872
dev_langs: C++
helpviewer_keywords: C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 03bfb79a424b1272239826abf3056a8ab6228eec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2872"></a>Derleyici Hatası C2872
'*sembol*': belirsiz simgesi  
  
Derleyici başvurduğunuz hangi sembolün belirleyemiyor. Belirtilen ada sahip birden fazla sembol kapsamıdır. Dosya konumları ve bildirimler için hata iletisini aşağıdaki notlara belirsiz simgenin bulunduğu derleyici bakın. Bu sorunu gidermek için tam olarak belirsiz simge kendi bu gibi bir durumda ad kullanarak nitelemek `std::byte` veya `::byte`. Aynı zamanda bir [ad alanı diğer adı](../../cpp/namespaces-cpp.md#namespace_aliases) kaynak kodunuzu sembolleri belirsizliği zaman dahil edilen bir ad alanı kullanım için kullanışlı kısa bir ad vermek için.  
  
C2872 üstbilgi dosyası içeriyorsa oluşabilir bir [using yönergesi](../../cpp/namespaces-cpp.md#using_directives), ve bir sonraki üst bilgi dosyasını dahil ayrıca belirtilen ad alanında bir türü içeren `using` yönergesi. Belirtin bir `using` yalnızca tüm üst bilgi dosyaları ile belirtilir sonra yönerge `#include`.  
  
 Bilgi Bankası makaleleri C2872 hakkında daha fazla bilgi için bkz: [sorun: derleyici hataları kullandığınız #import Visual C++ .NET XML ile](http://support.microsoft.com/kb/316317) ve ["hata C2872: 'Platformu': belirsiz simge" kullandığınızda hata iletisi Visual Studio 2013'te Windows::Foundation::metadata ad alanı](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2872, oluşturur ve belirsiz bir başvuruya adlı bir değişkene yapılan çünkü `i`; iki değişkenlerdir aynı ada sahip kapsamda:  
  
```cpp  
// C2872.cpp  
// compile with: cl /EHsc C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok, uses i from global namespace  
   A::i++;   // ok, uses i from namespace A  
   i++;   // C2872 ambiguous: ::i or A::i? 
   // To fix this issue, use the fully qualified name
   // for the intended variable. 
}  
```