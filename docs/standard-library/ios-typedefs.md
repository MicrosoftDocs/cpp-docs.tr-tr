---
title: '&lt;iOS&gt; typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
ms.openlocfilehash: d79e3361d58165ac356e2ef75c0a3fd1a4cb4f26
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963647"
---
# <a name="ltiosgt-typedefs"></a>&lt;iOS&gt; tür tanımları

||||
|-|-|-|
|[iOS](#ios)|[streamoff](#streamoff)|[streampos](#streampos)|
|[streamsize](#streamsize)|[wios](#wios)|[wstreampos](#wstreampos)|

## <a name="ios"></a>  iOS

Eski iostream Kitaplığı'ndan ios sınıf destekler.

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ios](../standard-library/basic-ios-class.md), türü öğeler için özelleştirilmiş **char** varsayılan karakter nitelikleri ile.

## <a name="streamoff"></a>  streamoff

İç işlemlerini destekler.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Açıklamalar

İşlemleri konumlandırma çeşitli stream'de ilgili bir bayt uzaklığı depolayan bir nesne tanımlayan bir işaretli bir tamsayı türüdür. Değer en az 32 bit gösterimine sahiptir. Bir rastgele bayt konumu bir akış içinde temsil etmek için mutlaka yeterli büyüklükte değil. Değer `streamoff(-1)` genellikle hatalı bir uzaklık gösterir.

## <a name="streampos"></a>  streampos

Arabelleğin işaretçisini veya dosya işaretçisi konumunu içerir.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.

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

## <a name="streamsize"></a>  streamsize

Akış boyutunu gösterir.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Açıklamalar

Çeşitli akış işlemleriyle ilgili öğelerin sayısını depolayan bir nesne tanımlayan bir işaretli bir tamsayı türüdür. En az 16 bit gösterimine sahiptir. Bir rastgele bayt konumu bir akış içinde temsil etmek için mutlaka yeterli büyüklükte değil.

### <a name="example"></a>Örnek

Derleyerek ve çalıştırarak aşağıdaki programın ara sonra ayarının etkisini görmek için dosya test.txt `streamsize`.

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

## <a name="wios"></a>  wios

Eski iostream kitaplığı wios sınıftan destekler.

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ios](../standard-library/basic-ios-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="wstreampos"></a>  wstreampos

Arabelleğin işaretçisini veya dosya işaretçisi konumunu içerir.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<iOS >](../standard-library/ios.md)<br/>
