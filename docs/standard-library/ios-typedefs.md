---
title: '&lt;iOS&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
ms.openlocfilehash: 20bffbeb7720274302633c5dda9e6364c06d5b54
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418967"
---
# <a name="ltiosgt-typedefs"></a>&lt;iOS&gt; tür tanımları

## <a name="ios"></a>işlemine

Eski ıostream kitaplığından iOS sınıfını destekler.

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş [basic_ios](../standard-library/basic-ios-class.md)sınıf şablonu için bir eş anlamlı.

## <a name="streamoff"></a>streamoff

İç işlemleri destekler.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Açıklamalar

Tür, çeşitli akış konumlandırma işlemlerinde yer alan bayt sapmasını depolayabilen bir nesneyi tanımlayan işaretli bir tamsayıdır. Gösteriminin en az 32 değer bitleri vardır. Bir akış içinde rastgele bir bayt konumunu temsil etmek için yeterince büyük değildir. Değer `streamoff(-1)` genellikle hatalı bir sapmayı gösterir.

## <a name="streampos"></a>streampos

Arabellek işaretçisinin veya dosya işaretçisinin geçerli konumunu tutar.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Açıklamalar

Tür, [fpos](../standard-library/fpos-class.md)< `mbstate_t`> için bir eş anlamlı.

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

## <a name="streamsize"></a>streamsize

Akışın boyutunu gösterir.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Açıklamalar

Türü, çeşitli akış işlemlerinde yer alan öğelerin sayısını depolayabilen bir nesneyi tanımlayan işaretli bir tamsayıdır. Gösteriminin en az 16 bit vardır. Bir akış içinde rastgele bir bayt konumunu temsil etmek için yeterince büyük değildir.

### <a name="example"></a>Örnek

Aşağıdaki programı derleyip çalıştırdıktan sonra, `streamsize`ayarının etkisini görmek için test. txt dosyasına bakın.

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

## <a name="wios"></a>wmorolar

Eski ıostream kitaplığından wios sınıfını destekler.

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_ios](../standard-library/basic-ios-class.md)sınıf şablonu için bir eş anlamlıdır.

## <a name="wstreampos"></a>wstreampos

Arabellek işaretçisinin veya dosya işaretçisinin geçerli konumunu tutar.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Açıklamalar

Tür, [fpos](../standard-library/fpos-class.md)< `mbstate_t`> için bir eş anlamlı.

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
