---
title: Diğer Tek Bağımsız Değişkenli Çıkış Akışı Manipülatörleri
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, one-argument manipulators
ms.assetid: e381dee8-6b16-4cef-805a-4a6a1d2b696b
ms.openlocfilehash: b5f24033d8da0933b8252fdace60fb419ef2e605
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664834"
---
# <a name="other-one-argument-output-stream-manipulators"></a>Diğer Tek Bağımsız Değişkenli Çıkış Akışı Manipülatörleri

Aşağıdaki örnek, bir sınıfı kullanır. `money`, olduğu bir **uzun** türü. `setpic` İşleyici sınıfı aşırı yüklenmiş akışı ekleme operatör tarafından kullanılabilecek sınıfına bir biçimlendirme "resmi" dizesi ekler `money`. Statik bir değişken olarak resim dizesinde depolanan `money` yerine stream sınıfı veri üyesi olarak, bu nedenle yeni bir çıkış akışı sınıf türetmek erişiminiz yok sınıfı.

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
