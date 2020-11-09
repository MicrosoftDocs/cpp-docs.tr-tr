---
title: '`<ios>` tür tanımları'
description: '`<ios>`Eski kitaplıktan sınıfını destekleyen C++ Standart Şablon kitaplığı (STL) tür tanımları öğesini açıklar `ios` `iostream` .'
ms.date: 11/06/2020
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.openlocfilehash: 4af9636ab3317e7b81eb73dc74aef065b1287e21
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381642"
---
# <a name="ios-typedefs"></a>`<ios>` tür tanımları

## `ios`

`ios`Eski kitaplıktan sınıfını destekler `iostream` .

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Açıklamalar

Tür, [`basic_ios`](../standard-library/basic-ios-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş olan sınıf şablonu için bir eş anlamlıdır.

## `streamoff`

İç işlemleri destekler.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Açıklamalar

Tür işaretli bir tamsayıdır. Stream konumlandırma işlemlerinde bayt sapmasını depolayabilen bir nesneyi tanımlar. Gösteriminin en az 32 değer bitleri vardır. Akış içinde rastgele bir bayt konumunu temsil etmek için yeterince büyük değildir. Değer `streamoff(-1)` genellikle hatalı bir sapmayı gösterir.

## `streampos`

Arabellek işaretçisinin veya dosya işaretçisinin geçerli konumunu tutar.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Açıklamalar

Tür> için bir eş anlamlı [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t` .

### <a name="example"></a>Örnek

```cpp
// ios_streampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ofstream x( "iostream.txt" );
   x << "testing";
   streampos y = x.tellp( );
   cout << streamoff(y) << '\n';
}
```

```Output
7
```

## `streamsize`

Akışın boyutunu gösterir.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Açıklamalar

Türü, çeşitli akış işlemlerinde yer alan öğelerin sayısını depolayabilen bir nesneyi tanımlayan işaretli bir tamsayıdır. Gösteriminin en az 16 bit vardır. Akış içinde rastgele bir bayt konumunu temsil etmek için yeterince büyük değildir.

### <a name="example"></a>Örnek

Aşağıdaki programı derleyip çalıştırdıktan sonra, `test.txt` ayarın etkisini görmek için dosyaya bakın `streamsize` .

```cpp
// ios_streamsize.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   char a[16] = "any such text";
   ofstream x( "test.txt" );
   streamsize y = 6;
   x.write( a, y );
}
```

## `wios`

`wios`Eski kitaplıktan sınıfını destekler `iostream` .

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Açıklamalar

Tür, [`basic_ios`](../standard-library/basic-ios-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş olan sınıf şablonu için bir eş anlamlıdır.

## `wstreampos`

Arabellek işaretçisinin veya dosya işaretçisinin geçerli konumunu tutar.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Açıklamalar

Tür> için bir eş anlamlı [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t` .

### <a name="example"></a>Örnek

```cpp
// ios_wstreampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   wofstream xw( "wiostream.txt" );
   xw << L"testing";
   wstreampos y = xw.tellp( );
   cout << y << endl;
}
```

```Output
7
```
