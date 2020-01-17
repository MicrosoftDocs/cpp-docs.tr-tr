---
title: C++program sonlandırma
description: Bir C++-dil programının exit yollarını açıklar.
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
ms.openlocfilehash: f83c9d5da5b0a1127603a97fd7946e9cca43a7a5
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123961"
---
# <a name="c-program-termination"></a>C++program sonlandırma

' C++De, bir programı şu yollarla exit yapabilirsiniz:

- [exit](exit-function.md) işlevini çağırın.
- [abort](abort-function.md) işlevini çağırın.
- `main`[return](return-statement-cpp.md) bir ifade yürütün.

## <a name="opno-locexit-function"></a>exit işlevi

\<Stdlib. h > içinde belirtilen [exit](../c-runtime-library/reference/exit-exit-exit.md) işlevi bir C++ programı sonlandırır. `exit` için bir bağımsız değişken olarak sağlanan değer, programın return kodu veya exit kodu olarak işletim sistemine döndürülür. Kurala göre, sıfır return bir kodu programın başarıyla tamamlandığı anlamına gelir. Programınızın başarısını veya başarısızlığını göstermek için \<Stdlib. h > içinde de tanımlanan sabitleri EXIT_FAILURE ve EXIT_SUCCESS kullanabilirsiniz.

`main` işlevinden bir **return** deyimin verilmesi, `exit` işlevinin bağımsız değişkeni olarak return değeri ile çağrılmasının eşdeğeridir.

## <a name="opno-locabort-function"></a>abort işlevi

Ayrıca, standart içerme dosyasında \<Stdlib. h > olarak da tanımlanan [abort](../c-runtime-library/reference/abort.md) işlevi bir C++ programı sonlandırır. `exit` ve `abort` arasındaki fark `exit`, C++ çalışma zamanı sonlandırma işlemenin ortaya sürmesidir (genel nesne yıkıcıları çağrılır), ancak `abort` programı hemen sonlandırır. `abort` işlevi, başlatılmış genel statik nesneler için normal yok etme işlemini atlar. Ayrıca, [atexit](../c-runtime-library/reference/atexit.md) işlevi kullanılarak belirtilen özel işlemleri de atlar.

## <a name="opno-locatexit-function"></a>atexit işlevi

Program sonlandırmadan önce yürütülen eylemleri belirtmek için [atexit](../c-runtime-library/reference/atexit.md) işlevini kullanın. **atexit** çağrısı öncesinde başlatılan genel statik nesne, exitişleme işlevinin yürütülmesinden önce yok edilir.

## <a name="opno-locreturn-statement-in-opno-locmain"></a>main return ifade

`main` [return](return-statement-cpp.md) bir deyimin `exit` işlevi çağrılırken işlevsel olarak eşdeğerdir. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Yukarıdaki örnekteki `exit` ve **return** deyimleri işlevsel olarak aynıdır. Ancak, C++ **void** dışında return türlerine sahip işlevlerin bir değer return gerekir. **return** bildiri, `main`bir değer return sağlar.

## <a name="destruction-of-static-objects"></a>Statik nesneleri yok etme

`exit` çağırdığınızda veya `main`bir **return** ifadesini çalıştırdığınızda statik nesneler, başlatma işlemi için ters sırada (varsa `atexit` çağrısından sonra) yok edilir. Aşağıdaki örnek, başlatma ve Temizleme işlemlerinin nasıl çalıştığını gösterir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `sd1` ve `sd2` statik nesneler `main`girişinden önce oluşturulur ve başlatılır. Bu program **return** ifadesini kullanarak sonlandırıldıktan sonra, ilk `sd2` yok edilir ve `sd1`. `ShowData` sınıfı için yıkıcısı bu statik nesnelerle ilişkili dosyaları kapatır.

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

Bu kodu yazmak için başka bir yol da blok kapsamı olan `ShowData` nesneleri bildirmek, kapsam dışına çıktıklarında yok edilmesi gerekir:

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[main işlevi ve komut satırı bağımsız değişkenleri](main-function-command-line-args.md)
