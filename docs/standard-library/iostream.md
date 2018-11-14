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
ms.openlocfilehash: 18d6a8517d71cfa9c7e17a45c97f77977ec778f0
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522408"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Okuma ve yazma için standart akışlarına denetim nesnesi bildirir. Bu genellikle giriş ve çıkış bir C++ programı gerçekleştirmek için eklemeniz gereken yalnızca üst bilgi olur.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iostream>
```

## <a name="remarks"></a>Açıklamalar

Nesneleri ikiye ayrılır:

- [cin](#cin), [cout](#cout), [cerr](#cerr), ve [clog](#clog) olan yönelik, bayt geleneksel bir kerede bir bayt aktarımları gerçekleştiriliyor.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr), ve [wclog](#wclog) program dahili olarak yöneten geniş karakterler gelen ve giden çevirme geniş, yerleştirilir.

Standart giriş gibi bir akış üzerinde belirli işlemlerin gerçekleştirilmesi sonra aynı akışta farklı yön ayarına işlemleri gerçekleştiremezsiniz. Bu nedenle, bir program birbirinin yerine hem de çalışamaz [cin](#cin) ve [wcin](#wcin), örneğin.

Tüm nesneleri bildirilen bu üst bilgi paylaşımına özgü bir özellik — bunlar oluşturulması, tanımlayın, içeren bir çeviri biriminde herhangi bir statik nesne önce varsayabilirsiniz \<iostream >. Eşit şekilde, bu nesneler için tanımladığınız gibi statik nesnelerin yok ediciler önce yok edilmez varsayabilirsiniz. (Çıkış akışları ancak program sonlandırma sırasında temizlenir.) Bu nedenle, güvenli bir şekilde okuyabilir ya da önce program başlatma ve program sonlandırma sonra standart akışlara yazma.

Bu garanti ancak universal, değildir. Statik Oluşturucu başka bir çeviri biriminde bir işlevi çağırabilir. Çağrılan işlev bu üstbilgisinde bildirilen nesneler, hangi çeviri birimleri statik oluşturma, katılmak belirsiz sırasını verilen yapılandırılmış olduğunu varsayamazsınız. Bu nesneler bu tür bir bağlamda kullanmak için önce sınıfın bir nesnesi oluşturmalıdır [ios_base::Init](../standard-library/ios-base-class.md#init).

### <a name="global-stream-objects"></a>Genel Stream nesneleri

|||
|-|-|
|[cerr](#cerr)|Belirtir `cerr` genel akışı.|
|[cin](#cin)|Belirtir `cin` genel akışı.|
|[clog](#clog)|Belirtir `clog` genel akışı.|
|[cout](#cout)|Belirtir `cout` genel akışı.|
|[wcerr](#wcerr)|Belirtir `wcerr` genel akışı.|
|[wcin](#wcin)|Belirtir `wcin` genel akışı.|
|[wclog](#wclog)|Belirtir `wclog` genel akışı.|
|[wcout](#wcout)|Belirtir `wcout` genel akışı.|

###  <a name="cerr"></a>  cerr

Nesne `cerr` nesnesiyle ilişkili bir akış arabelleğinin çıktısına denetimleri `stderr`bildirilen \<cstdio >.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [ostream](../standard-library/ostream-typedefs.md#ostream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne, bayt akışı olarak standart hata çıktısı arabellekten çıkarılan eklemelerin denetler. Nesnesi oluşturulduktan sonra ifade `cerr.` [bayrakları](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfır ve `cerr.tie() == &cout`.

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

###  <a name="cin"></a>  cin

Belirtir `cin` genel akışı.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [istream](../standard-library/istream-typedefs.md#istream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne ayıklamalar standart girişten alınan bayt akışı olarak denetler. Nesnesi oluşturulduktan sonra çağrı `cin.` [tie](../standard-library/basic-ios-class.md#tie) döndürür `&` [cout](#cout).

#### <a name="example"></a>Örnek

Bu örnekte, `cin` sayısal olmayan karakterler karşılaştığında akışta bit başarısız ayarlar. Program başarısız bit temizler ve devam etmek için akışından geçersiz karakteri kaldırır.

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

###  <a name="clog"></a>  clog

Belirtir `clog` genel akışı.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [ostream](../standard-library/ostream-typedefs.md#ostream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, bayt akışı olarak standart hata çıktısı eklemelerin arabelleğe alındı.

#### <a name="example"></a>Örnek

Bkz: [cerr](#cerr) kullanma örneği için `clog`.

###  <a name="cout"></a>  cout

Belirtir `cout` genel akışı.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [ostream](../standard-library/ostream-typedefs.md#ostream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne eklemeler standart çıktıya bayt akışı olarak denetler.

#### <a name="example"></a>Örnek

Bkz: [cerr](#cerr) kullanma örneği için `cout`.

###  <a name="wcerr"></a>  wcerr

Belirtir `wcerr` genel akışı.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Dönüş Değeri

A [wostream](../standard-library/ostream-typedefs.md#wostream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesnesi, geniş bir akış olarak standart hata çıktısı arabellekten çıkarılan eklemelerin denetler. Nesnesi oluşturulduktan sonra ifade `wcerr.` [bayrakları](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfır değil.

#### <a name="example"></a>Örnek

Bkz: [cerr](#cerr) kullanma örneği için `wcerr`.

###  <a name="wcin"></a>  wcin

Belirtir `wcin` genel akışı.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Dönüş Değeri

A [wistream](../standard-library/istream-typedefs.md#wistream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne ayıklamalar standart girişten alınan geniş bir akış olarak denetler. Nesnesi oluşturulduktan sonra çağrı `wcin.` [tie](../standard-library/basic-ios-class.md#tie) döndürür `&` [wcout](#wcout).

#### <a name="example"></a>Örnek

Bkz: [cerr](#cerr) kullanma örneği için `wcin`.

###  <a name="wclog"></a>  wclog

Belirtir `wclog` genel akışı.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Dönüş Değeri

A [wostream](../standard-library/ostream-typedefs.md#wostream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne denetimleri, geniş bir akış olarak standart hata çıktısı eklemelerin arabelleğe alındı.

#### <a name="example"></a>Örnek

Bkz: [cerr](#cerr) kullanma örneği için `wclog`.

###  <a name="wcout"></a>  wcout

Belirtir `wcout` genel akışı.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Dönüş Değeri

A [wostream](../standard-library/ostream-typedefs.md#wostream) nesne.

#### <a name="remarks"></a>Açıklamalar

Nesne eklemeler standart çıktıya geniş bir akış olarak denetler.

#### <a name="example"></a>Örnek

Bkz: [cerr](#cerr) kullanma örneği için `wcout`.

`CString` içinde örnekler bir `wcout` deyimi cast, için `const wchar_t*`, aşağıdaki örnekte gösterildiği gibi.

```

    CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;
```

Daha fazla bilgi için [temel CString işlemleri](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
