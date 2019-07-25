---
title: Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: 93e4de25323514eb4105814b565dc3ddc3fbb737
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453003"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)

İostream sınıf kitaplığı, parametreli düzenlemeler oluşturmaya yönelik bir makro kümesi sağlar. Tek bir **int** veya **Long** bağımsız değişkenine sahip olan düzenlemeler özel bir durumdur. Tek bir **int** veya **Long** bağımsız değişkenini (gibi `setw`) kabul eden bir çıkış akışı oluşturma işlemi oluşturmak için, \<iomanıp > tanımlanmış olan _smanıp makrosunu kullanmanız gerekir. Bu örnek, akışa `fillblank` belirtilen sayıda boşluk ekleyen bir işleici tanımlar:

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

[Bağımsız Değişkenlerle Birlikte Özel Manipülatörler](../standard-library/custom-manipulators-with-arguments.md)
