---
title: Giriş Akışı Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
ms.openlocfilehash: b046ea1995d5a8eaa39dced9feb7a5e4c422c253
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663989"
---
# <a name="input-stream-member-functions"></a>Giriş Akışı Üye İşlevleri

Giriş akışı üye işlevleri, disk giriş için kullanılır. Üye işlevleri şunları içerir:

- [Giriş akışları için açık işlevi](#vclrftheopenfunctionforinputstreamsanchor11)

- [Get](#vclrfthegetfunctionanchor12)

- [Getline](#vclrfthegetlinefunctionanchor13)

- [Okuma](#vclrfthereadfunctionanchor14)

- [Seekg ve tellg işlevleri](#vclrftheseekgandtellgfunctionsanchor7)

- [Giriş akışları için Kapat işlevi](#vclrftheclosefunctionforinputstreamsanchor15)

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Giriş akışları için açık işlevi

Bir giriş dosya akışı (ifstream) kullanıyorsanız, bu akış bir belirli disk dosyası ile ilişkilendirmeniz gerekir. Bu oluşturucuda yapabilirsiniz veya kullanabileceğiniz `open` işlevi. Her iki durumda da aynı bağımsız değişkenler.

Genel olarak belirttiğiniz bir [ios_base::openmode](../standard-library/ios-base-class.md#openmode) bir giriş akışı ile ilişkili dosyayı açtığınızda bayrağını (varsayılan mod `ios::in`). Bir listesi için `open_mode` bayrakları, bkz: [açık](#vclrftheopenfunctionforinputstreamsanchor11). Bayrak bit düzeyinde OR ile birleştirilebilir ( &#124; ) işleci.

Bir dosyayı okumak için önce kullanın `fail` üye işlevi var olup olmadığını belirlemek için:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a> Get

Biçimlendirilmemiş `get` üye işlev çalışır gibi `>>` işleci iki özel durumu. İlk olarak, `get` işlevi içeren beyaz boşluk karakterleri, boşluk ayıklayıcısı dışlar ise zaman `skipws` bayrağı ayarlanmış (varsayılan). İkinci olarak, `get` işlevi bağlı çıkış akışına neden olma olasılığını (`cout`, örneğin) kopyalanması için.

Çeşitlemesi `get` işlevi bir arabellek adresi ve en fazla Okunacak karakter sayısını belirtir. Bu örnekte gösterildiği gibi belirli bir değişkene gönderilen karakter sayısını sınırlamak için kullanışlıdır:

```cpp
// ioo_get_function.cpp
// compile with: /EHsc
// Type up to 24 characters and a terminating character.
// Any remaining characters can be extracted later.
#include <iostream>
using namespace std;

int main()
{
   char line[25];
   cout << " Type a line terminated by carriage return\n>";
   cin.get( line, 25 );
   cout << line << endl;
}
```

### <a name="input"></a>Giriş

```Input
1234
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
1234
```

## <a name="vclrfthegetlinefunctionanchor13"></a> Getline

`getline` Üye işlevine benzer `get` işlevi. Her iki işlev girişi için Sonlandırıcı karakter belirten üçüncü bir bağımsız değişken izin verin. Yeni satır karakterini varsayılan değerdir. Her iki işlev, gerekli Sonlandırıcı karakter için bir karakter saklı tutarız. Ancak, `get` Sonlandırıcı karakter stream'de bırakır ve `getline` Sonlandırıcı karakteri kaldırır.

Aşağıdaki örnek, bir giriş akışı Sonlandırıcı karakter belirtir:

```cpp
// getline_func.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char line[100];
   cout << " Type a line terminated by 't'" << endl;
   cin.getline( line, 100, 't' );
   cout << line;
}
```

### <a name="input"></a>Giriş

```Input
test
```

## <a name="vclrfthereadfunctionanchor14"></a> Okuma

`read` Üye işlevi bir dosyadan bayt bellek belirtilen bir alana okur. Uzunluk değişkeni, okunan bayt sayısını belirler. Bu bağımsız değişkeni eklemezseniz, fiziksel dosya sonuna ulaşıldığında veya bir metin modunda dosyası katıştırılmış zaman okuma durdurur `EOF` karakter okunur.

Bu örnek bir ikili kayıt yapısı içinde bir bordro dosyadan okur:

```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main()
{
   struct
   {
      double salary;
      char name[23];
   } employee;

   ifstream is( "payroll" );
   if( is ) {  // ios::operator void*()
      is.read( (char *) &employee, sizeof( employee ) );
      cout << employee.name << ' ' << employee.salary << endl;
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

Program veri kayıtlarının biçimlendirildiğini tam olarak belirtilen sonlandırma hiçbir satır başı veya satır besleme karakteri ile yapısı tarafından varsayar.

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Seekg ve tellg işlevleri

Giriş dosyası akışları veri sonraki okunacak nerede dosya konumuna bir iç işaretçi tutun. Bu işaretçiyle ayarladığınız `seekg` burada gösterildiği gibi işlev:

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main( )
{
   char ch;

   ifstream tfile( "payroll" );
   if( tfile ) {
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)
      while ( tfile.good() ) { // EOF or failure stops the reading
         tfile.get( ch );
         if( !ch ) break;      // quit on null
         cout << ch;
      }
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

Kullanılacak `seekg` kayıt odaklı veriler yönetim sistemleri uygulamak için sabit uzunluklu kayıt boyutu dosyasının sonuna göre bayt konumunun alıp ardından kayıt sayısıyla çarpın `get` kayıt okumak için nesne.

`tellg` Üye işlevi okumak için geçerli dosya konumu döndürür. Bu değer türünde `streampos`, `typedef` tanımlanan \<iostream >. Aşağıdaki örnek, bir dosyayı okur ve alanları konumlarını gösteren bir ileti görüntüler.

```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main( )
{
   char ch;
   ifstream tfile( "payroll" );
   if( tfile ) {
       while ( tfile.good( ) ) {
          streampos here = tfile.tellg();
          tfile.get( ch );
          if ( ch == ' ' )
             cout << "\nPosition " << here << " is a space";
       }
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Giriş akışları için Kapat işlevi

`close` Üye işlevi bir giriş dosya akışı ile ilişkili disk dosyayı kapatır ve işletim sisteminin dosya tanıtıcısı serbest bırakır. [İfstream](../standard-library/basic-ifstream-class.md) yok Edicisi, dosyayı kapatır, ancak kullanabileceğiniz `close` aynı stream nesne için başka bir dosyayı açmaya gerekiyorsa işlev.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
