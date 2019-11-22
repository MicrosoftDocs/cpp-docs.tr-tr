---
title: C++Standart Kitaplık üst bilgi dosyaları
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: 807e65c69e55d8790b77a493e4ae1878aa740557
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305407"
---
# <a name="c-standard-library-header-files"></a>C++Standart Kitaplık üst bilgi dosyaları

Kategoriye göre C++ standart kitaplık ve uzantılar için üst bilgi dosyaları.

## <a name="headers-by-category"></a>Kategoriye göre üstbilgiler

::: moniker range=">=vs-2017"

| Kategori | bilgisinde |
| - | - |
| [Algoritmalar](../cpp/algorithms-modern-cpp.md) | [\<algoritması >](algorithm.md), [\<cstdlib >](cstdlib.md), [\<sayısal >](numeric.md) |
| Atomik işlemler |  [\<atomik >](atomic.md)<sup>11</sup> |
| C Kitaplığı sarmalayıcıları | [\<cassert >](cassert.md), [\<ccomplex >](ccomplex.md)<sup>11 a b</sup>, [\<cctype >](cctype.md), [\<cerrno >](cerrno.md), [\<cfenv >](cfenv.md)<sup>11</sup>,\<[cfloat >](cfloat.md), [\<cinttypes >](cinttypes.md)<sup>11</sup>,\<[ciso646 >](ciso646.md)<sup>b</sup>,\<[climits >](climits.md), [\<clocale >](clocale.md), [\<cmath >](cmath.md), [\<csetjmp >](csetjmp.md), [\<csignal >](csignal.md), [\<cstdalıgn >](cstdalign.md)<sup>11 a b</sup>, [\<cstdarg >](cstdarg.md), [\<cstdbool >](cstdbool.md)<sup>11 a b</sup>, [\<cstddef](cstddef.md)>, [\<cstdınt](cstdint.md)<sup>> 11</sup>, [\<cstdio >](cstdio.md),\<[cstdlib >](cstdlib.md), [\<CString >](cstring.md),\<[ctgmath](ctgmath.md)><sup>11 a b</sup>,\<[CTime >](ctime.md),\<[cuchar](cuchar.md)><sup>11</sup> [\<cwchar >](cwchar.md), [\<cwctype >](cwctype.md) |
| Kavramlar | \<kavramlar ><sup>20</sup> |
| [Kapsayıcılar](../cpp/containers-modern-cpp.md) | |
| Dizi kapsayıcıları | [\<dizi >](array.md)<sup>11</sup> [\<deque >](deque.md), [\<forward_list](forward-list.md)><sup>11</sup>, [\<List >](list.md),\<[Vector >](vector.md) |
| Sıralı ilişkilendirilebilir kapsayıcılar| [\<eşleme >](map.md) [\<kümesi >](set.md) |
| Sırasız ilişkilendirilebilir kapsayıcılar | [\<unordered_map >](unordered-map.md)<sup>11</sup>, [\<unordered_set >](unordered-set.md)<sup>11</sup> |
| Kapsayıcı bağdaştırıcıları | [\<kuyruğu >](queue.md) [\<Stack >](stack.md) |
| Kapsayıcı görünümleri | \<span ><sup>20</sup> |
| [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md) | [\<cassert >](cassert.md), [\<özel durum >](exception.md), [\<stdexcept >](stdexcept.md), [\<system_error](system-error.md)><sup>11</sup> |
| Genel yardımcı programlar | \<><sup>17</sup>, [\<bitset >](bitset.md), \<charconv ><sup>17</sup>, [\<cstdlib >](cstdlib.md), \<yürütme ><sup>17</sup>, [\<işlevsel >](functional.md),\<[bellek >](memory.md), \<memory_resource ><sup>17</sup>, \<isteğe bağlı ><sup>17</sup>,\<[Ratio >](ratio.md)<sup>11</sup>, [\<scoped_allocator >](scoped-allocator.md)<sup>11</sup>, [\<kayıt >](tuple.md)<sup>11</sup> [\<type_traits >](type-traits.md)<sup>11</sup>, [\<typeındex >](typeindex.md)<sup>11</sup>, [\<yardımcı programı >](utility.md), \<varyant ><sup>17</sup> |
| [G/ç ve biçimlendirme](../text/string-and-i-o-formatting-modern-cpp.md) | [\<cinttypes >](cinttypes.md)<sup>11</sup>, [\<cstdio >](cstdio.md), [\<filesystem >](filesystem.md)<sup>17</sup>, [\<fstream >](fstream.md), [\<iomanıp >](iomanip.md), [\<iOS >](ios.md), [\<iosfwd](iosfwd.md)>,\<[iostream](iostream.md)>, [\<IStream](istream.md) [](strstream.md)> [,\<](sstream.md) [ostream](ostream.md) [>,\<](streambuf.md)<sup> </sup>, \<syncstream ><sup>20</sup>\<\< |
| Yineleyiciler | [\<Yineleyici >](iterator.md) |
| Dil desteği | [\<cfloat >](cfloat.md), [\<climits >](climits.md), [\<codecvt >](codecvt.md)<sup>11 a</sup>, \<Compare ><sup>20</sup>, \<<sup>anlaşma > 20, \<</sup>coroutine ><sup>20</sup>,\<[csetjmp >](csetjmp.md), [\<csignal](csignal.md)>, [\<cstdarg >](cstdarg.md) [\<>](cstdlib.md)cstddef\<, [](cstdint.md)<sup></sup>> [özel durum](exception.md)\<[](cstddef.md) [\<initializer_list >](initializer-list.md)<sup>11</sup> [\<sınırlar >](limits.md), [\<yeni >](new.md), [\<TypeInfo >](typeinfo.md), \<sürüm ><sup>20</sup>\< |
| Yerelleştirme | [\<clocale >](clocale.md), [\<codecvt >](codecvt.md)<sup>11 a</sup>, [\<CVT/wbuffer](cvt-wbuffer.md)>,\<[cvt/wstrıng](cvt-wstring.md)>,\<[locale >](locale.md) |
| Matematik ve sayı | \<bit ><sup>20</sup>, [\<cfenv >](cfenv.md)<sup>11</sup>, [\<cmath >](cmath.md), [\<karmaşık >](complex.md), [\<cstdlib](cstdlib.md)>, [\<limit >](limits.md), [\<](numeric.md) [>](ratio.md)<sup></sup>, [\<>](random.md)\<<sup>11</sup> [](valarray.md)\< |
| [Bellek yönetimi](../cpp/smart-pointers-modern-cpp.md) | [\<ayrıcılar >](allocators-header.md), [\<bellek >](memory.md), \<memory_resource ><sup>17</sup>, [\<yeni >](new.md), [\<](scoped-allocator.md)scoped_allocator ><sup>11</sup> |
| İş | [\<atomik >](atomic.md)<sup>11</sup>, [\<condition_variable >](condition-variable.md)<sup>11</sup>, [\<gelecek >](future.md)<sup>11</sup>, [\<mutex >](mutex.md)<sup>11</sup>, [\<shared_mutex >](shared-mutex.md)<sup>14</sup>, [\<iş parçacığı >](thread.md)<sup>11</sup> |
| Aralıklar | \<aralıkları ><sup>20</sup> |
| Normal ifadeler | [\<regex >](regex.md)<sup>11</sup> |
| Dizeler ve karakter verileri | [\<cctype >](cctype.md), [\<cstdlib >](cstdlib.md), [\<CString >](cstring.md), [\<cuchar >](cuchar.md)<sup>11</sup>, [\<cwchar](cwchar.md)>, [\<cwctype >](cwctype.md),\<[Regex >](regex.md)<sup>11</sup>, [\<dize >](string.md),\<[string_view >](string-view.md)<sup>17</sup> |
| Time | [\<hatası >](chrono.md)<sup>11</sup> [\<CTime >](ctime.md) |

