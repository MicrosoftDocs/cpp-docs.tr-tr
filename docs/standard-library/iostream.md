---
title: '&lt;iostream&gt;'
ms.date: 09/20/2017
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
ms.openlocfilehash: 2906e802072c43a93c59ca40d15e032adeeeef97
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418918"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Okumayı ve standart akışlara yazmayı denetleyen nesneler bildirir. Bu, genellikle bir C++ programdan giriş ve çıkış yapmanız gereken tek üst bilgi içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iostream>
```

> [!NOTE]
> \<iostream > kitaplığı `#include <ios>`, `#include <streambuf>`, `#include <istream>`ve `#include <ostream>` deyimlerini kullanır.

## <a name="remarks"></a>Açıklamalar

Nesneler iki gruba ayrılır:

- [cin](#cin), [cout](#cout), [cerr](#cerr)ve [CLOG](#clog) bayt yönelimlidir ve geleneksel bir süre içinde aktarım yapar.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr)ve [wclog](#wclog) , geniş bir yönelimlidir ve programın dahili olarak kullandığı geniş karakterlere göre yapılır.

Standart giriş gibi bir akışta belirli işlemleri yaptıktan sonra, aynı akışta farklı bir yönle işlem yapamazsınız. Bu nedenle, bir program, örneğin hem [cin](#cin) hem de [wcin](#wcin)üzerinde birbirlerinin yerine çalışamaz.

Bu üst bilgide belirtilen tüm nesneler bir, bir, bir, \<iostream > içeren bir çeviri biriminde, tanımladığınız herhangi bir statik nesneden önce oluşturulduğunu varsayabilirsiniz. Benzer şekilde, bu nesnelerin, tanımladığınız herhangi bir statik nesne için yıkıcıdan önce yok edildiğini varsayabilirsiniz. (Çıkış akışları, ancak program sonlandırması sırasında temizlenir.) Bu nedenle, program başlamadan önce ve program sonlandırmadan önce standart akışlardan güvenli bir şekilde okuma veya yazma yapabilirsiniz.

Ancak bu garanti evrensel değildir. Statik Oluşturucu, başka bir çeviri birimindeki bir işlevi çağırabilir. Çağrılan işlev, bu üst bilgide belirtilen nesnelerin oluşturulduğunu, çeviri birimlerinin statik oluşturmaya katılması kesin sıra olarak kabul edemiyor. Bu nesneleri böyle bir bağlamda kullanmak için, öncelikle [ios_base:: Init](../standard-library/ios-base-class.md#init)sınıfının bir nesnesini oluşturmanız gerekir.

### <a name="global-stream-objects"></a>Genel akış nesneleri

|||
|-|-|
|[cerr](#cerr)|`cerr` genel akışı belirtir.|
|[cin](#cin)|`cin` genel akışı belirtir.|
|[CLOG](#clog)|`clog` genel akışı belirtir.|
|[cout](#cout)|`cout` genel akışı belirtir.|
|[wcerr](#wcerr)|`wcerr` genel akışı belirtir.|
|[wcin](#wcin)|`wcin` genel akışı belirtir.|
|[wclog](#wclog)|`wclog` genel akışı belirtir.|
|[wcout](#wcout)|`wcout` genel akışı belirtir.|

###  <a name="cerr"></a>cerr

Nesne `cerr`, çıktıyı \<cstdio > tarafından belirtilen nesne `stderr`ilişkili bir akış arabelleğine denetler.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne, arabelleğe alınmamış bir bayt akışı olarak standart hata çıktısına eklemeleri denetler. Nesne oluşturulduktan sonra, `&` [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) `cerr.`[bayrakları](../standard-library/ios-base-class.md#flags) sıfır dışında ve `cerr.tie() == &cout`.

#### <a name="example"></a>Örnek

```cpp
// iostream_cerr.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void TestWide( )
{
   int i = 0;
   wcout << L"Enter a number: ";
   wcin >> i;
   wcerr << L"test for wcerr" << endl;
   wclog << L"test for wclog" << endl;
}

int main( )
{
   int i = 0;
   cout << "Enter a number: ";
   cin >> i;
   cerr << "test for cerr" << endl;
   clog << "test for clog" << endl;
   TestWide( );
}
```

###  <a name="cin"></a>cin

`cin` genel akışı belirtir.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Dönüş Değeri

[IStream](../standard-library/istream-typedefs.md#istream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesnesi standart girişten bayt akışı olarak oluşan dışlamaları denetler. Nesne oluşturulduktan sonra [, `cin.`bağlama](../standard-library/basic-ios-class.md#tie) çağrısı `&`[cout](#cout)döndürür.

#### <a name="example"></a>Örnek

Bu örnekte, `cin` sayısal olmayan karakterlere geldiğinde akıştaki başarısız bitini ayarlar. Program hata bitini temizler ve devam etmek için akıştan geçersiz karakteri kaldırır.

```cpp
// iostream_cin.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
   int x;
   cout << "enter choice:";
   cin >> x;
   while (x < 1 || x > 4)
   {
      cout << "Invalid choice, try again:";
      cin >> x;
      // not a numeric character, probably
      // clear the failure and pull off the non-numeric character
      if (cin.fail())
      {
         cin.clear();
         char c;
         cin >> c;
      }
   }
}
```

```Output
2
```

###  <a name="clog"></a>CLOG

`clog` genel akışı belirtir.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, bir bayt akışı olarak standart hata çıktısına ara belleğe eklenen.

#### <a name="example"></a>Örnek

`clog`kullanımı örneği için bkz. [cerr](#cerr) .

###  <a name="cout"></a>cout

`cout` genel akışı belirtir.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart çıktıya bayt akışı olarak Eklenenler.

#### <a name="example"></a>Örnek

`cout`kullanımı örneği için bkz. [cerr](#cerr) .

### <a name="wcerr"></a>wcerr

`wcerr` genel akışı belirtir.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne, ara belleğe alınmamış standart hata çıktılarına geniş bir akış olarak eklenenleri denetler. Nesne oluşturulduktan sonra, `&` [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) `wcerr.`[bayrakları](../standard-library/ios-base-class.md#flags) sıfır dışında bir ifade olur.

#### <a name="example"></a>Örnek

`wcerr`kullanımı örneği için bkz. [cerr](#cerr) .

### <a name="wcin"></a>wcin

`wcin` genel akışı belirtir.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wıtreaa](../standard-library/istream-typedefs.md#wistream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesnesi standart girişten geniş bir akış olarak dışlamaları denetler. Nesne oluşturulduktan sonra, [çağrı `wcin.`bağlama](../standard-library/basic-ios-class.md#tie) `&`[wcout](#wcout)döndürür.

#### <a name="example"></a>Örnek

`wcin`kullanımı örneği için bkz. [cerr](#cerr) .

### <a name="wclog"></a>wclog

`wclog` genel akışı belirtir.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart hata çıktısına geniş bir akış olarak ara belleğe Eklenenler.

#### <a name="example"></a>Örnek

`wclog`kullanımı örneği için bkz. [cerr](#cerr) .

### <a name="wcout"></a>wcout

`wcout` genel akışı belirtir.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart çıktıya geniş bir akış olarak Eklenenler.

#### <a name="example"></a>Örnek

`wcout`kullanımı örneği için bkz. [cerr](#cerr) .

Aşağıdaki örnekte gösterildiği gibi, bir `wcout` deyimindeki `CString` örneklerin `const wchar_t*`olarak dönüştürülmesi gerekir.

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Daha fazla bilgi için bkz. [temel CString işlemleri](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
