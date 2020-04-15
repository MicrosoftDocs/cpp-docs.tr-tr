---
title: '&lt;ostream&gt; operatörleri'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: d8b6f4e0f0b5bca41f8d895415fff4003231ad1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373600"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt; operatörleri

||
|-|
|[Işleç&lt;&lt;](#op_lt_lt)|

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Işleç&lt;&lt;

Akışa çeşitli türlerde yazar.

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

*Str*\
Bir karakter dizesi.

*_Tr*\
Karakter özellikleri.

*Val*\
Türü

### <a name="return-value"></a>Dönüş Değeri

Dere.

### <a name="remarks"></a>Açıklamalar

Sınıf `basic_ostream` ayrıca birkaç ekleme işleci tanımlar. Daha fazla bilgi için [basic_ostream::operator&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

*str'de*başlayan `traits_type::`dizinin`str`N = uzunluk ( ) [uzunluğunu](../standard-library/char-traits-struct.md#length)belirler ve diziyi ekler. N < `_Ostr.` [genişliği](../standard-library/ios-base-class.md#width)ise, işlev de bir yineleme `_Ostr.width` ekler - N dolgu karakterleri. Yineleme, if dizisinden önce`_Ostr`gelir ( . [bayraklar](../standard-library/ios-base-class.md#flags)  &  `adjustfield` != [sol](../standard-library/ios-functions.md#left). Aksi takdirde, yineleme sırayı izler. İşlev *_Ostr*döndürür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

öğeyi `_Ch`ekler. 1 < `_Ostr.width`ise, işlev de bir yineleme `_Ostr.width` ekler - 1 dolgu karakterleri. Yineleme, eğer `_Ostr.flags & adjustfield != left`. Aksi takdirde, yineleme sırayı izler. *_Ostr*döndürür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```

aynı şekilde

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

str'de başlayan dizinin *_Ch* *str* her [öğe, put](../standard-library/basic-ostream-class.md#put)`_Ostr.`[(widen](../standard-library/basic-ios-class.md#widen)( )`_Ch`()) diyerek `Elem` `_Ostr.`tür nesnesine dönüştürülür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    char _Ch);
```

aynı şekilde

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

_Ch *_Ch* ( `_Ostr.widen`( `_Ch`)) numaralı `Elem` çağrıyaparak `_Ostr.put`bir tür nesneye dönüştürülmesi dışında.

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```

aynı şekilde

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

(Eklemeden önce öğeleri genişletmek zorunda değildir.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```

aynı şekilde

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

(Takmadan önce *_Ch* genişletmek zorunda değildir.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

 <<  `_Ostr` döndürür.`const char *` `str`

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

 <<  `_Ostr` döndürür.`char` `_Ch`

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

 <<  `_Ostr` döndürür.`const char *` `str`

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

 <<  `_Ostr` döndürür.`char` `_Ch`

Şablon işlevi:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

döndürür `_Ostr` `<<` `val` (ve işlemdeki `_Ostr` bir [lvalue'ye Bir RValue Başvurusu](../cpp/rvalue-reference-declarator-amp-amp.md) dönüştürür).

### <a name="example"></a>Örnek

Kullanarak `operator<<`bir örnek için [floş](../standard-library/ostream-functions.md#flush) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream>](../standard-library/ostream.md)
