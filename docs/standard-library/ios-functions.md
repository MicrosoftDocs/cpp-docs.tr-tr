---
title: '&lt;iOS&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- xiosbase/std::defaultfloat
- xiosbase/std::boolalpha
- xiosbase/std::dec
- ios/std::fixed
- ios/std::hex
- ios/std::internal
- ios/std::left
- ios/std::noboolalpha
- ios/std::noshowbase
- ios/std::noshowpoint
- ios/std::noshowpos
- ios/std::noskipws
- ios/std::nounitbuf
- ios/std::nouppercase
- ios/std::oct
- ios/std::right
- ios/std::scientific
- ios/std::showbase
- ios/std::showpoint
- ios/std::showpos
- ios/std::skipws
- ios/std::unitbuf
- ios/std::uppercase
ms.assetid: 1382d53f-e531-4b41-adf6-6a1543512e51
helpviewer_keywords:
- std::defaultfloat [C++]
- std::boolalpha [C++]
- std::dec [C++]
- std::fixed [C++]
- std::hex [C++]
- std::internal [C++]
- std::left [C++]
- std::noboolalpha [C++]
- std::noshowbase [C++]
- std::noshowpoint [C++]
- std::noshowpos [C++]
- std::noskipws [C++]
- std::nounitbuf [C++]
- std::nouppercase [C++]
- std::oct [C++]
- std::right [C++]
- std::scientific [C++]
- std::showbase [C++]
- std::showpoint [C++]
- std::showpos [C++]
- std::skipws [C++]
- std::unitbuf [C++]
- std::uppercase [C++]
ms.openlocfilehash: 4937d79c04484dd0cd96f74abb7150873b6f7235
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848430"
---
# <a name="ltiosgt-functions"></a>&lt;iOS&gt; işlevleri

