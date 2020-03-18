---
title: '&lt;ostream&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: c80abcb08423b4bb269e7d60ac43ef97d197a0e9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419688"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt; işleçleri

||
|-|
|[işleç&lt;&lt;](#op_lt_lt)|

## <a name="op_lt_lt"></a>işleç&lt;&lt;

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

*str*\
Bir karakter dizesi.

*_Tr*\
Karakter nitelikleri.

*val*\
Tür

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

`basic_ostream` sınıfı birçok ekleme işlecini de tanımlar. Daha fazla bilgi için bkz. [basic_ostream:: operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

*Str*'Nin uzunluğu N = `traits_type::`[uzunluğunu](../standard-library/char-traits-struct.md#length)(`str`) belirler ve diziyi ekler. N `_Ostr.`[width](../standard-library/ios-base-class.md#width)<, işlev Ayrıca `_Ostr.width`-N dolgusu karakterlerinden oluşan bir yineleme ekler. (`_Ostr`, yineleme sırayla önce gelir. [bayraklar](../standard-library/ios-base-class.md#flags) & `adjustfield`! = [kaldı](../standard-library/ios-functions.md#left). Aksi takdirde, yineleme diziyi izler. İşlev *_Ostr*döndürür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

öğe `_Ch`ekler. 1 < `_Ostr.width`, işlev aynı zamanda `_Ostr.width`-1 Fill karakterlerinden oluşan bir yineleme ekler. `_Ostr.flags & adjustfield != left`, yineleme sıranın önüne gelir. Aksi takdirde, yineleme diziyi izler. *_Ostr*döndürür.

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

her öğe _Ch, *Str* 'de başlayan sıranın *_Ch* , `_Ostr.`[put](../standard-library/basic-ostream-class.md#put)(`_Ostr.`[Genişlet](../standard-library/basic-ios-class.md#widen)(`_Ch`)) çağırarak `Elem` türünde bir nesneye dönüştürüldüğünden.

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

*_Ch* , `_Ostr.put`(`_Ostr.widen`(`_Ch`)) çağırarak `Elem` türündeki bir nesneye dönüştürüldüğünden.

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

`_Ostr` < < (`const char *`) `str`döndürür.

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

`_Ostr` < < (`char`) `_Ch`döndürür.

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

`_Ostr` < < (`const char *`) `str`döndürür.

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

`_Ostr` < < (`char`) `_Ch`döndürür.

Şablon işlevi:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

`_Ostr` `<<` `val` döndürür (ve rvalue `_Ostr` [başvurusunu](../cpp/rvalue-reference-declarator-amp-amp.md) işlemdeki bir lvalue öğesine dönüştürür).

### <a name="example"></a>Örnek

`operator<<`kullanarak bir örnek için [Temizleme](../standard-library/ostream-functions.md#flush) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[ostream > \<](../standard-library/ostream.md)
