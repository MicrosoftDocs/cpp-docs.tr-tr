---
title: '&lt;ostream&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: c80abcb08423b4bb269e7d60ac43ef97d197a0e9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453528"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt; işleçleri

||
|-|
|[işlecinde&lt;&lt;](#op_lt_lt)|

## <a name="op_lt_lt"></a>işlecinde&lt;&lt;

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

*_Eley*\
Öğe türü.

*_Ostr*\
A `basic_ostream` nesne.

*üstbilgisine*\
Bir karakter dizesi.

*_Tr*\
Karakter nitelikleri.

*Acil*\
Tür

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

`basic_ostream` Sınıfı ayrıca birkaç ekleme işleci tanımlar. Daha fazla bilgi için bkz. [basic_ostream::&lt;operator&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

Str 'nin uzunluğu N = `traits_type::` [uzunluğunu](../standard-library/char-traits-struct.md#length)(`str`) belirler ve diziyi ekler. N < `_Ostr.` [Width](../standard-library/ios-base-class.md#width)ise, işlev bir `_Ostr.width` -N Fill karakter yinelemesi de ekler. Yineleme (`_Ostr`. [](../standard-library/ios-base-class.md#flags)bayraklar & != [sol](../standard-library/ios-functions.md#left).`adjustfield` Aksi takdirde, yineleme diziyi izler. İşlev *_Ostr*döndürür.

Şablon işlevi

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

öğesi `_Ch`ekler. 1 < `_Ostr.width`, işlev bir `_Ostr.width` -1 Fill karakter yinelemesi de ekler. Yineleme, IF `_Ostr.flags & adjustfield != left`dizisinden önce gelir. Aksi takdirde, yineleme diziyi izler. *_Ostr*döndürür.

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

bir dizinin her bir *öğesi,* *Str* ' de başlayan her öğe için, [PUT](../standard-library/basic-ostream-class.md#put)(`_Ostr.`[Genişlet](../standard-library/basic-ios-class.md#widen)`_Ch`() `Elem` ) yöntemini `_Ostr.`çağırarak türü bir nesneye dönüştürüldüğünden hariç.

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

Bu *_Ch* `Elem` , ( `_Ostr.put` `_Ostr.widen`( ))öğesiniçağıraraktüründebirnesneyedönüştürüldüğünden.`_Ch`

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

(Bu, eklemeden önce *_Ch* öğesini genişletmek zorunda değildir.)

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

< `_Ostr` < (`const char *` )`str`döndürür.

Şablon işlevi

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

< `_Ostr` < (`char` )`_Ch`döndürür.

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

< `_Ostr` < (`const char *` )`str`döndürür.

Şablon işlevi:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

< `_Ostr` < (`char` )`_Ch`döndürür.

Şablon işlevi:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

döndürür `_Ostr` `<<` (ve`_Ostr` bir [rvalue başvurusunu](../cpp/rvalue-reference-declarator-amp-amp.md) işlemdeki bir lvalue öğesine dönüştürür). `val`

### <a name="example"></a>Örnek

Bkz [](../standard-library/ostream-functions.md#flush) `operator<<`. bir örnek için temizleme.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)
