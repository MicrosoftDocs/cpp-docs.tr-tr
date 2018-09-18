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
ms.openlocfilehash: 4ce62f17008bf4a1ba805db40583e6c63b69a302
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059992"
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