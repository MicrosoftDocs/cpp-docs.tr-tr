---
description: 'Daha fazla bilgi edinin: &lt; iostream&gt;'
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
ms.openlocfilehash: 882b7de8add9339a0580efeac18740205cc175aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323907"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Okumayı ve standart akışlara yazmayı denetleyen nesneler bildirir. Bu, genellikle bir C++ programından giriş ve çıkış yapmanız gereken tek üst bilgi içerir.

## <a name="syntax"></a>Syntax

```cpp
#include <iostream>
```

> [!NOTE]
> \<iostream>Kitaplığı,,, `#include <ios>` `#include <streambuf>` `#include <istream>` ve deyimlerini kullanır `#include <ostream>` .

## <a name="remarks"></a>Açıklamalar

Nesneler iki gruba ayrılır:

- [cin](#cin), [cout](#cout), [cerr](#cerr)ve [CLOG](#clog) bayt yönelimlidir ve geleneksel bir süre içinde aktarım yapar.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr)ve [wclog](#wclog) , geniş bir yönelimlidir ve programın dahili olarak kullandığı geniş karakterlere göre yapılır.

Standart giriş gibi bir akışta belirli işlemleri yaptıktan sonra, aynı akışta farklı bir yönle işlem yapamazsınız. Bu nedenle, bir program, örneğin hem [cin](#cin) hem de [wcin](#wcin)üzerinde birbirlerinin yerine çalışamaz.

Bu üst bilgide belirtilen tüm nesneler bir, bir, bir bir bir bir çeviri biriminde, tanımladığınız herhangi bir statik nesneden önce oluşturulduğunu varsayabilirsiniz \<iostream> . Benzer şekilde, bu nesnelerin, tanımladığınız herhangi bir statik nesne için yıkıcıdan önce yok edildiğini varsayabilirsiniz. (Çıkış akışları, ancak program sonlandırması sırasında temizlenir.) Bu nedenle, program başlamadan önce ve program sonlandırmadan önce standart akışlardan güvenli bir şekilde okuma veya yazma yapabilirsiniz.

Ancak bu garanti evrensel değildir. Statik Oluşturucu, başka bir çeviri birimindeki bir işlevi çağırabilir. Çağrılan işlev, bu üst bilgide belirtilen nesnelerin oluşturulduğunu, çeviri birimlerinin statik oluşturmaya katılması kesin sıra olarak kabul edemiyor. Bu nesneleri böyle bir bağlamda kullanmak için, öncelikle [ios_base:: Init](../standard-library/ios-base-class.md#init)sınıfının bir nesnesini oluşturmanız gerekir.

### <a name="global-stream-objects"></a>Genel akış nesneleri

|Ad|Açıklama|
|-|-|
|[cerr](#cerr)|`cerr`Genel akışı belirtir.|
|[cin](#cin)|`cin`Genel akışı belirtir.|
|[CLOG](#clog)|`clog`Genel akışı belirtir.|
|[cout](#cout)|`cout`Genel akışı belirtir.|
|[wcerr](#wcerr)|`wcerr`Genel akışı belirtir.|
|[wcin](#wcin)|`wcin`Genel akışı belirtir.|
|[wclog](#wclog)|`wclog`Genel akışı belirtir.|
|[wcout](#wcout)|`wcout`Genel akışı belirtir.|

### <a name="cerr"></a><a name="cerr"></a> cerr

Nesnesi, `cerr` içinde belirtilen nesnesiyle ilişkili bir akış arabelleğine çıktıyı denetler `stderr` \<cstdio> .

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne, arabelleğe alınmamış bir bayt akışı olarak standart hata çıktısına eklemeleri denetler. Nesne oluşturulduktan sonra, `cerr.` [](../standard-library/ios-base-class.md#flags) `&` [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) deyiminin ifadesi sıfır değildir ve olur `cerr.tie() == &cout` .

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

### <a name="cin"></a><a name="cin"></a> cin

`cin`Genel akışı belirtir.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Dönüş Değeri

[IStream](../standard-library/istream-typedefs.md#istream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesnesi standart girişten bayt akışı olarak oluşan dışlamaları denetler. Nesne oluşturulduktan sonra, çağrı `cin.` [bağlaması](../standard-library/basic-ios-class.md#tie) `&` [cout](#cout)döndürür.

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

### <a name="clog"></a><a name="clog"></a> CLOG

`clog`Genel akışı belirtir.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, bir bayt akışı olarak standart hata çıktısına ara belleğe eklenen.

#### <a name="example"></a>Örnek

Bir örneği için bkz. [cerr](#cerr) `clog` .

### <a name="cout"></a><a name="cout"></a> cout

`cout`Genel akışı belirtir.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Dönüş Değeri

[Ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart çıktıya bayt akışı olarak Eklenenler.

#### <a name="example"></a>Örnek

Bir örneği için bkz. [cerr](#cerr) `cout` .

### <a name="wcerr"></a><a name="wcerr"></a> wcerr

`wcerr`Genel akışı belirtir.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne, ara belleğe alınmamış standart hata çıktılarına geniş bir akış olarak eklenenleri denetler. Nesne oluşturulduktan sonra, `wcerr.` [](../standard-library/ios-base-class.md#flags) `&` [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) deyiminin bayrak sıfır değildir.

#### <a name="example"></a>Örnek

Bir örneği için bkz. [cerr](#cerr) `wcerr` .

### <a name="wcin"></a><a name="wcin"></a> wcin

`wcin`Genel akışı belirtir.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wıtreaa](../standard-library/istream-typedefs.md#wistream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesnesi standart girişten geniş bir akış olarak dışlamaları denetler. Nesne oluşturulduktan sonra, çağrı `wcin.` [bağlaması](../standard-library/basic-ios-class.md#tie) `&` [wcout](#wcout)döndürür.

#### <a name="example"></a>Örnek

Bir örneği için bkz. [cerr](#cerr) `wcin` .

### <a name="wclog"></a><a name="wclog"></a> wclog

`wclog`Genel akışı belirtir.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart hata çıktısına geniş bir akış olarak ara belleğe Eklenenler.

#### <a name="example"></a>Örnek

Bir örneği için bkz. [cerr](#cerr) `wclog` .

### <a name="wcout"></a><a name="wcout"></a> wcout

`wcout`Genel akışı belirtir.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Dönüş Değeri

[Wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, standart çıktıya geniş bir akış olarak Eklenenler.

#### <a name="example"></a>Örnek

Bir örneği için bkz. [cerr](#cerr) `wcout` .

`CString``wcout` `const wchar_t*` Aşağıdaki örnekte gösterildiği gibi, bir deyimindeki örneklerin öğesine dönüştürülmesi gerekir.

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Daha fazla bilgi için bkz. [temel CString işlemleri](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
