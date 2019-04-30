---
title: '&lt;ostream&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: ee1a9a6829dbef13b034300d696c43ddba48d9d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370963"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt; işleçleri

||
|-|
|[İşleci&lt;&lt;](#op_lt_lt)|

## <a name="op_lt_lt"></a>  İşleci&lt;&lt;

Çeşitli türleri, akışa yazar.

```cpp
template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const Elem* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    Elem _Ch);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const char* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);

template <class _Elem, class _Tr, class T>
basic_ostream <_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>&& _Ostr,
    Ty val);
```

### <a name="parameters"></a>Parametreler

*_Ch*<br/>
Bir karakter.

*_Elem*<br/>
Öğe türü.

*_Ostr*<br/>
A `basic_ostream` nesne.

*str*<br/>
Bir karakter dizesi.

*_Tr*<br/>
Karakter nitelikleri.

*VAL*<br/>
Türü

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

`basic_ostream` Sınıfı da birkaç ekleme işleçlerini tanımlar. Daha fazla bilgi için [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

' % s'uzunluk N belirler = `traits_type::` [uzunluğu](../standard-library/char-traits-struct.md#length)(`str`) dizisi başında, *str*ve dizisi ekler. N < `_Ostr.` [genişliği](../standard-library/ios-base-class.md#width), işlev ayrıca bir tekrarını ekler sonra `_Ostr.width` -N dolgu karakter. Yineleme sırası, önündeki (`_Ostr`. [bayrakları](../standard-library/ios-base-class.md#flags)  &  `adjustfield` ! = [sol](../standard-library/ios-functions.md#left). Aksi takdirde, yineleme sırası izler. İşlev döndürür *_Ostr*.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

bir öğe ekler `_Ch`. 1 < `_Ostr.width`, işlev ayrıca bir tekrarını ekler sonra `_Ostr.width` - 1 karakter doldurun. Yineleme sırası, önündeki `_Ostr.flags & adjustfield != left`. Aksi takdirde, yineleme sırası izler. Döndürür *_Ostr*.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```

aynı şekilde davranır.

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

dışında her öğe *_Ch* dizisi başında, *str* türünde bir nesne için dönüştürülür `Elem` çağırarak `_Ostr.` [put](../standard-library/basic-ostream-class.md#put)(`_Ostr.` [genişletmek](../standard-library/basic-ios-class.md#widen)(`_Ch`)).

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    char _Ch);
```

aynı şekilde davranır.

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

dışında *_Ch* türünde bir nesne için dönüştürülür `Elem` çağırarak `_Ostr.put`( `_Ostr.widen`( `_Ch`)).

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```

aynı şekilde davranır.

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

(Bu öğeleri eklemeden önce genişletmeniz gerekmez.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```

aynı şekilde davranır.

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

(Genişletmek yok *_Ch* eklemeden önce.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

döndürür `_Ostr` << (`const char *`) `str`.

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

döndürür `_Ostr` << (`char`) `_Ch`.

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

döndürür `_Ostr` << (`const char *`) `str`.

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

döndürür `_Ostr` << (`char`) `_Ch`.

Şablon işlevi:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

döndürür `_Ostr` `<<` `val` (ve dönüştüren bir [RValue başvuru](../cpp/rvalue-reference-declarator-amp-amp.md) için `_Ostr` işleminde bir lvalue için).

### <a name="example"></a>Örnek

Bkz: [Temizleme](../standard-library/ostream-functions.md#flush) bir örnek için `operator<<`.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)<br/>
