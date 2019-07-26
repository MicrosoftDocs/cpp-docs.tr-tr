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
ms.openlocfilehash: 471b149eba32d163e6e3e54e1c2820bbe0b94133
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449036"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Okumayı ve standart akışlara yazmayı denetleyen nesneler bildirir. Bu, genellikle bir C++ programdan giriş ve çıkış yapmanız gereken tek üst bilgi içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iostream>
```

> [!NOTE]
> `#include <ios>` `#include <streambuf>`İostream > Kitaplığı ,`#include <istream>`,, ve`#include <ostream>`deyimlerinikullanır. \<

## <a name="remarks"></a>Açıklamalar

Nesneler iki gruba ayrılır:

- [cin](#cin), [cout](#cout), [cerr](#cerr)ve [CLOG](#clog) bayt yönelimlidir ve geleneksel bir süre içinde aktarım yapar.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr)ve [wclog](#wclog) , geniş bir yönelimlidir ve programın dahili olarak kullandığı geniş karakterlere göre yapılır.

Standart giriş gibi bir akışta belirli işlemleri yaptıktan sonra, aynı akışta farklı bir yönle işlem yapamazsınız. Bu nedenle, bir program, örneğin hem [cin](#cin) hem de [wcin](#wcin)üzerinde birbirlerinin yerine çalışamaz.

Bu üst bilgide belirtilen tüm nesneler bir, bir bir bir bir bir özellik paylaşır. Bu, tanımlandığınız herhangi bir statik nesneden önce, ıostream > içeren \<bir çeviri biriminde oluşturulduğunu varsayabilirsiniz. Benzer şekilde, bu nesnelerin, tanımladığınız herhangi bir statik nesne için yıkıcıdan önce yok edildiğini varsayabilirsiniz. (Çıkış akışları, ancak program sonlandırması sırasında temizlenir.) Bu nedenle, program başlamadan önce ve program sonlandırmadan önce standart akışlardan güvenli bir şekilde okuma veya yazma yapabilirsiniz.

Ancak bu garanti evrensel değildir. Statik Oluşturucu, başka bir çeviri birimindeki bir işlevi çağırabilir. Çağrılan işlev, bu üst bilgide belirtilen nesnelerin oluşturulduğunu, çeviri birimlerinin statik oluşturmaya katılması kesin sıra olarak kabul edemiyor. Bu nesneleri böyle bir bağlamda kullanmak için, önce [ios_base:: Init](../standard-library/ios-base-class.md#init)sınıfının bir nesnesini oluşturmanız gerekir.

### <a name="global-stream-objects"></a>Genel akış nesneleri

|||
|-|-|
|[cerr](#cerr)|`cerr` Genel akışı belirtir.|
|[cin](#cin)|`cin` Genel akışı belirtir.|
|[CLOG](#clog)|`clog` Genel akışı belirtir.|
|[cout](#cout)|`cout` Genel akışı belirtir.|
|[wcerr](#wcerr)|`wcerr` Genel akışı belirtir.|
|[wcin](#wcin)|`wcin` Genel akışı belirtir.|
|[wclog](#wclog)|`wclog` Genel akışı belirtir.|
|[wcout](#wcout)|`wcout` Genel akışı belirtir.|

###  <a name="cerr"></a>cerr

Nesnesi `cerr` , cstdio > içinde \<belirtilen nesneyle `stderr`ilişkili bir akış arabelleğine çıktıyı denetler.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne, arabelleğe alınmamış bir bayt akışı olarak standart hata çıktısına eklemeleri denetler. Nesne oluşturulduktan sonra, [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) deyiminin ifadesi `cerr.` [](../standard-library/ios-base-class.md#flags) `&` sıfır değildir ve `cerr.tie() == &cout`olur.

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

`cin` Genel akışı belirtir.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Dönüş Değeri

[IStream](../standard-library/istream-typedefs.md#istream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesnesi standart girişten bayt akışı olarak oluşan dışlamaları denetler. Nesne oluşturulduktan sonra `cin.`, çağrı [bağlaması](../standard-library/basic-ios-class.md#tie) `&` [cout](#cout)döndürür.

#### <a name="example"></a>Örnek

Bu örnekte, `cin` sayısal olmayan karakterler üzerine geldiğinde akıştaki başarısız bitini ayarlar. Program hata bitini temizler ve devam etmek için akıştan geçersiz karakteri kaldırır.

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

`clog` Genel akışı belirtir.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, bir bayt akışı olarak standart hata çıktısına ara belleğe eklenen.

#### <a name="example"></a>Örnek

Bir örneği `clog`için bkz. [cerr](#cerr) .

###  <a name="cout"></a>cout

`cout` Genel akışı belirtir.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart çıktıya bayt akışı olarak Eklenenler.

#### <a name="example"></a>Örnek

Bir örneği `cout`için bkz. [cerr](#cerr) .

### <a name="wcerr"></a>wcerr

`wcerr` Genel akışı belirtir.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne, ara belleğe alınmamış standart hata çıktılarına geniş bir akış olarak eklenenleri denetler. Nesne `wcerr.`oluşturulduktan sonra, [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) deyiminin [bayrak](../standard-library/ios-base-class.md#flags) `&` sıfır değildir.

#### <a name="example"></a>Örnek

Bir örneği `wcerr`için bkz. [cerr](#cerr) .

### <a name="wcin"></a>wcin

`wcin` Genel akışı belirtir.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wıtreaa](../standard-library/istream-typedefs.md#wistream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesnesi standart girişten geniş bir akış olarak dışlamaları denetler. Nesne oluşturulduktan sonra `wcin.`, çağrı [bağlaması](../standard-library/basic-ios-class.md#tie) [wcout](#wcout)döndürür `&`.

#### <a name="example"></a>Örnek

Bir örneği `wcin`için bkz. [cerr](#cerr) .

### <a name="wclog"></a>wclog

`wclog` Genel akışı belirtir.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart hata çıktısına geniş bir akış olarak ara belleğe Eklenenler.

#### <a name="example"></a>Örnek

Bir örneği `wclog`için bkz. [cerr](#cerr) .

### <a name="wcout"></a>wcout

`wcout` Genel akışı belirtir.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart çıktıya geniş bir akış olarak Eklenenler.

#### <a name="example"></a>Örnek

Bir örneği `wcout`için bkz. [cerr](#cerr) .

`CString`Aşağıdaki örnekte gösterildiği `wcout` gibi, bir deyimindeki örneklerin `const wchar_t*`öğesine dönüştürülmesi gerekir.

```
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Daha fazla bilgi için bkz. [temel CString işlemleri](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