||||
|-|-|-|
|[defaultfloat](#ios_defaultfloat)|[boolalpha](#boolalpha)|[Ara](#dec)|
|[Sabit](#fixed)|[Onaltılık](#hex)|[internal](#internal)|
|[Sol](#left)|[noboolalpha](#noboolalpha)|[noshowbase](#noshowbase)|
|[noshowpoint](#noshowpoint)|[noshowpos](#noshowpos)|[noskipws](#noskipws)|
|[nounitbuf](#nounitbuf)|[nouppercase](#nouppercase)|[Eki](#oct)|
|[Sağ](#right)|[Bilimsel](#scientific)|[showbase](#showbase)|
|[showpoint](#showpoint)|[showpos](#showpos)|[skipws](#skipws)|
|[unitbuf](#unitbuf)|[büyük harf](#uppercase)|

## <a name="boolalpha"></a>  boolalpha

Belirtir türündeki bu değişkenler [bool](../cpp/bool-cpp.md) olarak görünür **true** veya **false** akış.

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, türündeki değişkenler `bool` 1 veya 0 olarak görüntülenir.

`boolalpha` etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::boolalpha`) ve ardından döndürür `str`.

[noboolalpha](../standard-library/ios-functions.md#noboolalpha) etkisini tersine çevirir `boolalpha`.

### <a name="example"></a>Örnek

```cpp
// ios_boolalpha.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   bool b = true;
   cout << b << endl;
   boolalpha( cout );
   cout << b << endl;
   noboolalpha( cout );
   cout << b << endl;
   cout << boolalpha << b << endl;
}
```

```Output
1
true
1
true
```

## <a name="dec"></a>  Ara

Tamsayı değişkenleri temel 10 gösterimde görüntüleneceğini belirtir.

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri temel 10'da görüntülenir.

**DEC** etkili bir şekilde çağırır `str.` [setf](../standard-library/ios-base-class.md#setf)( `ios_base::dec` **, ios_base::basefield**) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_dec.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 100;

   cout << i << endl;   // Default is base 10
   cout << hex << i << endl;
   dec( cout );
   cout << i << endl;
   oct( cout );
   cout << i << endl;
   cout << dec << i << endl;
}
```

```Output
100
64
100
144
100
```

## <a name="ios_defaultfloat"></a>  &lt;iOS&gt; defaultfloat

Bayraklarını yapılandırır bir `ios_base` nesne float değerleri için bir varsayılan görüntü biçimi kullanın.

```cpp
ios_base& defaultfloat(ios_base& _Iosbase);
```

### <a name="parameters"></a>Parametreler

`_Iosbase` Bir `ios_base` nesnesi.

### <a name="remarks"></a>Açıklamalar

_Lisans manipulator etkili bir şekilde çağırır `osbase.` [ios_base::unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::floatfield)`, _lisans döndürür `osbase`.

## <a name="fixed"></a>  Sabit

Bir kayan noktalı sayının Sabit ondalık gösterimde görüntüleneceğini belirtir.

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

**Sabit** kayan nokta sayıları varsayılan görüntü gösterimidir. [Bilimsel](../standard-library/ios-functions.md#scientific) bilimsel gösterim kullanılarak görüntülenecek kayan noktalı sayıların neden olur.

Manipulator etkili bir şekilde çağırır * str.*[setf](../standard-library/ios-base-class.md#setf)( `ios_base::fixed`, **ios_base::floatfield**) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_fixed.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 1.1F;

   cout << i << endl;   // fixed is the default
   cout << scientific << i << endl;
   cout.precision( 1 );
   cout << fixed << i << endl;
}
```

```Output
1.1
1.100000e+000
1.1
```

## <a name="hex"></a>  Onaltılık

Tamsayı değişkenleri temel 16 gösterimde göründüğünü belirtir.

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri temel 10 gösterimde görüntülenir. [DEC](../standard-library/ios-functions.md#dec) ve [Eki](../standard-library/ios-functions.md#oct) de şekilde tamsayı değişkenleri görünür Değiştir.

Manipulator etkili bir şekilde çağırır `str` **.** [setf](../standard-library/ios-base-class.md#setf)( `ios_base::hex`, **ios_base::basefield**) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

Bkz: [Ara](../standard-library/ios-functions.md#dec) nasıl kullanılacağına ilişkin bir örnek **onaltılık**.

## <a name="internal"></a>  İç

Sayının işaretini sola hizalı olarak ve sağa hizalı olarak numarası neden olur.

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesne başvuru içinden `str` türetilir.

### <a name="remarks"></a>Açıklamalar

[showpos](../standard-library/ios-functions.md#showpos) için pozitif sayıları görüntülemek oturum neden olur.

Manipulator etkili bir şekilde çağırır `str`. [setf](../standard-library/ios-base-class.md#setf)( [ios_base::internal](../standard-library/ios-base-class.md#fmtflags), [ios_base::adjustfield](../standard-library/ios-base-class.md#fmtflags)) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_internal.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( void )
{
   using namespace std;
   float i = -123.456F;
   cout.fill( '.' );
   cout << setw( 10 ) << i << endl;
   cout << setw( 10 ) << internal << i << endl;
}
```

```Output
..-123.456
-..123.456
```

## <a name="left"></a>  Sol

Sol kenar boşluğu ile akış temizleme görünmesi çıkış genişliği kadar geniş değil metin neden olur.

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::left`, **ios_base::adjustfield**) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_left.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout.width( 20 );
   cout << f1 << endl;
   cout << left << f1 << endl;
}
```

```Output
                   5
5
```

## <a name="noboolalpha"></a>  noboolalpha

Belirtir türündeki bu değişkenler [bool](../cpp/bool-cpp.md) 1 veya 0'a akış olarak görünür.

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `noboolalpha` etkili olur.

`noboolalpha` etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::boolalpha`) ve ardından döndürür `str`.

[boolalpha](../standard-library/ios-functions.md#boolalpha) etkisini tersine çevirir `noboolalpha`.

### <a name="example"></a>Örnek

Bkz: [boolalpha](../standard-library/ios-functions.md#boolalpha) kullanma örneği için `noboolalpha`.

## <a name="noshowbase"></a>  noshowbase

Bir sayı görüntülendiği notational temel belirten devre dışı bırakır.

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`noshowbase` Varsayılan olarak açıktır. Kullanım [showbase](../standard-library/ios-functions.md#showbase) notational temel sayıların belirtmek için.

Manipulator etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showbase`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

Bkz: [showbase](../standard-library/ios-functions.md#showbase) nasıl kullanılacağına ilişkin bir örnek `noshowbase`.

## <a name="noshowpoint"></a>  noshowpoint

Kayan nokta sayıları, kesirli bölümü sıfırdır yalnızca tam sayı bölümünü görüntüler.

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`noshowpoint` Varsayılan olarak etkindir; kullanmak [showpoint](../standard-library/ios-functions.md#showpoint) ve [duyarlık](../standard-library/ios-base-class.md#precision) sıfır ondalık ayırıcıdan sonra görüntülemek için.

Manipulator etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showpoint`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_noshowpoint.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.000;
   cout << f1 << endl;   // noshowpoint is default
   cout.precision( 4 );
   cout << showpoint << f1 << endl;
   cout << noshowpoint << f1 << endl;
}
```

```Output
5
5.000
5
```

## <a name="noshowpos"></a>  noshowpos

Açıkça imzalanmamış pozitif sayılar neden olur.

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`noshowpos` Varsayılan olarak açıktır.

Manipulator etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showps`), ardından döndürür `str`.

### <a name="example"></a>Örnek

Bkz: [showpos](../standard-library/ios-functions.md#showpos) kullanma örneği için `noshowpos`.

## <a name="noskipws"></a>  noskipws

Giriş akışı tarafından okunacak alanları neden.

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [skipws](../standard-library/ios-functions.md#skipws) etkili olur. Boşluk Giriş akışı okunurken arabelleğin sonuna işaret eder.

Manipulator etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::skipws`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_noskipws.cpp
// compile with: /EHsc
#include <iostream>
#include <string>

int main() {
   using namespace std;
   string s1, s2, s3;
   cout << "Enter three strings: ";
   cin >> noskipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

## <a name="nounitbuf"></a>  nounitbuf

Çıkış arabelleğe ve arabellek dolduğunda işlenmesi için neden olur.

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

[unitbuf](../standard-library/ios-functions.md#unitbuf) boş olmadığında işlenecek arabellek neden olur.

Manipulator etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::unitbuf`) ve ardından döndürür `str`.

## <a name="nouppercase"></a>  nouppercase

Onaltılık basamak ve bilimsel gösterimde üs küçük harflerle görüntüleneceğini belirtir.

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Manipulator etkili bir şekilde çağırır `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::uppercase`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

Bkz: [büyük](../standard-library/ios-functions.md#uppercase) kullanma örneği için `nouppercase`.

## <a name="oct"></a>  Eki

Tamsayı değişkenleri temel 8 gösterimde görüntüleneceğini belirtir.

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesne başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri temel 10 gösterimde görüntülenir. [DEC](../standard-library/ios-functions.md#dec) ve [onaltılık](../standard-library/ios-functions.md#hex) de şekilde tamsayı değişkenleri görünür Değiştir.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::oct`, `ios_base::basefield`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

Bkz: [Ara](../standard-library/ios-functions.md#dec) nasıl kullanılacağına ilişkin bir örnek **Eki**.

## <a name="right"></a>  Sağ

Sağ kenar boşluğu ile akış temizleme görünmesi çıkış genişliği kadar geniş değil metin neden olur.

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesne başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

[Sol](../standard-library/ios-functions.md#left) de metni hizalama değiştirir.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::right`, `ios_base::adjustfield`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_right.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << left << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << right << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
}
```

```Output
5
                   5
5
5
                   5
                   5
```

## <a name="scientific"></a>  Bilimsel

Kayan nokta sayıları bilimsel gösterim kullanılarak görüntülenmesine neden olur.

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [sabit](../standard-library/ios-functions.md#fixed) gösterimidir yürürlükte için kayan nokta sayıları.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::scientific`, `ios_base::floatfield`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_scientific.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 100.23F;

   cout << i << endl;
   cout << scientific << i << endl;
}
```

```Output
100.23
1.002300e+002
```

## <a name="showbase"></a>  showbase

Bir sayı görüntülendiği notational temel gösterir.

```cpp
ios_base& showbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Bir sayının notational temel değiştirilebilir [Ara](../standard-library/ios-functions.md#dec), [Eki](../standard-library/ios-functions.md#oct), veya [onaltılık](../standard-library/ios-functions.md#hex).

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::showbase`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_showbase.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int j = 100;

   cout << showbase << j << endl;   // dec is default
   cout << hex << j << showbase << endl;
   cout << oct << j << showbase << endl;

   cout << dec << j << noshowbase << endl;
   cout << hex << j << noshowbase << endl;
   cout << oct << j << noshowbase << endl;
}
```

```Output
100
0x64
0144
100
64
144
```

## <a name="showpoint"></a>  showpoint

Kesirli bölümü sıfır olsa bile bir kayan noktalı sayı ve basamak tamsayılı bölümünü ondalık konumun sağında görüntüler.

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [noshowpoint](../standard-library/ios-functions.md#noshowpoint) etkili olur.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::showpoint`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

Bkz: [noshowpoint](../standard-library/ios-functions.md#noshowpoint) kullanma örneği için `showpoint`.

## <a name="showpos"></a>  showpos

Açıkça imzalanacak pozitif sayılar neden olur.

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

[noshowpos](../standard-library/ios-functions.md#noshowpos) varsayılandır.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::showpos`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_showpos.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 1;

   cout << noshowpos << i << endl;   // noshowpos is default
   cout << showpos << i << endl;
}
```

```Output
1
+1
```

## <a name="skipws"></a>  skipws

Giriş akışı tarafından değil okunacak alanları neden.

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `skipws` etkili olur. [noskipws](../standard-library/ios-functions.md#noskipws) giriş akışından okumaya alanları neden olur.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::skipws`) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   char s1, s2, s3;
   cout << "Enter three characters: ";
   cin >> skipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

```Output

1 2 3

```

```Output

      1 2 3.1.
.2.
.3.
```

## <a name="unitbuf"></a>  unitbuf

Çıkış arabelleği boş olmadığında işlenmesi için neden olur.

```cpp
ios_base& unitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesne başvuru içinden `str` türetilir.

### <a name="remarks"></a>Açıklamalar

Unutmayın `endl` de arabelleği temizler.

[nounitbuf](../standard-library/ios-functions.md#nounitbuf) varsayılan olarak etkindir.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( [ios_base::unitbuf](../standard-library/ios-base-class.md#fmtflags)) ve ardından döndürür `str`.

## <a name="uppercase"></a>  büyük harf

Onaltılık basamak ve bilimsel gösterimde üs büyük görüntüleneceğini belirtir.

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

`str` Bir başvuru türünde bir nesne [ios_base](../standard-library/ios-base-class.md), veya devralan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesne başvuru içinden `str` türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [nouppercase](../standard-library/ios-functions.md#nouppercase) etkili olur.

Manipulator etkili bir şekilde çağırır `str`.[ setf](../standard-library/ios-base-class.md#setf)( [ios_base::uppercase](../standard-library/ios-base-class.md#fmtflags)) ve ardından döndürür `str`.

### <a name="example"></a>Örnek

```cpp
// ios_uppercase.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
   using namespace std;

   double i = 1.23e100;
   cout << i << endl;
   cout << uppercase << i << endl;

   int j = 10;
   cout << hex << nouppercase << j << endl;
   cout << hex << uppercase << j << endl;
}
```

```Output
1.23e+100
1.23E+100
a
A
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iOS >](../standard-library/ios.md)<br/>