<sup>11</sup> c++ 11 standardına eklenmiştir. \
<sup>14</sup> c++ 14 standardına eklendi. \
<sup>17</sup> c++ 17 standardına eklendi. \
<sup>20</sup> , taslak c++ 20 standardına eklenmiştir. \
C++ 17 <sup>standardında kullanım dışı</sup> . \
<sup>b</sup> , taslak c++ 20 standardına göre kaldırılır. \
<sup>c</sup> , c++ 98 standardında kullanım dışıdır.

::: moniker-end

::: moniker range="vs-2015"

|Kategori|bilgisinde|
|-|-|
|[Algoritmalar](../cpp/algorithms-modern-cpp.md)|[\<algoritması >](algorithm.md)|
|C Kitaplığı sarmalayıcıları|[\<cassert >](cassert.md), [\<cctype >](cctype.md), [\<cerrno >](cerrno.md), [\<cfenv >](cfenv.md),\<[cfloat >](cfloat.md), [\<cinttypes >](cinttypes.md),\<[ciso646 >](ciso646.md),\<[climits >](climits.md), [\<clocale >](clocale.md),\<[cmath](cmath.md)>,\<[](cstdarg.md) [csetjmp](csetjmp.md)>, [\<](csignal.md) [cstdbool >](cstdbool.md) [\<cstddef >](cstddef.md), [\<cstdint >](cstdint.md),\<[cstdio >](cstdio.md),\<[cstdlib >](cstdlib.md), [\<CString >](cstring.md), [\<ctgmath >](ctgmath.md),\<[CTime >](ctime.md),\<[cwchar >](cwchar.md), [\<cwctype >](cwctype.md)\<\<|
|[Kapsayıcılar](../cpp/containers-modern-cpp.md)||
|Dizi kapsayıcıları|[\<dizi >](array.md), [\<deque >](deque.md),\<[forward_list](forward-list.md)>, [\<List >](list.md),\<[Vector >](vector.md)|
|Sıralı ilişkilendirilebilir kapsayıcılar| [\<eşleme >](map.md) [\<kümesi >](set.md)|
|Sırasız ilişkilendirilebilir kapsayıcılar|[\<unordered_map >](unordered-map.md), [\<unordered_set >](unordered-set.md)|
|Bağdaştırıcı kapsayıcıları|[\<kuyruğu >](queue.md) [\<Stack >](stack.md)|
|[Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)|[\<özel durum >](exception.md), [\<stdexcept >](stdexcept.md), [\<system_error >](system-error.md)|
|[G/ç ve biçimlendirme](../text/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem >](filesystem.md), [\<fstream >](fstream.md), [\<iomanip >](iomanip.md),\<[iOS >](ios.md), [\<iosfwd >](iosfwd.md), [\<iostream >](iostream.md), [\<IStream](istream.md)>,\<[ostream](ostream.md)>,\<[sstream](sstream.md)>,\<[streamarabelleğe](streambuf.md)>,\<[strstream](strstream.md) >|
|Yineleyiciler|[\<Yineleyici >](iterator.md)|
|Yerelleştirme|[\<codecvt >](codecvt.md), [\<CVT/wbuffer >](cvt-wbuffer.md), [\<cvt/wstring >](cvt-wstring.md), [\<locale >](locale.md)|
|Matematik ve sayı|[\<karmaşık >](complex.md), [\<limitleri >](limits.md), [\<sayısal >](numeric.md), [\<rastgele >](random.md), [\<Ratio >](ratio.md), [\<valarray >](valarray.md)|
|[Bellek Yönetimi](../cpp/smart-pointers-modern-cpp.md)|[\<ayrıcılar >](allocators-header.md), [\<bellek >](memory.md), [\<yeni >](new.md), [\<](scoped-allocator.md) scoped_allocator >|
|İş|[\<atomik >](atomic.md), [\<condition_variable >](condition-variable.md)\<[>\<,](future.md)> [mutex\<](mutex.md), shared_mutex [>](shared-mutex.md)\<> [iş parçacığı](thread.md)|
|Diğer yardımcı programlar|[\<bitset >](bitset.md), [\<ako >](chrono.md), [\<işlevsel >](functional.md), [\<initializer_list >](initializer-list.md), [\<demet >](tuple.md),\<[type_traits >](type-traits.md), [\<TypeInfo >](typeinfo.md), [\<typeındex >](typeindex.md), [\<yardımcı >](utility.md)|
|Dizeler ve karakter verileri|[\<regex >](regex.md), [\<dize >](string.md), [\<](string-view.md) string_view >

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık C++ üstbilgilerini kullanma](using-cpp-library-headers.md)\
[C++Standart Kitaplık](cpp-standard-library-reference.md)
