---
title: Giriş Akışı Üye İşlevleri
ms.date: 07/19/2019
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
ms.openlocfilehash: b846ff177f3032d81e5c81a39a0111c73a1750fb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452064"
---
# <a name="input-stream-member-functions"></a>Giriş Akışı Üye İşlevleri

Giriş akışı üye işlevleri disk girişi için kullanılır.

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a>açın

Bir giriş dosyası akışı (`ifstream`) kullanıyorsanız, bu akışı belirli bir disk dosyası ile ilişkilendirmeniz gerekir. Bunu oluşturucuda yapabilir veya `open` işlevini kullanabilirsiniz. Her iki durumda da, bağımsız değişkenler aynıdır.

Bir giriş akışıyla ilişkili dosyayı açtığınızda genellikle bir [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) bayrağı belirtirsiniz (varsayılan mod ' dır `ios::in`). `openmode` Bayrakların bir listesi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode). Bayraklar bit düzeyinde OR ( &#124; ) işleciyle birleştirilebilir.

Bir dosyayı okumak için, önce varolup olmadığını `fail` öğrenmek için üye işlevini kullanın:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a>Al

Biçimlendirilmemiş `get` üye işlevi, `>>` iki özel durum ile işleç gibi çalışır. İlk olarak, `get` işlev boşluk karakterleri içerir, ancak Extractor, `skipws` bayrak ayarlandığında boşluk dışlar (varsayılan). İkinci olarak, `get` işlev bağlı çıkış akışının (`cout`Örneğin,) silinmesine neden olur.

`get` İşlevin çeşitlemesi bir arabellek adresi ve okunacak en fazla karakter sayısını belirtir. Bu örnekte gösterildiği gibi belirli bir değişkene gönderilen karakter sayısını kısıtlamak için faydalıdır:

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

## <a name="vclrfthegetlinefunctionanchor13"></a>getline

Üye işlevi `get` işlevine benzer. `getline` Her iki işlev de giriş için Sonlandırıcı karakteri belirten üçüncü bir bağımsız değişkene izin verir. Varsayılan değer yeni satır karakteridir. Her iki işlev de gerekli sonlandırma karakteri için bir karakter ayırmakta. Ancak, `get` akışta sonlandırma karakterini bırakır ve `getline` sonlandırma karakterini kaldırır.

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

## <a name="vclrfthereadfunctionanchor14"></a>okuyamaz

`read` Üye işlevi bir dosyadan belirtilen bellek alanına bayt okur. Length bağımsız değişkeni, okunan bayt sayısını belirler. Bu bağımsız değişkeni eklemezseniz, okuma, dosyanın fiziksel sonuna ulaşıldığında veya bir metin modu dosyası söz konusu olduğunda, gömülü `EOF` bir karakter okunurken yanıt vermez.

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

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a>seekg ve tellg

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

Kayıt odaklı `seekg` veri yönetimi sistemlerini uygulamak için kullanmak üzere, dosyanın sonuna göre bayt konumunu almak için sabit uzunluklu kayıt boyutunu kayıt numarası ile çarpın ve sonra kaydı okumak için `get` nesnesini kullanın.

`tellg` Üye işlevi, okuma için geçerli dosya konumunu döndürür. Bu değer, `streampos` \<iostream > tanımlı `typedef` bir türüdür. Aşağıdaki örnek bir dosyayı okur ve boşluk konumlarını gösteren iletileri görüntüler.

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

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a>~eksik

`close` Üye işlevi, bir giriş dosyası akışıyla ilişkili disk dosyasını kapatır ve işletim sistemi dosya tanıtıcısını serbest bırakır. Yıkıcı dosyayı sizin için kapatır, ancak aynı Stream nesnesi için başka bir `close` dosya açmanız gerekiyorsa bu işlevi kullanabilirsiniz. [`ifstream`](../standard-library/basic-ifstream-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)
