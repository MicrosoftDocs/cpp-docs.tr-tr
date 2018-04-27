---
title: Diğer tek-bağımsız değişken çıkış akışı Manipülatörleri | Microsoft Docs
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
- output streams, one-argument manipulators
ms.assetid: e381dee8-6b16-4cef-805a-4a6a1d2b696b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c263de73c34506e3c2fd9c26500d97d9513e22f0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="other-one-argument-output-stream-manipulators"></a>Diğer Tek Bağımsız Değişkenli Çıkış Akışı Manipülatörleri

Aşağıdaki örnek, bir sınıf kullanır `money`, olduğu bir `long` türü. `setpic` Manipulator sınıfı aşırı yüklenmiş akış ekleme operatör tarafından kullanılan sınıf için bir biçimlendirme "resim" dizesi iliştirir `money`. Resim dize olarak statik bir değişkende depolanır `money` stream sınıfı veri üyesi olarak, bu nedenle, yeni bir çıkış akışı sınıf türetin gerekmez yerine sınıfı.

## <a name="example"></a>Örnek

```cpp
// one_arg_output.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

typedef char* charp;

class money
{
private:
    long value;
    static char *szCurrentPic;
public:
    money( long val ) { value = val; }
    friend ostream& operator << ( ostream& os, money m ) {
        // A more complete function would merge the picture
        // with the value rather than simply appending it
        os << m.value << '[' << money::szCurrentPic << ']';
        return os;
    }
    static void setpic( char* szPic ) {
        money::szCurrentPic = new char[strlen( szPic ) + 1];
        strcpy_s( money::szCurrentPic, strlen( szPic ) + 1, szPic );
    }
};

char *money::szCurrentPic;  // Static pointer to picture

void fb( ios_base& os, char * somename )
{
   money::setpic(somename);
/*
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
*/
}

_Smanip<charp>
   __cdecl setpic(char * somename)
   {
   return (_Smanip<charp>(&fb, somename));
   }

int main( )
{
    money amt = (long)35235.22;
    cout << setiosflags( ios::fixed );
    cout << setpic( "###,###,###.##" ) << "amount = " << amt << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkenlerle Birlikte Özel Manipülatörler](../standard-library/custom-manipulators-with-arguments.md)<br/>
