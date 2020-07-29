---
title: C++ program sonlandırma
description: :::no-loc(exit):::C++ dili programın yollarını açıklar.
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- :::no-loc(exit):::ing applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- ':::no-loc(exit):::'
- ':::no-loc(abort):::'
- ':::no-loc(return):::'
- ':::no-loc(main):::'
- ':::no-loc(atexit):::'
- ':::no-loc(void):::'
ms.openlocfilehash: 216aef5dbe8d110f9d75d43b5009b89fc5bfda51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227185"
---
# <a name="c-program-termination"></a>C++ program sonlandırma

C++ ' da, :::no-loc(exit)::: şu yollarla bir program kullanabilirsiniz:

- İşlevi çağırın [:::no-loc(exit):::](:::no-loc(exit):::-function.md) .
- İşlevi çağırın [:::no-loc(abort):::](:::no-loc(abort):::-function.md) .
- Öğesinden bir [:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md) Ekstre yürütün `:::no-loc(main):::` .

## <a name="no-locexit-function"></a>:::no-loc(exit)::: işlevi

[:::no-loc(exit):::](../c-runtime-library/reference/:::no-loc(exit):::-:::no-loc(exit):::-:::no-loc(exit):::.md)İçinde belirtilen işlev, \<stdlib.h> bir C++ programını sonlandırır. İçin bir bağımsız değişken olarak sağlanan değer `:::no-loc(exit):::` , :::no-loc(return)::: programın :::no-loc(return)::: kodu veya kodu olarak işletim sistemine gönderilir :::no-loc(exit)::: . Kural gereği, bir :::no-loc(return)::: sıfır kodu programın başarıyla tamamlandığı anlamına gelir. \<stdlib.h>Programınızın başarısını veya başarısızlığını göstermek için ' de tanımlanan sabitleri EXIT_FAILURE ve EXIT_SUCCESS kullanabilirsiniz.

İşlevinden bir **`:::no-loc(return):::`** deyimin verilmesi, `:::no-loc(main):::` `:::no-loc(exit):::` işlevi :::no-loc(return)::: bağımsız değişkeni olarak değeriyle çağırma ile eşdeğerdir.

## <a name="no-locabort-function"></a>:::no-loc(abort)::: işlevi

[:::no-loc(abort):::](../c-runtime-library/reference/:::no-loc(abort):::.md)Standart içerme dosyasında da belirtilen işlev \<stdlib.h> bir C++ programını sonlandırır. Ve arasındaki fark `:::no-loc(exit):::` , `:::no-loc(abort):::` `:::no-loc(exit):::` C++ çalışma zamanı sonlandırma işlemenin gerçekleşmesini olanaklı olmasına olanak sağlar (genel nesne yıkıcıları çağrılır), ancak `:::no-loc(abort):::` programı hemen sonlandırır. `:::no-loc(abort):::`İşlev, başlatılmış genel statik nesneler için normal yok etme işlemini atlar. Ayrıca, işlevi kullanılarak belirtilen özel işlemleri de atlar [:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md) .

## <a name="no-locatexit-function"></a>:::no-loc(atexit)::: işlevi

[:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md)Program sonlandırmadan önce yürütülen eylemleri belirtmek için işlevini kullanın. ' A çağrı öncesinde başlatılan genel statik nesne **:::no-loc(atexit):::** , işleme işlevinin yürütülmesi öncesinde yok edilmez :::no-loc(exit)::: .

## <a name="no-locreturn-statement-in-no-locmain"></a>:::no-loc(return):::içindeki ifade:::no-loc(main):::

Öğesinden bir [:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md) deyimin verilmesi, `:::no-loc(main):::` işlevi çağırmaya yönelik işlevsel olarak eşdeğerdir `:::no-loc(exit):::` . Aşağıdaki örneği inceleyin:

```cpp
// :::no-loc(return):::_statement.cpp
#include <stdlib.h>
int :::no-loc(main):::()
{
    :::no-loc(exit):::( 3 );
    :::no-loc(return)::: 3;
}
```

`:::no-loc(exit):::` **`:::no-loc(return):::`** Yukarıdaki örnekteki ve deyimleri işlevsel olarak aynıdır. Ancak C++, :::no-loc(return)::: bir değerden farklı türlere sahip olan işlevleri gerektirir **`:::no-loc(void):::`** :::no-loc(return)::: . **`:::no-loc(return):::`** İfade, :::no-loc(return)::: öğesinden bir değer sağlar `:::no-loc(main):::` .

## <a name="destruction-of-static-objects"></a>Statik nesneleri yok etme

`:::no-loc(exit):::`Öğesinden bir ekstre çağırdığınızda veya yürüttüğünüzde **`:::no-loc(return):::`** `:::no-loc(main):::` , statik nesneler, başlatma işlemi için ters sırada (varsa, ' a yönelik çağrıdan sonra) yok edilir `:::no-loc(atexit):::` . Aşağıdaki örnek, başlatma ve Temizleme işlemlerinin nasıl çalıştığını gösterir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, statik nesneler ve ' a `sd1` `sd2` girişinden önce oluşturulur ve başlatılır `:::no-loc(main):::` . Bu program, ifadesini kullanarak sonlandırıldıktan sonra **`:::no-loc(return):::`** , ilk olarak `sd2` yok edilir ve sonra `sd1` . Sınıfın yıkıcısı `ShowData` Bu statik nesnelerle ilişkili dosyaları kapatır.

```cpp
// using_:::no-loc(exit):::_or_:::no-loc(return):::1.cpp
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
   :::no-loc(void)::: Disp( char *szData ) {
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

int :::no-loc(main):::() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

Bu kodu yazmanın başka bir yolu `ShowData` da blok kapsamına sahip nesneleri bildirmek, kapsam dışına çıktıklarında yok edilmesi gerekir:

```cpp
int :::no-loc(main):::() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[:::no-loc(main):::işlev ve komut satırı bağımsız değişkenleri](:::no-loc(main):::-function-command-line-args.md)
