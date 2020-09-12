---
title: '&lt;ostream &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: a4dfee6c70f068e5a61294e6b2863a8a12a9c378
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039774"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream &gt; işleçleri

[işlecinde&lt;&lt;](#op_lt_lt)

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> işlecinde&lt;&lt;

Akışa çeşitli türler yazar.

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

*_Ch*\
Bir karakter.

*_Elem*\
Öğe türü.

*_Ostr*\
Bir `basic_ostream` nesnesi.

*üstbilgisine*\
Bir karakter dizesi.

*_Tr*\
Karakter nitelikleri.

*Acil*\
Tür

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

`basic_ostream`Sınıfı ayrıca birkaç ekleme işleci tanımlar. Daha fazla bilgi için bkz. [basic_ostream:: &lt; &lt; işleci](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

Str 'nin uzunluğu N = `traits_type::` [uzunluğunu](../standard-library/char-traits-struct.md#length)( `str` ) belirler ve diziyi ekler. *str* N < `_Ostr.` [Width](../standard-library/ios-base-class.md#width)ise, işlev bir `_Ostr.width` -N Fill karakter yinelemesi de ekler. Yineleme ( `_Ostr` . [flags](../standard-library/ios-base-class.md#flags)  &  bayraklar `adjustfield` ! = [sol](../standard-library/ios-functions.md#left). Aksi takdirde, yineleme diziyi izler. İşlev *_Ostr*döndürür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

öğesi ekler `_Ch` . 1 < `_Ostr.width` , işlev bir `_Ostr.width` -1 Fill karakter yinelemesi de ekler. Yineleme, IF dizisinden önce gelir `_Ostr.flags & adjustfield != left` . Aksi takdirde, yineleme diziyi izler. *_Ostr*döndürür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```

aynı şekilde davranır

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

her öğe _Ch, *Str* 'de başlayan sıranın *_Ch* , `Elem` `_Ostr.` [PUT](../standard-library/basic-ostream-class.md#put)( `_Ostr.` [Genişlet](../standard-library/basic-ios-class.md#widen)( `_Ch` )) yöntemini çağırarak türü bir nesneye dönüştürülebileceğinden.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    char _Ch);
```

aynı şekilde davranır

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

*_Ch* dışında, çağırarak bir nesnesine dönüştürülür `Elem` `_Ostr.put( _Ostr.widen( _Ch ))` .

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```

aynı şekilde davranır

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

(Öğeleri eklemeden önce genişletmek zorunda değildir.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```

aynı şekilde davranır

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

(Bu, eklemeden önce *_Ch* genişlememelidir.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

döndürür `_Ostr << (const char *)str` .

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

döndürür `_Ostr << (char)_Ch` .

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

döndürür `_Ostr << (const char *)str` .

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

döndürür `_Ostr << (char)_Ch` .

Şablon işlevi:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

döndürür `_Ostr << val` (ve bir [rvalue başvurusunu](../cpp/rvalue-reference-declarator-amp-amp.md) `_Ostr` işlemdeki bir lvalue öğesine dönüştürür).

### <a name="example"></a>Örnek

Bkz [flush](../standard-library/ostream-functions.md#flush) . bir örnek için Temizleme `operator<<` .

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream>](../standard-library/ostream.md)
