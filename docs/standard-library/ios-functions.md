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
ms.openlocfilehash: a19d023400179e1e7e16541b7e3d7ef38ad963ba
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101099"
---
# <a name="ltiosgt-functions"></a>&lt;iOS&gt; işlevleri

||||
|-|-|-|
|[defaultfloat](#ios_defaultfloat)|[boolalpha](#boolalpha)|[Ara](#dec)|
|[düzeltildi](#fixed)|[onaltılık](#hex)|[internal](#internal)|
|[Sol](#left)|[noboolalpha](#noboolalpha)|[noshowbase](#noshowbase)|
|[noshowpoint](#noshowpoint)|[noshowpos](#noshowpos)|[noskipws](#noskipws)|
|[nounitbuf](#nounitbuf)|[nouppercase](#nouppercase)|[Eki](#oct)|
|[sağ](#right)|[Bilimsel](#scientific)|[showbase](#showbase)|
|[showpoint](#showpoint)|[showpos](#showpos)|[skipws](#skipws)|
|[unitbuf](#unitbuf)|[büyük harf](#uppercase)|

## <a name="boolalpha"></a>  boolalpha

Belirtir, türü değişkenlerindeki [bool](../cpp/bool-cpp.md) olarak görünür **true** veya **false** akış.

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, türündeki değişkenler **bool** 1 veya 0 olarak görüntülenir.

`boolalpha` etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::boolalpha`) ve sonra *str*.

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

Tamsayı değişkenleri taban 10 gösteriminde görüneceğini belirtir.

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri taban 10'da görüntülenir.

`dec` etkili bir şekilde çağıran `str.` [setf](../standard-library/ios-base-class.md#setf)( `ios_base::dec`, `ios_base::basefield`) ve sonra *str*.

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

Bayraklarını yapılandırır bir `ios_base` kayan nokta değerleri için varsayılan görüntüleme biçimi kullanılacak nesne.

```cpp
ios_base& defaultfloat(ios_base& _Iosbase);
```

### <a name="parameters"></a>Parametreler

*_Iosbase*<br/>
Bir `ios_base` nesne.

### <a name="remarks"></a>Açıklamalar

İşleyici _lisans etkili bir şekilde çağıran `osbase.` [ios_base::unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::floatfield)`, ardından _lisans döndürür `osbase`.

## <a name="fixed"></a>  düzeltildi

Bir kayan noktalı sayı sabit ondalık gösteriminde görüntüleneceğini belirtir.

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`fixed` Varsayılan görüntü kayan nokta numaraları gösterimidir. [Bilimsel](../standard-library/ios-functions.md#scientific) bilimsel gösterim kullanılarak görüntüleneceğini kayan noktalı sayıların neden olur.

İşleyici etkili bir şekilde çağıran * str.*[setf](../standard-library/ios-base-class.md#setf)( `ios_base::fixed`, `ios_base::floatfield`) ve sonra *str*.

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

## <a name="hex"></a>  onaltılık

Tamsayı değişkenleri temel 16 gösteriminde görünmesi gereken belirtir.

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri taban 10 gösterim görüntülenir. [Ara](../standard-library/ios-functions.md#dec) ve [Eki](../standard-library/ios-functions.md#oct) de değişiklik şekilde tamsayı değişkenleri görünür.

İşleyici etkili bir şekilde çağıran `str` **.** [setf](../standard-library/ios-base-class.md#setf)( `ios_base::hex`, `ios_base::basefield`) ve sonra *str*.

### <a name="example"></a>Örnek

Bkz: [Ara](../standard-library/ios-functions.md#dec) nasıl kullanılacağına ilişkin bir örnek `hex`.

## <a name="internal"></a>  İç

Bir sayının işaretini sola hizalı olarak ve sağa hizalı olarak sayı neden olur.

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesnesine bir başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

[showpos](../standard-library/ios-functions.md#showpos) pozitif sayılar için görüntülenecek oturum neden olur.

İşleyici etkili bir şekilde çağıran `str`. [setf](../standard-library/ios-base-class.md#setf)( [ios_base::internal](../standard-library/ios-base-class.md#fmtflags), [ios_base::adjustfield](../standard-library/ios-base-class.md#fmtflags)) ve sonra *str*.

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

Sol kenar boşluğu ile stream temizleme görünmesini çıkış olarak geniş olmayan metin neden olur.

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::left`, `ios_base::adjustfield`) ve sonra *str*.

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

Belirten bu türü değişkenlerindeki [bool](../cpp/bool-cpp.md) 1 veya 0 akışı gibi görünür.

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `noboolalpha` etkilidir.

`noboolalpha` etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::boolalpha`) ve sonra *str*.

[boolalpha](../standard-library/ios-functions.md#boolalpha) etkisini tersine çevirir `noboolalpha`.

### <a name="example"></a>Örnek

Bkz: [boolalpha](../standard-library/ios-functions.md#boolalpha) kullanma örneği için `noboolalpha`.

## <a name="noshowbase"></a>  noshowbase

Bir sayı görüntülendiği notational temel belirten devre dışı bırakır.

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`noshowbase` Varsayılan olarak açıktır. Kullanım [showbase](../standard-library/ios-functions.md#showbase) notational taban sayı belirtmek için.

İşleyici etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showbase`) ve sonra *str*.

### <a name="example"></a>Örnek

Bkz: [showbase](../standard-library/ios-functions.md#showbase) nasıl kullanılacağına ilişkin bir örnek `noshowbase`.

## <a name="noshowpoint"></a>  noshowpoint

Kayan noktalı sayıların, kesirli bölümü sıfırdır. yalnızca tam sayı bölümünü görüntüler.

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`noshowpoint` Varsayılan olarak açıktır; kullanma [showpoint](../standard-library/ios-functions.md#showpoint) ve [duyarlık](../standard-library/ios-base-class.md#precision) sayının ondalık ayırıcıdan sonra görüntülenecek.

İşleyici etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showpoint`) ve sonra *str*.

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

Pozitif sayı değil açıkça imzalanmasını neden olur.

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

`noshowpos` Varsayılan olarak açıktır.

İşleyici etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showps`), ardından döndürür *str*.

### <a name="example"></a>Örnek

Bkz: [showpos](../standard-library/ios-functions.md#showpos) kullanma örneği için `noshowpos`.

## <a name="noskipws"></a>  noskipws

Giriş akışı tarafından okunacak alanları neden.

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [skipws](../standard-library/ios-functions.md#skipws) etkindir. Giriş akışında bir boşluk okunduğunda, arabelleğin sonuna işaret eder.

İşleyici etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::skipws`) ve sonra *str*.

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

Arabelleğe alınan ve arabelleği dolu olduğunda işlenmesi için neden çıktı.

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

[unitbuf](../standard-library/ios-functions.md#unitbuf) arabellek boş olmadığında işlenecek neden olur.

İşleyici etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::unitbuf`) ve sonra *str*.

## <a name="nouppercase"></a>  nouppercase

Onaltılık basamak ve bilimsel gösterimde üs küçük harflerle görüneceğini belirtir.

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

İşleyici etkili bir şekilde çağıran `str`.[ unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::uppercase`) ve sonra *str*.

### <a name="example"></a>Örnek

Bkz: [büyük](../standard-library/ios-functions.md#uppercase) kullanma örneği için `nouppercase`.

## <a name="oct"></a>  Eki

Tamsayı değişkenleri temel 8 gösteriminde görüneceğini belirtir.

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesnesine bir başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri taban 10 gösterim görüntülenir. [Ara](../standard-library/ios-functions.md#dec) ve [onaltılık](../standard-library/ios-functions.md#hex) de değişiklik şekilde tamsayı değişkenleri görünür.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::oct`, `ios_base::basefield`) ve sonra *str*.

### <a name="example"></a>Örnek

Bkz: [Ara](../standard-library/ios-functions.md#dec) nasıl kullanılacağına ilişkin bir örnek `oct`.

## <a name="right"></a>  sağ

Sağ kenar boşluğu ile stream temizleme görünmesini çıkış olarak geniş olmayan metin neden olur.

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesnesine bir başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

[Sol](../standard-library/ios-functions.md#left) de metin gerekçe değiştirir.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::right`, `ios_base::adjustfield`) ve sonra *str*.

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

Bilimsel gösterim kullanılarak görüntüleneceğini kayan noktalı sayıların neden olur.

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [sabit](../standard-library/ios-functions.md#fixed) gösterimi yürürlükte olan kayan nokta sayıları için.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::scientific`, `ios_base::floatfield`) ve sonra *str*.

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

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Bir sayının notational temel değiştirilebilir [Ara](../standard-library/ios-functions.md#dec), [Eki](../standard-library/ios-functions.md#oct), veya [onaltılık](../standard-library/ios-functions.md#hex).

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::showbase`) ve sonra *str*.

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

Kesirli bölümü sıfır olsa bile tam sayı bölümü bir kayan noktalı sayı ve sayılar ondalık noktasının sağında görüntüler.

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [noshowpoint](../standard-library/ios-functions.md#noshowpoint) etkindir.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::showpoint`) ve sonra *str*.

### <a name="example"></a>Örnek

Bkz: [noshowpoint](../standard-library/ios-functions.md#noshowpoint) kullanma örneği için `showpoint`.

## <a name="showpos"></a>  showpos

Pozitif sayıları açıkça imzalanmasını neden olur.

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

[noshowpos](../standard-library/ios-functions.md#noshowpos) varsayılandır.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::showpos`) ve sonra *str*.

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

Giriş akışı tarafından okunur olmayan alanları neden.

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Hangi _ nesnesine bir başvuru *Str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `skipws` etkilidir. [noskipws](../standard-library/ios-functions.md#noskipws) giriş akışından okunacak alanları neden olur.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( `ios_base::skipws`) ve sonra *str*.

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

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesnesine bir başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

Unutmayın `endl` ayrıca arabelleğini aktarır.

[nounitbuf](../standard-library/ios-functions.md#nounitbuf) varsayılan olarak etkindir.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( [ios_base::unitbuf](../standard-library/ios-base-class.md#fmtflags)) ve sonra *str*.

## <a name="uppercase"></a>  büyük harf

Onaltılık basamak ve bilimsel gösterimde üs büyük harf olarak görüneceğini belirtir.

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Türü bir nesneye başvuru [ios_base](../standard-library/ios-base-class.md), veya devralınan bir türe `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Nesnesine bir başvuru içinden *str* türetilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [nouppercase](../standard-library/ios-functions.md#nouppercase) etkindir.

İşleyici etkili bir şekilde çağıran `str`.[ setf](../standard-library/ios-base-class.md#setf)( [ios_base::uppercase](../standard-library/ios-base-class.md#fmtflags)) ve sonra *str*.

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
