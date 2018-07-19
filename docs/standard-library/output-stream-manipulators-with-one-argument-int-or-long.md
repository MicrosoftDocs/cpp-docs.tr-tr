---
title: Stream Manipülatörleri (int veya long) bir bağımsız değişkenli çıkış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f569b064d2ee5de5bd1aa39c9d443c8a49ca2677
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961857"
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
