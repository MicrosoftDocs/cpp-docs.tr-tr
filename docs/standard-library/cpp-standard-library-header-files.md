---
title: C++Standart Kitaplık üst bilgi dosyaları
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: dc337ef078108d86849aa7b7452512dfb69e6e18
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341129"
---
# <a name="c-standard-library-header-files"></a>C++Standart Kitaplık üst bilgi dosyaları

Kategoriye göre C++ standart kitaplık ve uzantılar için üst bilgi dosyaları.

## <a name="headers-by-category"></a>Kategoriye göre üstbilgiler

::: moniker range=">=vs-2017"

| Kategori | Bilgisinde |
| - | - |
| [Algoritmalar](../cpp/algorithms-modern-cpp.md) | [ \<algoritma >](numeric.md) , [ \<cstdlib >](cstdlib.md), sayısal > [ \<](algorithm.md) |
| Atomik işlemler |  Atomik ><sup>11</sup> [ \<](atomic.md) |
| C Kitaplığı sarmalayıcıları | [ \<](cctype.md) [ \<](cfenv.md)<sup></sup><sup></sup> [ \<](cerrno.md) [ cassert\<>, ccomplex >](ccomplex.md)11 a b, cctype >, cerrno >, cfenv > 11, [ \<](cassert.md) [ \<cfloat >](cfloat.md), [ \<cinttypes >](cinttypes.md)<sup>11</sup>, [ \<ciso646 >](ciso646.md)<sup>b</sup>, [ \<climits >](climits.md), [ \<clocale >](clocale.md), [ \<cmath >](cmath.md) [ ,\<csetjmp >](csetjmp.md), [ \<csignal >](csignal.md), [ \<cstdalıgn >](cstdalign.md)<sup>11 a b</sup>, [ \<cstdarg >](cstdarg.md), [ \<cstdbool >](cstdbool.md)<sup>11 a b</sup>, [ \<cstddef >](cstddef.md), [ \<cstdint >](cstdint.md)<sup>11</sup>, [ \<cstdio >](cstdio.md), [ \<cstdlib >](cstdlib.md), [ CString\<>](cstring.md),<sup></sup> [ \<](cuchar.md) [ \<](ctime.md) [ \<](cwchar.md)<sup></sup> [ ctgmath>11ab,CTime>,cuchar>11\<](ctgmath.md), cwchar >, [ \<cwctype >](cwctype.md) |
| Kavramlar | \<kavramlar ><sup>20</sup> |
| [Kapsayıcılar](../cpp/containers-modern-cpp.md) | |
| Dizi kapsayıcıları | <sup></sup><sup></sup> [ \<](list.md) [ \<](vector.md) [ dizi>\<](forward-list.md)11, [ \<deque >](deque.md), forward_list > 11, liste >, vektör > [ \<](array.md) |
| Sıralı ilişkilendirilebilir kapsayıcılar| eşleme >, [ \<](map.md) [ >ayarla\<](set.md) |
| Sırasız ilişkilendirilebilir kapsayıcılar | unordered_map ><sup>11</sup>, [ unordered_set>\<](unordered-set.md)<sup>11</sup> [ \<](unordered-map.md) |
| Kapsayıcı bağdaştırıcıları | kuyruk >, [ \<](queue.md) [ yığın>\<](stack.md) |
| Kapsayıcı görünümleri | \<Aralık ><sup>20</sup> |
| [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md) | [ \<](stdexcept.md)<sup></sup> [ \<](system-error.md)cassert >, [ \<özel durum >](exception.md), stdexcept >, system_error > 11 [ \<](cassert.md) |
| Genel yardımcı programlar | \<Her ><sup>17</sup>, [ \<bitset >](bitset.md), \<charconv ><sup>17</sup>, [ \<cstdlib >](cstdlib.md), \<yürütme ><sup>17</sup>, [ \<işlevsel >](functional.md), [ bellek\<>](memory.md), \< [ \<](ratio.md)<sup></sup><sup></sup><sup></sup>memory_resource > 17, isteğe bağlı > 17, oran > 11, scoped_allocator > \< [ \< ](scoped-allocator.md) <sup>11</sup><sup></sup><sup></sup> [, demet\<>](tuple.md)11,<sup></sup> [ type_traits>\<](utility.md)11, [ \<typeındex >](typeindex.md)11, yardımcı program >, [ \<](type-traits.md) \<değişken ><sup>17</sup> |
| [G/ç ve biçimlendirme](../cpp/string-and-i-o-formatting-modern-cpp.md) | [ \<](filesystem.md)<sup></sup><sup></sup> [ \<](fstream.md) [ \<](cstdio.md) [ \<](iomanip.md) [ \<cinttypes >](cinttypes.md)11, cstdio >, FileSystem > 17, fstream >, iomanıp >, [ iOS\<>](ios.md), [ \<](istream.md) [ \<](iostream.md) [ \<](ostream.md) [ \<](sstream.md) [ıosfwd >, ıostream >, IStream >, ostream >, sstream > \<](iosfwd.md) \< [ ,\<streamarabelleğe >](streambuf.md), [ \<strstream >](strstream.md)<sup>c</sup>, syncstream ><sup>20</sup> |
| Yineleyiciler | [\<Yineleyici >](iterator.md) |
| Dil desteği | \< \<<sup></sup> \< <sup></sup><sup></sup> [ cfloat\<>, climits >](climits.md), [ \<codecvt >](codecvt.md)11 a, karşılaştırma > 20, sözleşme > 20, [ \<](cfloat.md) coroutine ><sup>20</sup>, [ \<csetjmp >](csetjmp.md), [ \<csignal >](csignal.md), [ \<cstdarg >](cstdarg.md), [ \<cstddef >](cstddef.md), [ \<cstdint > ](cstdint.md) <sup>11</sup><sup></sup> [ \<](initializer-list.md) [, \<cstdlib >](cstdlib.md), [ \<özel durum >](exception.md), initializer_list > 11, [ \<sınırlar >](limits.md), [ \< Yeni >](new.md), [ \<TypeInfo >](typeinfo.md), \<sürüm ><sup>20</sup> |
| Yerelleştirme | [ \<](locale.md) <sup></sup> [ \<](cvt-wbuffer.md) [ clocale\<>, codecvt >](codecvt.md)11 a, CVT/wbuffer >, [ \<CVT/wstrıng >](cvt-wstring.md), locale > [ \<](clocale.md) |
| Matematik ve sayı | \<bit ><sup>20</sup>, [ \<cfenv >](cfenv.md)<sup>11</sup>, [ \<cmath >](cmath.md), [ \<karmaşık >](complex.md), [ \<cstdlib >](cstdlib.md), [ \<sınırlar >](limits.md), [ Sayısal\<>](numeric.md),<sup></sup><sup></sup> [ rastgele\<>](random.md)11 [, oran>11,valarray>\<](ratio.md) [ \<](valarray.md) |
| [Bellek yönetimi](../cpp/smart-pointers-modern-cpp.md) | \< [ \<](new.md) [ \<](scoped-allocator.md)<sup></sup><sup></sup> [ \<](memory.md)ayrıcılar >, bellek >, memory_resource > 17, yeni >, scoped_allocator > 11 [ \<](allocators-header.md) |
| İş | <sup></sup><sup></sup><sup></sup><sup></sup> [ atomik\<>](atomic.md)11, [ condition_variable>11,gelecekteki>11,mutex>11,\<](condition-variable.md) [ \<](future.md) [ \<](mutex.md) [ \< shared_mutex >](shared-mutex.md)<sup>14</sup>, [ \<iş parçacığı >](thread.md)<sup>11</sup> |
| Aralıklar | \<aralıklar ><sup>20</sup> |
| Normal ifadeler | Regex ><sup>11</sup> [ \<](regex.md) |
| Dizeler ve karakter verileri | [ \<](cstring.md)<sup></sup> [ \<](cuchar.md) [ \<](cwchar.md) [ cctype\<>, cstdlib >](cstdlib.md), CString >, cuchar > 11, cwchar >, [ \<](cctype.md) [ \<cwctype >](cwctype.md) [ ,\<Regex >](regex.md)<sup>11</sup>, [ \<String >](string.md), [ \<string_view >](string-view.md)<sup>17</sup> |
| Zaman | zaman hatası ><sup>11</sup>, [ \<CTime >](ctime.md) [ \<](chrono.md) |

