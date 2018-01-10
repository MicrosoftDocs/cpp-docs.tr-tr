---
title: "&lt;ostream&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ostream/std::operator&lt;&lt;
dev_langs: C++
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f78befe92263dd6b4ef666c865ef9dd65c7103db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt; işleçleri
||  
|-|  
|[işleci&lt;&lt;](#op_lt_lt)|  
  
##  <a name="op_lt_lt"></a>işleci&lt;&lt;  
 Çeşitli türleri akışa yazar.  
  
```
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
 `_Ch`  
 Karakter.  
  
 `_Elem`  
 Öğe türü.  
  
 `_Ostr`  
 A `basic_ostream` nesnesi.  
  
 `str`  
 Bir karakter dizesi.  
  
 `_Tr`  
 Karakter nitelikler.  
  
 `val`  
 Türü  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış.  
  
### <a name="remarks"></a>Açıklamalar  
 `basic_ostream` Sınıfı ayrıca birkaç ekleme işleçlerini tanımlar. Daha fazla bilgi için bkz: [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).  
  
 Şablon işlevi  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```  
  
 N uzunluğunu belirler = `traits_type::` [uzunluğu](../standard-library/char-traits-struct.md#length)( `str`) dizisi başında, `str`ve dizisi ekler. Varsa N < `_Ostr.` [genişliği](../standard-library/ios-base-class.md#width), işlevi de bir yinelenmesinin ekler sonra `_Ostr.width` -N dolgu karakter. Yineleme dizisi varsa önündeki ( `_Ostr`. [bayrakları](../standard-library/ios-base-class.md#flags)  &  `adjustfield` ! = [sol](../standard-library/ios-functions.md#left). Aksi takdirde, yineleme dizisi izler. İşlevi döndürür `_Ostr`.  
  
 Şablon işlevi  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 öğe ekler `_Ch`. 1 ise < `_Ostr.width`, işlevi de bir yinelenmesinin ekler sonra `_Ostr.width` - 1 karakter doldurun. Yineleme dizisi varsa önündeki `_Ostr.flags & adjustfield != left`. Aksi takdirde, yineleme dizisi izler. Döndürdüğü `_Ostr`.  
  
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
  
 dışında her öğe `_Ch` dizisi başında, `str` türünde bir nesneye dönüştürülür `Elem` çağırarak `_Ostr.` [put](../standard-library/basic-ostream-class.md#put)( `_Ostr.` [widen](../standard-library/basic-ios-class.md#widen)( `_Ch`)).  
  
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
  
 dışında `_Ch` türünde bir nesneye dönüştürülür `Elem` çağırarak `_Ostr.put`( `_Ostr.widen`( `_Ch`)).  
  
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
  
 (Bu öğeleri eklemeden önce genişletmek yok.)  
  
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
  
 (Genişletmek yok `_Ch` eklemeden önce.)  
  
 Şablon işlevi  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```  
  
 döndürür `_Ostr` << ( `const char *`) `str`.  
  
 Şablon işlevi  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```  
  
 döndürür `_Ostr` << ( `char`) `_Ch`.  
  
 Şablon işlevi:  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```  
  
 döndürür `_Ostr` << ( `const char *`) `str`.  
  
 Şablon işlevi:  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```  
  
 döndürür `_Ostr` << ( `char`) `_Ch`.  
  
 Şablon işlevi:  
  
```cpp  
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```  
  
 döndürür `_Ostr` `<<` `val` (ve dönüştüren bir [RValue başvuru](../cpp/rvalue-reference-declarator-amp-amp.md) için `_Ostr` işleminde bir lvalue için).  
  
### <a name="example"></a>Örnek  
  Bkz: [Temizleme](../standard-library/ostream-functions.md#flush) kullanarak bir örnek için `operator<<`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<ostream >](../standard-library/ostream.md)



