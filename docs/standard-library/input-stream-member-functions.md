---
description: 'Daha fazla bilgi edinin: giriş akışı üye Işlevleri'
title: Giriş Akışı Üye İşlevleri
ms.date: 07/19/2019
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
ms.openlocfilehash: 8b75470d39e5c376da497f721c725eaad8424b3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231608"
---
# <a name="input-stream-member-functions"></a>Giriş Akışı Üye İşlevleri

Giriş akışı üye işlevleri disk girişi için kullanılır.

## <a name="open"></a><a name="vclrftheopenfunctionforinputstreamsanchor11"></a> açın

Bir giriş dosyası akışı ( `ifstream` ) kullanıyorsanız, bu akışı belirli bir disk dosyası ile ilişkilendirmeniz gerekir. Bunu oluşturucuda yapabilir veya `open` işlevini kullanabilirsiniz. Her iki durumda da, bağımsız değişkenler aynıdır.

Bir giriş akışıyla ilişkili dosyayı açtığınızda genellikle bir [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) bayrağını belirtirsiniz (varsayılan mod ' dır `ios::in` ). Bayrakların bir listesi için `openmode` bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode). Bayraklar bit düzeyinde OR (&#124;) işleci ile birleştirilebilir.

Bir dosyayı okumak için, önce `fail` varolup olmadığını öğrenmek için üye işlevini kullanın:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="get"></a><a name="vclrfthegetfunctionanchor12"></a> Al

Biçimlendirilmemiş `get` üye işlevi, `>>` iki özel durum ile işleç gibi çalışır. İlk olarak, `get` işlev boşluk karakterleri içerir, ancak Extractor, `skipws` bayrak ayarlandığında boşluk dışlar (varsayılan). İkinci olarak, `get` işlev bağlı çıkış akışının (örneğin,) silinmesine neden olur `cout` .

İşlevin çeşitlemesi bir `get` arabellek adresi ve okunacak en fazla karakter sayısını belirtir. Bu örnekte gösterildiği gibi belirli bir değişkene gönderilen karakter sayısını kısıtlamak için faydalıdır:

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

## <a name="getline"></a><a name="vclrfthegetlinefunctionanchor13"></a> getline

`getline`Üye işlevi `get` işlevine benzer. Her iki işlev de giriş için Sonlandırıcı karakteri belirten üçüncü bir bağımsız değişkene izin verir. Varsayılan değer yeni satır karakteridir. Her iki işlev de gerekli sonlandırma karakteri için bir karakter ayırmakta. Ancak, `get` akışta sonlandırma karakterini bırakır ve `getline` sonlandırma karakterini kaldırır.

Aşağıdaki örnek, giriş akışı için bir sonlandırma karakteri belirtir:

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

## <a name="read"></a><a name="vclrfthereadfunctionanchor14"></a> okuyamaz

`read`Üye işlevi bir dosyadan belirtilen bellek alanına bayt okur. Length bağımsız değişkeni, okunan bayt sayısını belirler. Bu bağımsız değişkeni eklemezseniz, okuma, dosyanın fiziksel sonuna ulaşıldığında veya bir metin modu dosyası söz konusu olduğunda, gömülü bir karakter okunurken yanıt vermez `EOF` .

Bu örnek, bir bordro dosyasındaki ikili kaydı bir yapıya okur:

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

Program, veri kayıtlarının kesin olmayan satır dönüşü veya satır besleme karakterleri olmadan yapı tarafından belirtilen şekilde biçimlendirildiğini varsayar.

## <a name="seekg-and-tellg"></a><a name="vclrftheseekgandtellgfunctionsanchor7"></a> seekg ve tellg

Giriş dosyası akışları, dosyadaki bir sonraki okunacak konuma bir iç işaretçi tutar. Bu işaretçiyi `seekg` , aşağıda gösterildiği gibi işleviyle ayarlarsınız:

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

`seekg`Kayıt odaklı veri yönetimi sistemlerini uygulamak için kullanmak üzere, dosyanın sonuna göre bayt konumunu almak için sabit uzunluklu kayıt boyutunu kayıt numarası ile çarpın ve sonra `get` kaydı okumak için nesnesini kullanın.

`tellg`Üye işlevi, okuma için geçerli dosya konumunu döndürür. Bu değer `streampos` , **`typedef`** içinde tanımlanan türüdür \<iostream> . Aşağıdaki örnek bir dosyayı okur ve boşluk konumlarını gösteren iletileri görüntüler.

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

## <a name="close"></a><a name="vclrftheclosefunctionforinputstreamsanchor15"></a> ~eksik

`close`Üye işlevi, bir giriş dosyası akışıyla ilişkili disk dosyasını kapatır ve işletim sistemi dosya tanıtıcısını serbest bırakır. [`ifstream`](../standard-library/basic-ifstream-class.md)Yıkıcı dosyayı sizin için kapatır, ancak `close` aynı Stream nesnesi için başka bir dosya açmanız gerekiyorsa bu işlevi kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş akışları](../standard-library/input-streams.md)
