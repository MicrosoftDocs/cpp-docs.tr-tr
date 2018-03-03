---
title: "Exit veya dönüş kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f5c9fdb17811206732811db4e27006dc5e0ed84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-exit-or-return"></a>exit veya return Kullanma
Çağırdığınızda **çıkmak** veya yürütme bir `return` from deyimi **ana**, statik nesneler kendi başlatma ters sırada yok. Aşağıdaki örnek, başlatma ve temizleme gibi nasıl çalıştığını gösterir.  
  
## <a name="example"></a>Örnek  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 Önceki örnekte, statik nesneleri `sd1` ve `sd2` oluşturulur ve girişine önce başlatılmış `main`. Bu program kullanarak sonlandırıldıktan sonra `return` deyimi, ilk `sd2` yok ve ardından `sd1`. Yıkıcı için `ShowData` sınıfı statik bu nesnelerle ilişkili dosyaları kapatır.   
  
 Bu kod yazmak için başka bir yolu bildirmektir `ShowData` kapsamının dışına gittiğinizde yok edilmesi vermeden blok kapsamlı nesneler:  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ek Sonlandırma Konuları](../cpp/additional-termination-considerations.md)