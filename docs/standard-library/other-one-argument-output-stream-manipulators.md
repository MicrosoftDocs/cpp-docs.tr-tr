---
description: 'Daha fazla bilgi edinin: diğer One-Argument çıkış akışı düzenlemeleri'
title: Diğer Tek Bağımsız Değişkenli Çıkış Akışı Manipülatörleri
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, one-argument manipulators
ms.assetid: e381dee8-6b16-4cef-805a-4a6a1d2b696b
ms.openlocfilehash: 3ad50216375de1ca5e2d9fe41b206aa01a8c8e80
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342263"
---
# <a name="other-one-argument-output-stream-manipulators"></a>Diğer Tek Bağımsız Değişkenli Çıkış Akışı Manipülatörleri

Aşağıdaki örnek `money` , bir türü olan bir sınıfı kullanır **`long`** . Bu işlem, `setpic` sınıfının aşırı yüklenmiş akış ekleme işleci tarafından kullanılabilecek sınıfa bir biçimlendirme "Picture" dizesi ekliyor `money` . Resim dizesi bir `money` Stream sınıfının veri üyesi yerine sınıfında statik bir değişken olarak depolanır, bu nedenle yeni bir çıkış akışı sınıfı türetmeniz gerekmez.

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

[Bağımsız değişkenlerle özel Işleicileri](../standard-library/custom-manipulators-with-arguments.md)
