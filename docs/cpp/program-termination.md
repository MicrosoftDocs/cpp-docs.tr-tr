---
title: C++program sonlandırma
ms.date: 12/10/2019
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
ms.openlocfilehash: a0e86cacd951327d39296a183be5ee4fbc36fd15
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301346"
---
# <a name="c-program-termination"></a>C++program sonlandırma

' C++De, bir programdan şu yollarla çıkabilirsiniz:

- [Exit](exit-function.md) işlevini çağırın.
- [Abort](abort-function.md) işlevini çağırın.
- `main`bir [dönüş](return-statement-cpp.md) ekstresi yürütün.

## <a name="exit-function"></a>exit işlevi

\<Stdlib. h > içinde belirtilen [Çıkış](../c-runtime-library/reference/exit-exit-exit.md) işlevi bir C++ programı sonlandırır. `exit` için bir bağımsız değişken olarak sağlanan değer, programın dönüş kodu veya çıkış kodu olarak işletim sistemine döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir. Programınızın başarısını veya başarısızlığını göstermek için \<Stdlib. h > içinde de tanımlanan sabitleri EXIT_FAILURE ve EXIT_SUCCESS kullanabilirsiniz.

`main` işlevden **Return** ifadesinin verilmesi, bağımsız değişkeni olarak dönüş değeri ile `exit` işlevi çağırmaya eşdeğerdir.

## <a name="abort-function"></a>abort işlevi

Ayrıca, standart içerme dosyasında \<Stdlib. h > olarak da belirtilen [Abort](../c-runtime-library/reference/abort.md) işlevi bir C++ programı sonlandırır. `exit` ve `abort` arasındaki fark `exit`, C++ çalışma zamanı sonlandırma işlemenin ortaya sürmesidir (genel nesne yıkıcıları çağrılır), ancak `abort` programı hemen sonlandırır. `abort` işlevi, başlatılmış genel statik nesneler için normal yok etme işlemini atlar. Ayrıca, [atexit](../c-runtime-library/reference/atexit.md) işlevi kullanılarak belirtilen özel işlemleri de atlar.

## <a name="atexit-function"></a>atexit işlevi

Program sonlandırmadan önce yürütülen eylemleri belirtmek için [atexit](../c-runtime-library/reference/atexit.md) işlevini kullanın. Herhangi bir genel statik nesne, **atexcall** çağrısından önce başlatılmaz ve çıkış işleme işlevinin yürütülmesinden önce yok edilir.

## <a name="return-statement-in-main"></a>Main içinde Return deyimleri

`main` bir [Return](return-statement-cpp.md) ifadesinin verilmesi, `exit` işlevi çağırma ile işlevsel olarak eşdeğerdir. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Yukarıdaki örnekteki `exit` ve **Return** deyimleri işlevsel olarak aynıdır. Ancak, C++ **void** dışında bir dönüş türü olan işlevlerin bir değer döndürmesi gerekir. **Return** deyimleri `main`bir değer döndürbırakmanıza olanak tanır.

## <a name="destruction-of-static-objects"></a>Statik nesneleri yok etme

`main`bir **dönüş** ifadesini çağırdığınızda veya `exit` çalıştırdığınızda statik nesneler, başlatma işlemi için ters sırada (varsa `atexit` çağrısından sonra) yok edilir. Aşağıdaki örnek, başlatma ve Temizleme işlemlerinin nasıl çalıştığını gösterir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `sd1` ve `sd2` statik nesneler `main`girişinden önce oluşturulur ve başlatılır. Bu program **Return** ifadesini kullanarak sonlandırıldıktan sonra ilk `sd2` yok edilir ve sonra `sd1`. `ShowData` sınıfı için yıkıcısı bu statik nesnelerle ilişkili dosyaları kapatır.

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

[main: Program Başlatma](main-program-startup.md)