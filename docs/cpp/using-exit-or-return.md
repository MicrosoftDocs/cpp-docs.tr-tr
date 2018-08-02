---
title: Çıkmayın veya dönüş kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47fb8ff09fc50557283a0f4e8ef0e159bc900e86
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460951"
---
# <a name="using-exit-or-return"></a>exit veya return Kullanma
Çağırdığınızda **çıkmak** veya yürütme bir **dönüş** deyimden `main`, statik nesneleri başlatma ters sırada yok edilir. Aşağıdaki örnek, başlatma ve temizleme gibi nasıl çalıştığını gösterir.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
 Yukarıdaki örnekte, statik nesneler `sd1` ve `sd2` oluşturulur ve girişten önce başlatılır `main`. Bu program kullanarak sonlandırıldıktan sonra **dönüş** deyimi, ilk `sd2` yok ve ardından `sd1`. Yok Edicisi `ShowData` sınıfı statik bu nesnelerle ilişkili dosyaları kapatır.   
  
 Bu kod yazmak için başka bir şekilde bildirmektir `ShowData` onlara kapsam dışına gitmeleri yok sağlar, blok kapsamlı nesneler:  
  
```cpp 
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Ek Sonlandırma Konuları](../cpp/additional-termination-considerations.md)