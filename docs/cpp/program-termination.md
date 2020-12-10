---
title: C++ program sonlandırma
description: C++ dil programından çıkmak için standart yollar hakkında bilgi edinin.
ms.date: 12/07/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.openlocfilehash: 15d31d8d454f6ac90e012d35ef14e6d6e0a9e29a
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933215"
---
# <a name="c-program-termination"></a>C++ program sonlandırma

C++ ' da, bir programdan şu yollarla çıkabilirsiniz:

- İşlevi çağırın [`exit`](../c-runtime-library/reference/exit-exit-exit.md) .
- İşlevi çağırın [`abort`](../c-runtime-library/reference/abort.md) .
- Öğesinden bir [`return`](return-statement-cpp.md) Ekstre yürütün `main` .

## <a name="exit-function"></a>`exit` işlevi

[`exit`](../c-runtime-library/reference/exit-exit-exit.md)İçinde belirtilen işlev, \<stdlib.h> bir C++ programını sonlandırır. İçin bir bağımsız değişken olarak sağlanan değer, `exit` programın dönüş kodu veya çıkış kodu olarak işletim sistemine döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir. `EXIT_FAILURE` `EXIT_SUCCESS` \<stdlib.h> Programınızın başarısını veya başarısızlığını göstermek için ' de tanımlanan sabitleri ve ayrıca kullanabilirsiniz.

İşlevinden bir **`return`** deyimin verilmesi, `main` `exit` işlevi bağımsız değişkeni olarak dönüş değeri ile çağırma ile eşdeğerdir.

## <a name="abort-function"></a>`abort` işlevi

[`abort`](../c-runtime-library/reference/abort.md)Standart içerme dosyasında da belirtilen işlev \<stdlib.h> bir C++ programını sonlandırır. Ve arasındaki fark `exit` , `abort` `exit` C++ çalışma zamanı sonlandırma işlemenin ortaya sürme (genel nesne yıkıcıları çağırılır), ancak `abort` programı hemen sonlandırır. `abort`İşlev, başlatılmış genel statik nesneler için normal yok etme işlemini atlar. Ayrıca, işlevi kullanılarak belirtilen özel işlemleri de atlar [`atexit`](../c-runtime-library/reference/atexit.md) .

## <a name="atexit-function"></a>`atexit` işlevi

[`atexit`](../c-runtime-library/reference/atexit.md)Program sonlandırılmadan önce yürütülen eylemleri belirtmek için işlevini kullanın. Çıkış işleme işlevinin yürütülmesinden önce, çağrısının yok edilmesi için hiçbir genel statik nesne başlatılmamış `atexit` .

## <a name="return-statement-in-main"></a>`return` içindeki ifade `main`

Öğesinden bir [`return`](return-statement-cpp.md) deyimin verilmesi, `main` işlevi çağırmaya yönelik işlevsel olarak eşdeğerdir `exit` . Aşağıdaki örneği inceleyin:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit` **`return`** Yukarıdaki örnekteki ve deyimleri işlevsel olarak aynıdır. Normal olarak, C++, **`void`** bir değer döndürün dışında, dönüş türleri olan işlevlerin kullanılmasını gerektirir. `main`İşlev bir özel durumdur; bir deyimleri olmadan bitebilirler **`return`** . Bu durumda, çağırma işlemine uygulamaya özgü bir değer döndürür. **`return`** İfade, öğesinden bir dönüş değeri belirtmenize olanak tanır `main` .

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
   ShowData sd1( "CON" ), sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[`main` işlev ve komut satırı bağımsız değişkenleri](main-function-command-line-args.md)
