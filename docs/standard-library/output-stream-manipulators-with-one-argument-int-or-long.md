---
description: 'Hakkında daha fazla bilgi edinin: bir bağımsız değişkenle çıkış akışı Işleicileri (int veya Long)'
title: Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: e04486f7d207731d9fbf7ba8083ffcb02a82ba8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340898"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)

İostream sınıf kitaplığı, parametreli düzenlemeler oluşturmaya yönelik bir makro kümesi sağlar. Tek **`int`** veya bağımsız değişkenine sahip olan düzenlemeler **`long`** özel bir durumdur. Tek veya bağımsız değişken (gibi) kabul eden bir çıkış akışı oluşturma işlemi oluşturmak için **`int`** **`long`** `setw` , içinde tanımlanan _Smanip makrosunu kullanmanız gerekir \<iomanip> . Bu örnek `fillblank` , akışa belirtilen sayıda boşluk ekleyen bir işleici tanımlar:

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

[Bağımsız değişkenlerle özel Işleicileri](../standard-library/custom-manipulators-with-arguments.md)
