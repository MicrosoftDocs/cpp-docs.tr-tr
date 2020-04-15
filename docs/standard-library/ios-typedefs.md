---
title: '&lt;ios&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
ms.openlocfilehash: 0f63f65fb4c10fbe2ad538852222e6468b9061d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375397"
---
# <a name="ltiosgt-typedefs"></a>&lt;ios&gt; typedefs

## <a name="ios"></a><a name="ios"></a>Ios

Eski iostream kitaplığından ios sınıfını destekler.

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip **tür char** öğeleri için özelleştirilmiş sınıf [şablonu basic_ios](../standard-library/basic-ios-class.md)eşanlamlıdır.

## <a name="streamoff"></a><a name="streamoff"></a>Streamoff

Dahili işlemleri destekler.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Açıklamalar

Tür, çeşitli akış konumlandırma işlemlerinde yer alan bir bayt ofset depolayabilir bir nesne açıklayan imzalı bir tamsayıdır. Temsili en az 32 değer biti vardır. Akış içinde rasgele bir bayt konumunu temsil edecek kadar büyük olması gerekmez. Değer `streamoff(-1)` genellikle hatalı bir mahsup gösterir.

## <a name="streampos"></a><a name="streampos"></a>akış

Arabellek işaretçisinin veya dosya işaretçisinin geçerli konumunu tutar.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Açıklamalar

Türü [fpos](../standard-library/fpos-class.md) <  `mbstate_t`> için eşanlamlıdır.

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
   cout << y << endl;
}
```

```Output
7
```

## <a name="streamsize"></a><a name="streamsize"></a>akış boyutu

Akışın boyutunu gösterir.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Açıklamalar

Tür, çeşitli akış işlemlerinde yer alan öğe sayısının sayısını depolayabilen bir nesneyi açıklayan imzalı bir tamsayıdır. Temsili en az 16 bit vardır. Akış içinde rasgele bir bayt konumunu temsil edecek kadar büyük olması gerekmez.

### <a name="example"></a>Örnek

Aşağıdaki programı derleyip çalıştırdıktan sonra, ayarın `streamsize`etkisini görmek için dosya test.txt'ye bakın.

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

## <a name="wios"></a><a name="wios"></a>wios

Eski iostream kitaplığından wios sınıfını destekler.

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip **wchar_t** türü öğeleri için özelleştirilmiş sınıf [şablonu basic_ios](../standard-library/basic-ios-class.md)eşanlamlıdır.

## <a name="wstreampos"></a><a name="wstreampos"></a>wstreampos

Arabellek işaretçisinin veya dosya işaretçisinin geçerli konumunu tutar.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Açıklamalar

Türü [fpos](../standard-library/fpos-class.md) <  `mbstate_t`> için eşanlamlıdır.

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
