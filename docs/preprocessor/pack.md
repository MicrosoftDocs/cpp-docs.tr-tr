---
title: Paketi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pack_CPP
- vc-pragma.pack
dev_langs: C++
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bf4c7a67abe03a1138eb2eb016426675c20355c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pack"></a>pack
Yapısı, union ve sınıf üyeleri için paket hizalamasını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sınıf paketlemek için üyeleri doğrudan diğer bazı veya tüm üyeleri varsayılan hizalama hedef mimari küçük bir sınırında hizalanabilir anlamına gelebilir bellekte sonra yerleştirmektir. `pack`veri bildirimi düzeyinde denetim sağlar. Bu derleyici seçeneği farklıdır [/Zp](../build/reference/zp-struct-member-alignment.md), hangi yalnızca modülü düzey denetim sağlar. `pack`ilk başta etkisi alır `struct`, `union`, veya `class` pragma görülen sonra bildirimi. `pack`tanımları üzerinde hiçbir etkisi yoktur. Çağırma `pack` hiçbir bağımsız değişkenleri kümeleriyle `n` derleyici seçeneğinde ayarlı değerine **/Zp**. Derleyici seçeneği ayarlanmazsa, varsayılan değer 8'dir.  
  
 Bir yapı hizalama değiştirirseniz, bellek, ancak kadar alan performans düşüklüğü bakın veya donanım tarafından oluşturulan bir özel durum hizalanmamış erişim için bile almak olarak kullanamazsınız.  Kullanarak bu özel durum davranışını değiştirebilirsiniz [SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621).  
  
 **Göster** (isteğe bağlı)  
 Hizalama sevk geçerli bayt değeri görüntüler. Değer, bir uyarı iletisi görüntülenir.  
  
 **anında iletme** (isteğe bağlı)  
 Geçerli paket hizalama iter değer iç derleyici yığını ve geçerli paket hizalama değerini için ayarlar `n`. Varsa `n` belirtilmezse, geçerli hizalama değeri sevk gönderilir.  
  
 **POP** (isteğe bağlı)  
 Derleyici iç yığını üstten kaydını kaldırır. Varsa `n` ile belirtilmemiş **pop**, sonuçta elde edilen kayıt yığının üst kısmında ilişkili paketleme değer yeni ise hizalama değeri paket. Varsa `n` , örneğin, belirtilen `#pragma pack(pop, 16)`, `n` yeni hale hizalama değeri paket. İle pop varsa `identifier`, örneğin, `#pragma pack(pop, r1)`, tüm kayıtları yığında olan kaydını kadar Sil'i sonra `identifier` bulunur. Kayıt Sil'i ve sonuç kaydının üzerinde üst ile ilişkili paketleme yeni paket yığını değerdir hizalama değeri. İle pop varsa bir `identifier` bulunmayan yığında herhangi bir kayıttaki sonra **pop** göz ardı edilir.  
  
 `identifier`(isteğe bağlı)  
 İle kullanıldığında **itme**, iç derleyici yığında kaydı bir adı atar. İle kullanıldığında **pop**, POP kadar iç yığından kayıtları `identifier` ; kaldırılır `identifier` bulunamadı iç yığında bir şey Sil'i.  
  
 `n`(isteğe bağlı)  
 Değer paketleme için kullanılacak bayt cinsinden belirtir. Varsa derleyici seçeneği [/Zp](../build/reference/zp-struct-member-alignment.md) modül için varsayılan değeri ayarlı değil `n` 8'dir. Geçerli değerler 1, 2, 4, 8 ve 16 ' dir. Üye hizalamasını olduğunu veya bir sınır birden fazla olacaktır `n` veya daha çok üye boyutunun hangisi daha küçüktür.  
  
 `#pragma pack(pop, identifier, n)`tanımlı değil.  
  
 Hizalama değiştirme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [__alignof](../cpp/alignof-operator.md)  
  
-   [Hizalama](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [Yapı hizalama örnekleri](../build/examples-of-structure-alignment.md) (x64 belirli)  
  
    > [!WARNING]
    >  Visual Studio 2015 ve sonraki alignof işleçler ve standart alignas kullanabileceğinizi unutmayın, öğesinden farklı olarak `__alignof` ve `declspec( align )` arasında derleyicileri taşınabilen. Hala kullanmalısınız C++ Standart paketleme, adresi değil `pack` (veya diğer derleyiciler üzerinde karşılık gelen uzantısı) hizalamaları hedef mimari 's word boyutundan daha küçük belirtmek için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `pack` pragma bir yapı hizalamasını değiştirme.  
  
```  
// pragma_directives_pack.cpp  
#include <stddef.h>  
#include <stdio.h>  
  
struct S {  
   int i;   // size 4  
   short j;   // size 2  
   double k;   // size 8  
};  
  
#pragma pack(2)  
struct T {  
   int i;  
   short j;  
   double k;  
};  
  
int main() {  
   printf("%zu ", offsetof(S, i));  
   printf("%zu ", offsetof(S, j));  
   printf("%zu\n", offsetof(S, k));  
  
   printf("%zu ", offsetof(T, i));  
   printf("%zu ", offsetof(T, j));  
   printf("%zu\n", offsetof(T, k));  
}  
```  
  
```  
0 4 8  
0 4 6  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir **itme**, **pop**, ve **Göster** sözdizimi.  
  
```  
// pragma_directives_pack_2.cpp  
// compile with: /W1 /c  
#pragma pack()   // n defaults to 8; equivalent to /Zp8  
#pragma pack(show)   // C4810  
#pragma pack(4)   // n = 4  
#pragma pack(show)   // C4810  
#pragma pack(push, r1, 16)   // n = 16, pushed to stack  
#pragma pack(show)   // C4810  
#pragma pack(pop, r1, 2)   // n = 2 , stack popped  
#pragma pack(show)   // C4810  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)