<sup>11</sup> c++ 11 standardına eklenmiştir. \
<sup>14</sup> c++ 14 standardına eklendi. \
<sup>17</sup> c++ 17 standardına eklendi. \
<sup>20</sup> , taslak c++ 20 standardına eklenmiştir. \
C++ 17 <sup>standardında kullanım dışı</sup> . \
<sup>b</sup> , taslak c++ 20 standardına göre kaldırılır. \
<sup>c</sup> , c++ 98 standardında kullanım dışıdır.

::: moniker-end

::: moniker range="vs-2015"

|Kategori|Bilgisinde|
|-|-|
|[Algoritmalar](../cpp/algorithms-modern-cpp.md)|[\<algoritma >](algorithm.md)|
|C Kitaplığı sarmalayıcıları|[ \<](cfloat.md) [ \<](cfenv.md) [ \<](cerrno.md) [ \<](cctype.md) [ \<](cinttypes.md) [ cassert\<>](cassert.md), cctype >, cerrno >, cfenv >, cfloat >, cinttypes >, [ ciso646\<>](ciso646.md) [, climits\<>](climits.md) [, \<clocale >](clocale.md) [ ,\<cmath >](cmath.md), [ \<csetjmp >](csetjmp.md), [ \<csignal >](csignal.md) [ ,\<cstdarg >](cstdarg.md), [ \<cstdbool >](cstdbool.md), [ \<cstddef >](cstddef.md), [ \<cstdint >](cstdint.md), [ \<cstdio >](cstdio.md), [ \<cstdlib >](cstdlib.md), [ \<CString >](cstring.md), [ \<ctgmath >](ctgmath.md), [ \<CTime >](ctime.md), [ \<cwchar >](cwchar.md), [ \<cwctype > ](cwctype.md)|
|[Kapsayıcılar](../cpp/containers-modern-cpp.md)||
|Dizi kapsayıcıları|[ dizi>\<](forward-list.md), [ \<deque >](deque.md), forward_list > [ ,\<List >](list.md), [ \<Vector >](vector.md) [ \<](array.md)|
|Sıralı ilişkilendirilebilir kapsayıcılar| eşleme >, [ \<](map.md) [ >ayarla\<](set.md)|
|Sırasız ilişkilendirilebilir kapsayıcılar|unordered_map >, [ \<](unordered-map.md) [ unordered_set>\<](unordered-set.md)|
|Bağdaştırıcı kapsayıcıları|kuyruk >, [ \<](queue.md) [ yığın>\<](stack.md)|
|[Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)|özel durum >, [ \<stdexcept >](stdexcept.md), [ \<system_error >](system-error.md) [ \<](exception.md)|
|[G/ç ve biçimlendirme](../cpp/string-and-i-o-formatting-modern-cpp.md)|[ \<](ios.md) [ \<](iostream.md) [ FileSystem>\<](iomanip.md), [ \<fstream >](fstream.md), ıomanıp >, iOS >, [ \<ıosfwd >](iosfwd.md), ıostream >, [ \<](filesystem.md) [ \<](streambuf.md) [ \<](sstream.md) [ \<](strstream.md) [ IStream\<>, ostream >](ostream.md), sstream >, streamarabelleğe >, strstream > [ \<](istream.md)|
|Yineleyiciler|[\<Yineleyici >](iterator.md)|
|Yerelleştirme|[ \<](locale.md) [ codecvt>\<](cvt-wstring.md), [ \<CVT/wbuffer >](cvt-wbuffer.md), CVT/wstring >, yerel ayar > [ \<](codecvt.md)|
|Matematik ve sayı|[ karmaşık\<>](complex.md), [ sınır>,sayısal>,rastgele>,oran>,valarray>\<](limits.md) [ \<](numeric.md) [ \<](random.md) [ \<](ratio.md) [ \<](valarray.md)|
|[Bellek Yönetimi](../cpp/smart-pointers-modern-cpp.md)|ayrıcılar >, [ \<bellek >](memory.md), [ \<yeni >](new.md), [ \<scoped_allocator >](scoped-allocator.md) [ \<](allocators-header.md)|
|İş|[ atomik\<>](atomic.md), [ condition_variable>,gelecekteki>,mutex>,shared_mutex>,işparçacığı\<](condition-variable.md) [ \<](future.md) [ \<](mutex.md) [ \<](shared-mutex.md) [ \< >](thread.md)|
|Diğer yardımcı programlar|[ \<](initializer-list.md) [ \<](functional.md) [ \<](tuple.md) [ bitset\<](chrono.md)>, zaman hatası >, işlevsel >, initializer_list >, demet >, type_traits [ \<](bitset.md) [ \< >](type-traits.md) [ ,\<TypeInfo >](typeinfo.md), [ \<typeındex >](typeindex.md), [ \<yardımcı program >](utility.md)|
|Dizeler ve karakter verileri|Regex > [, dize>\<](string.md), [ string_view\<>](string-view.md) [ \<](regex.md)

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık C++ üstbilgilerini kullanma](using-cpp-library-headers.md)\
[C++Standart Kitaplık](cpp-standard-library-reference.md)
