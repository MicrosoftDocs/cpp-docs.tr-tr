---
title: Giriş akışı üye işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41ab041fe3cee9a3b6065f22e5f96a44a56af030
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="input-stream-member-functions"></a>Giriş Akışı Üye İşlevleri

Giriş akışı üye işlevleri disk giriş için kullanılır. Üye işlevlerini içerir:

- [Giriş akışları için açık işlevi](#vclrftheopenfunctionforinputstreamsanchor11)

- [Alma](#vclrfthegetfunctionanchor12)

- [Getline](#vclrfthegetlinefunctionanchor13)

- [Okuma](#vclrfthereadfunctionanchor14)

- [Seekg ve tellg işlevleri](#vclrftheseekgandtellgfunctionsanchor7)

- [Giriş akışları için Kapat işlevi](#vclrftheclosefunctionforinputstreamsanchor15)

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Giriş akışları için açık işlevi

Bir giriş dosya akışı (ifstream) kullanıyorsanız, bu akış belirli bir disk dosyası ile ilişkilendirmeniz gerekir. Bu oluşturucuda yapabilirsiniz veya kullanabilirsiniz **açmak** işlevi. Her iki durumda da bağımsız değişkenler aynıdır.

Genellikle belirttiğiniz bir [ios_base::openmode](../standard-library/ios-base-class.md#openmode) bir giriş akışı ile ilişkilendirilmiş dosyayı açtığınızda İşaretle (varsayılan mod budur **ios::in**). Bir listesi için **open_mode** bayrakları, bkz: [açık](#vclrftheopenfunctionforinputstreamsanchor11). Bit düzeyinde OR ile bayrakları birleştirilebilir ( &#124; ) işleci.

Bir dosyayı okumak için önce kullanın **başarısız** var olup olmadığını belirlemek için üye fonksiyonu:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a> Alma

Biçimlendirilmemiş **almak** üye işlevi çalışır gibi **>>** iki özel durumlarla birlikte işleci. İlk olarak, **almak** işlevi ayıklayıcısı boşluk dışlar ancak boşluk karakterleri içeren zaman **skipws** bayrağını (varsayılan) ayarlayın. İkinci, **almak** işlevidir bağlı çıkış akışına neden olasılığı (`cout`, örneğin) kopyalanması için.

Bir çeşitlemesi **almak** işlevi bir arabellek adresi ve okumak için karakter üst sınırını belirtir. Bu, bu örnekte gösterildiği gibi belirli bir değişken için gönderilen karakter sayısını sınırlamak için yararlıdır:

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

**Getline** üye işlevine benzer **almak** işlevi. Her iki işlevler girişi için sonlandırma karakter belirten üçüncü bağımsız değişken izin verir. Yeni satır karakteri varsayılan değerdir. Her iki işlevleri bir karakter gerekli sonlandırma karakter ayırın. Ancak, **almak** sonlandırma karakter akışta bırakır ve **getline** Sonlandırıcı karakteri kaldırır.

Aşağıdaki örnek Giriş akışı için bir sonlandırma karakter belirtir:

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

**Okuma** üye işlevi belirtilen bir bellek alanı için bir dosyadan baytı okur. Length bağımsız okunan bayt sayısını belirler. Bu bağımsız değişken eklemezseniz okuma fiziksel dosya sonuna geldiğinde veya metin moddaki dosyası, katıştırılmış zaman durdurur `EOF` karakter okunur.

Bu örnek bir ikili kaydı yapısı içinde bir bordro dosyasından okur:

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

Program veri kayıtlarını biçimlendirildiğini tam olarak belirtildiği gibi sonlandırma hiçbir satır başı veya satır besleme karakter yapısıyla varsayar.

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Seekg ve tellg işlevleri

Giriş dosyası akışları veri sonraki okumaya nerede dosya konumu için bir iç işaretçi tutun. Bu işaretçiyle ayarladığınız `seekg` aşağıda gösterildiği gibi işlev:

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

Kullanılacak `seekg` kayıt odaklı veriler yönetim sistemleri uygulamak için sabit uzunluklu kayıt boyutunu bayt konumuna dosyasının sonuna göre elde edin ve ardından kayıt numarasına göre Çarp **almak** okumak için nesne kaydı.

`tellg` Üye işlevi okumak için geçerli dosya konumu döndürür. Bu değer `streampos`, `typedef` tanımlanan \<iostream >. Aşağıdaki örnek, bir dosyayı okur ve alanları konumlarını gösteren bir ileti görüntüler.

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

**Kapatmak** üye işlevi olan bir giriş dosyası akış ilişkili disk dosyası kapatır ve işletim sistemi dosya işleci boşaltır. [İfstream](../standard-library/basic-ifstream-class.md) yıkıcı kapatır dosya, ancak kullanabilirsiniz **kapatmak** aynı stream nesnesi için başka bir dosyayı açmaya gerekiyorsa işlev.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
