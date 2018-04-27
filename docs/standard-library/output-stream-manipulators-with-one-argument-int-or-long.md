---
title: Çıkış akışı Manipülatörleri (int veya long) tek bağımsız değişkenli | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68b26634bea9409be7166b6f937f71043f11473a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)

İostream sınıf kitaplığı parametreli manipülatörleri oluşturmak için makroları kümesi sağlar. Tek bir manipülatörleri `int` veya `long` bağımsız değişkeni olan bir özel durum. Tek bir kabul eden bir çıkış akışı manipulator oluşturmak için `int` veya `long` bağımsız değişkeni (gibi `setw`), tanımlanan _Smanip makrosu kullanmalısınız \<iomanip >. Bu örnek tanımlayan bir `fillblank` boşlukları belirtilen sayıda akışa ekler manipulator:

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
