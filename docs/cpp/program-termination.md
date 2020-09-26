---
title: C++ program sonlandırma
description: exitC++ dili programın yollarını açıklar.
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- exit
- abort
- return
- main
- atexit
- void
ms.openlocfilehash: fd0c7699ae032b5551f4fbc37eb3b7fa999a168f
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352927"
---
# <a name="c-program-termination"></a>C++ program sonlandırma

C++ ' da, exit şu yollarla bir program kullanabilirsiniz:

- İşlevi çağırın [exit](../c-runtime-library/reference/exit-exit-exit.md) .
- İşlevi çağırın [abort](../c-runtime-library/reference/abort.md) .
- Öğesinden bir [return](return-statement-cpp.md) Ekstre yürütün `main` .

## <a name="no-locexit-function"></a>exit işlevi

[exit](../c-runtime-library/reference/exit-exit-exit.md)İçinde belirtilen işlev, \<stdlib.h> bir C++ programını sonlandırır. İçin bir bağımsız değişken olarak sağlanan değer `exit` , return programın return kodu veya kodu olarak işletim sistemine gönderilir exit . Kural gereği, bir return sıfır kodu programın başarıyla tamamlandığı anlamına gelir. \<stdlib.h>Programınızın başarısını veya başarısızlığını göstermek için ' de tanımlanan sabitleri EXIT_FAILURE ve EXIT_SUCCESS kullanabilirsiniz.

İşlevinden bir **`return`** deyimin verilmesi, `main` `exit` işlevi return bağımsız değişkeni olarak değeriyle çağırma ile eşdeğerdir.

## <a name="no-locabort-function"></a>abort işlevi

[abort](../c-runtime-library/reference/abort.md)Standart içerme dosyasında da belirtilen işlev \<stdlib.h> bir C++ programını sonlandırır. Ve arasındaki fark `exit` , `abort` `exit` C++ çalışma zamanı sonlandırma işlemenin gerçekleşmesini olanaklı olmasına olanak sağlar (genel nesne yıkıcıları çağrılır), ancak `abort` programı hemen sonlandırır. `abort`İşlev, başlatılmış genel statik nesneler için normal yok etme işlemini atlar. Ayrıca, işlevi kullanılarak belirtilen özel işlemleri de atlar [atexit](../c-runtime-library/reference/atexit.md) .

## <a name="no-locatexit-function"></a>atexit işlevi

[atexit](../c-runtime-library/reference/atexit.md)Program sonlandırmadan önce yürütülen eylemleri belirtmek için işlevini kullanın. ' A çağrı öncesinde başlatılan genel statik nesne **atexit** , işleme işlevinin yürütülmesi öncesinde yok edilmez exit .

## <a name="no-locreturn-statement-in-no-locmain"></a>return içindeki ifade main

Öğesinden bir [return](return-statement-cpp.md) deyimin verilmesi, `main` işlevi çağırmaya yönelik işlevsel olarak eşdeğerdir `exit` . Aşağıdaki örneği inceleyin:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit` **`return`** Yukarıdaki örnekteki ve deyimleri işlevsel olarak aynıdır. Ancak C++, return bir değerden farklı türlere sahip olan işlevleri gerektirir **`void`** return . **`return`** İfade, return öğesinden bir değer sağlar `main` .

## <a name="destruction-of-static-objects"></a>Statik nesneleri yok etme

`exit`Öğesinden bir ekstre çağırdığınızda veya yürüttüğünüzde **`return`** `main` , statik nesneler, başlatma işlemi için ters sırada (varsa, ' a yönelik çağrıdan sonra) yok edilir `atexit` . Aşağıdaki örnek, başlatma ve Temizleme işlemlerinin nasıl çalıştığını gösterir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, statik nesneler ve ' a `sd1` `sd2` girişinden önce oluşturulur ve başlatılır `main` . Bu program, ifadesini kullanarak sonlandırıldıktan sonra **`return`** , ilk olarak `sd2` yok edilir ve sonra `sd1` . Sınıfın yıkıcısı `ShowData` Bu statik nesnelerle ilişkili dosyaları kapatır.

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

Bu kodu yazmanın başka bir yolu `ShowData` da blok kapsamına sahip nesneleri bildirmek, kapsam dışına çıktıklarında yok edilmesi gerekir:

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[main işlev ve komut satırı bağımsız değişkenleri](main-function-command-line-args.md)
