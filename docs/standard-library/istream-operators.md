---
title: '&lt;IStream&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: c10692194c80051b10ecbe776c7d23a03860d508
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447794"
---
# <a name="ltistreamgt-operators"></a>&lt;IStream&gt; işleçleri

## <a name="op_gt_gt"></a>işlecinde&gt;&gt;

Akıştan karakterler ve dizeler ayıklar.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Bir karakter.

*İstr*\
Bir akış.

*üstbilgisine*\
Bir dize.

*Acil*\
Bir tür.

### <a name="return-value"></a>Dönüş Değeri

Akış

### <a name="remarks"></a>Açıklamalar

`basic_istream` Sınıfı ayrıca birkaç ayıklama işleci tanımlar. Daha fazla bilgi için bkz. [basic_istream:: operator > >](../standard-library/basic-istream-class.md#op_gt_gt).

Şablon işlevi:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

*N* -1 ' e kadar öğeyi ayıklar ve bu öğeleri dizi Içinde _ *Str*'dan başlayarak depolar. Eğer `Istr`. [Genişlik](../standard-library/ios-base-class.md#width) sıfırdan büyük, `Istr` *N* . **Genişlik**; Aksi takdirde, bu, bildirilebilecek en büyük dizisinin `Elem` boyutudur. İşlev her zaman değeri `Elem()` , depoladığı herhangi bir ayıklanan öğeden sonra saklar. Ayıklama, dosyanın sonunda, **Eled**(0) değerine sahip bir karakter (ayıklanmayan) veya [WS](../standard-library/istream-functions.md#ws)tarafından atılacak herhangi bir öğe (ayıklanmayan) üzerinde erken bir süre sonra durduruluyor. İşlev hiçbir öğe ayıklaıyorsa, çağırır `Istr`. [SetState](../standard-library/basic-ios-class.md#setstate) (**failbit**). Herhangi bir durumda, çağırır `Istr`. **Genişlik** (0) ve *ISTR*döndürür.

**Güvenlik notunun** Giriş akışından ayıklanan null ile sonlandırılmış dizenin hedef arabellek *Str*boyutunu aşmaması gerekir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/desktop/SecBP/avoiding-buffer-overruns).

Şablon işlevi:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

Mümkünse bir öğe ayıklar ve bu öğeyi *ayıklar.* Aksi takdirde, çağrısı **olur**. [SetState](../standard-library/basic-ios-class.md#setstate) ( **failbit**). Herhangi bir durumda, *ISTR*döndürür.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

döndürür `Istr >> ( char * ) str`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

döndürür `Istr >> ( char& ) Ch`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

döndürür `Istr >> ( char * ) str`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

döndürür `Istr >> ( char& ) Ch`.

Şablon işlevi:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

döndürür `Istr >> val` (ve bir rvalue `Istr` başvurusunu işlemdeki bir lvalue öğesine dönüştürür).

### <a name="example"></a>Örnek

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[\<IStream >](../standard-library/istream.md)
