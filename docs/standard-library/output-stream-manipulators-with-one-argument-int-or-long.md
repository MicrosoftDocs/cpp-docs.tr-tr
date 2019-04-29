---
title: Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: e093512af2741329c58db0b613453f3388bacdf2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370807"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)

İostream sınıf kitaplığı parametreli manipülatörleri oluşturmak için makroları sunmaktadır. Tek bir manipülatörleri **int** veya **uzun** bağımsız değişkeni olan bir özel durum. Tek bir kabul eden bir çıkış akışı işleyiciyi oluşturmak için **int** veya **uzun** bağımsız değişken (gibi `setw`), tanımlanan _Smanip makro kullanmalısınız \<iomanip >. Bu örnekte tanımlayan bir `fillblank` akımına boşluk belirtilen sayıda eklediği işleyici:

## <a name="example"></a>Örnek

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkenlerle Birlikte Özel Manipülatörler](../standard-library/custom-manipulators-with-arguments.md)<br/>
