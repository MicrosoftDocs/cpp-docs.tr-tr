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
ms.openlocfilehash: 03afb777dc3926284cf0dc625e94a716ecdf5413
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375353"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Okuma ve yazmayı standart akışlara denetleyen nesneleri bildirir. Bu genellikle bir C++ programından giriş ve çıktı yapmanız gereken tek üstbilgidir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iostream>
```

> [!NOTE]
> \<Iostream> kitaplığı `#include <ios>` `#include <streambuf>`, `#include <istream>`, `#include <ostream>` , ve ifadeleri kullanır.

## <a name="remarks"></a>Açıklamalar

Nesneler iki gruba ayrılır:

- [cin](#cin), [cout](#cout), [cerr](#cerr), ve [tıkanan](#clog) bayt odaklı, geleneksel bayt-at-a-time transferleri yapıyor.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr), ve [wclog](#wclog) geniş odaklı, çeviri ve geniş karakterler den program dahili manipüle.

Standart giriş gibi bir akışta belirli işlemleri yaptıktan sonra, aynı akışta farklı bir yönlendirme işlemi yapamazsınız. Bu nedenle, bir program [cin](#cin) ve [wcin](#wcin)hem de birbirlerinin yerine çalışamaz, örneğin.

Bu üstbilgide bildirilen tüm nesneler kendine özgü bir özelliği paylaşır — bunların tanımladığınız statik nesnelerden önce, iostream> içeren \<bir çeviri biriminde oluşturulduklarını varsayabilirsiniz. Aynı şekilde, bu nesnelerin tanımladığınız bu tür statik nesneler için yıkıcılardan önce yok olmadığını varsayabilirsiniz. (Çıktı akışları, ancak, program sonlandırma sırasında kızartılır.) Bu nedenle, program başlatmadan önce ve program sonlandırmasonrasında standart akışlardan güvenle okuyabilir veya standart akışlara yazabilirsiniz.

Ancak bu garanti evrensel değildir. Statik bir oluşturucu başka bir çeviri biriminde bir işlev çağırabilir. Çağrılan işlev, çeviri birimlerinin statik yapıya katılma sırası belirsiz göz önüne alındığında, bu üstbilgide bildirilen nesnelerin oluşturuldurıldığını varsayamaz. Bu nesneleri böyle bir bağlamda kullanmak için, öncelikle sınıf ios_base bir nesne oluşturmanız [gerekir::Init](../standard-library/ios-base-class.md#init).

### <a name="global-stream-objects"></a>Küresel Akış Nesneleri

|||
|-|-|
|[cerr](#cerr)|`cerr` Genel akışı belirtir.|
|[cin](#cin)|`cin` Genel akışı belirtir.|
|[Zarar](#clog)|`clog` Genel akışı belirtir.|
|[Cout](#cout)|`cout` Genel akışı belirtir.|
|[wcerr](#wcerr)|`wcerr` Genel akışı belirtir.|
|[wcin](#wcin)|`wcin` Genel akışı belirtir.|
|[wclog](#wclog)|`wclog` Genel akışı belirtir.|
|[wcout](#wcout)|`wcout` Genel akışı belirtir.|

### <a name="cerr"></a><a name="cerr"></a>cerr

Nesne, `cerr` cstdio>'da `stderr` \<bildirilen nesneyle ilişkili bir akış arabelleği çıkışı denetler.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [ostream nesnesi.](../standard-library/ostream-typedefs.md#ostream)

#### <a name="remarks"></a>Açıklamalar

Nesne, arabelleğe alamayan eklemeleri standart hata çıkışına bayt akışı olarak denetler. Nesne oluşturulduktan sonra, `cerr.`ifade `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfırsız `cerr.tie() == &cout`ve . [flags](../standard-library/ios-base-class.md#flags)

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

### <a name="cin"></a><a name="cin"></a>cin

`cin` Genel akışı belirtir.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [istream nesnesi.](../standard-library/istream-typedefs.md#istream)

#### <a name="remarks"></a>Açıklamalar

Nesne, standart girişten çıkarmaları bayt akışı olarak denetler. Nesne oluşturulduktan sonra, `cin.`çağrı [kravatı](../standard-library/basic-ios-class.md#tie) `&` [cout](#cout)döndürür.

#### <a name="example"></a>Örnek

Bu örnekte, `cin` sayısal olmayan karakterlerle karşılaştığında akıştaki başarısız biti ayarlar. Program başarısız biti temizler ve geçersiz karakteri devam etmek için akıştan şeritler.

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

### <a name="clog"></a><a name="clog"></a>Zarar

`clog` Genel akışı belirtir.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [ostream nesnesi.](../standard-library/ostream-typedefs.md#ostream)

#### <a name="remarks"></a>Açıklamalar

Nesne, arabellekli eklemeleri standart hata çıkışına bayt akışı olarak denetler.

#### <a name="example"></a>Örnek

Kullanma `clog`örneği için [cerr'a](#cerr) bakın.

### <a name="cout"></a><a name="cout"></a>Cout

`cout` Genel akışı belirtir.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [ostream nesnesi.](../standard-library/ostream-typedefs.md#ostream)

#### <a name="remarks"></a>Açıklamalar

Nesne, standart çıktıya bayt akışı olarak eklemeleri denetler.

#### <a name="example"></a>Örnek

Kullanma `cout`örneği için [cerr'a](#cerr) bakın.

### <a name="wcerr"></a><a name="wcerr"></a>wcerr

`wcerr` Genel akışı belirtir.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [wostream nesnesi.](../standard-library/ostream-typedefs.md#wostream)

#### <a name="remarks"></a>Açıklamalar

Nesne, geniş bir akış olarak standart hata çıkışına arabelleğe alamayan eklemeleri denetler. Nesne oluşturulduktan sonra, `wcerr.`ifade [unitbuf](../standard-library/ios-functions.md#unitbuf) [flags](../standard-library/ios-base-class.md#flags) `&` sıfırsız dır.

#### <a name="example"></a>Örnek

Kullanma `wcerr`örneği için [cerr'a](#cerr) bakın.

### <a name="wcin"></a><a name="wcin"></a>wcin

`wcin` Genel akışı belirtir.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [wistream nesnesi.](../standard-library/istream-typedefs.md#wistream)

#### <a name="remarks"></a>Açıklamalar

Nesne, standart girişten çıkarmaları geniş bir akış olarak denetler. Nesne oluşturulduktan sonra, `wcin.`çağrı [kravat](../standard-library/basic-ios-class.md#tie) `&` [wcout](#wcout)döndürür.

#### <a name="example"></a>Örnek

Kullanma `wcin`örneği için [cerr'a](#cerr) bakın.

### <a name="wclog"></a><a name="wclog"></a>wclog

`wclog` Genel akışı belirtir.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [wostream nesnesi.](../standard-library/ostream-typedefs.md#wostream)

#### <a name="remarks"></a>Açıklamalar

Nesne, geniş bir akış olarak standart hata çıkışına arabelleğe alınan eklemeleri denetler.

#### <a name="example"></a>Örnek

Kullanma `wclog`örneği için [cerr'a](#cerr) bakın.

### <a name="wcout"></a><a name="wcout"></a>wcout

`wcout` Genel akışı belirtir.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Dönüş Değeri

Bir [wostream nesnesi.](../standard-library/ostream-typedefs.md#wostream)

#### <a name="remarks"></a>Açıklamalar

Nesne, standart çıktıya geniş bir akış olarak eklemeleri denetler.

#### <a name="example"></a>Örnek

Kullanma `wcout`örneği için [cerr'a](#cerr) bakın.

`CString`bir `wcout` deyimdeki `const wchar_t*`örnekler, aşağıdaki örnekte gösterildiği gibi,

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Daha fazla bilgi için [Temel CString İşlemleri'ne](../atl-mfc-shared/basic-cstring-operations.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
