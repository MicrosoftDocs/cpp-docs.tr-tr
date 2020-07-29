---
title: C++ standart kitaplığı üstbilgi dosyaları
ms.date: 07/23/2020
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: 845fda9e020727b71752f19c38bb8432d5cf7c25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228303"
---
# <a name="c-standard-library-header-files"></a>C++ standart kitaplığı üstbilgi dosyaları

C++ standart kitaplığı ve uzantıları kategorisine göre üst bilgi dosyaları.

## <a name="headers-by-category"></a>Kategoriye göre üstbilgiler

::: moniker range=">=vs-2017"

| Kategori | Üst bilgiler |
| - | - |
| [Algoritmalar](../cpp/algorithms-modern-cpp.md) | [\<algorithm>](algorithm.md), [\<cstdlib>](cstdlib.md), [\<numeric>](numeric.md) |
| Atomik işlemler |  [\<atomic>](atomic.md)<sup>üst</sup> |
| C Kitaplığı sarmalayıcıları | [\<cassert>](cassert.md), [\<ccomplex>](ccomplex.md) <sup>11 a b</sup>, [\<cctype>](cctype.md) , [\<cerrno>](cerrno.md) , [\<cfenv>](cfenv.md) <sup>11</sup>, [\<cfloat>](cfloat.md) , [\<cinttypes>](cinttypes.md) <sup>11</sup>, [\<ciso646>](ciso646.md) <sup>b</sup>, [\<climits>](climits.md) , [\<clocale>](clocale.md) , [\<cmath>](cmath.md) , [\<csetjmp>](csetjmp.md) , [\<csignal>](csignal.md) , [\<cstdalign>](cstdalign.md) <sup>11 a b</sup>, [\<cstdarg>](cstdarg.md) , [\<cstdbool>](cstdbool.md) <sup>11 a</sup>b,, 11 [\<cstddef>](cstddef.md) [\<cstdint>](cstdint.md) <sup>11</sup>, [\<cstdio>](cstdio.md) , [\<cstdlib>](cstdlib.md) , [\<cstring>](cstring.md) , [\<ctgmath>](ctgmath.md) <sup>11 a b</sup>, [\<ctime>](ctime.md) , [\<cuchar>](cuchar.md) <sup>11</sup>, [\<cwchar>](cwchar.md) ,[\<cwctype>](cwctype.md) |
| Kavramlar | \<concepts><sup>2.0</sup> |
| [Kapsayıcılar](../cpp/containers-modern-cpp.md) | |
| Dizi kapsayıcıları | [\<array>](array.md)<sup>11</sup>, [\<deque>](deque.md) , [\<forward_list>](forward-list.md) <sup>11</sup>, [\<list>](list.md) ,[\<vector>](vector.md) |
| Sıralı ilişkilendirilebilir kapsayıcılar| [\<map>](map.md), [\<set>](set.md) |
| Sırasız ilişkilendirilebilir kapsayıcılar | [\<unordered_map>](unordered-map.md)<sup>11</sup>, [\<unordered_set>](unordered-set.md) <sup>11</sup> |
| Kapsayıcı bağdaştırıcıları | [\<queue>](queue.md), [\<stack>](stack.md) |
| Kapsayıcı görünümleri | [\<span>](span.md)<sup>2.0</sup> |
| [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md) | [\<cassert>](cassert.md), [\<exception>](exception.md) , [\<stdexcept>](stdexcept.md) , [\<system_error>](system-error.md) <sup>11</sup> |
| Genel yardımcı programlar | \<any><sup>17</sup>, [\<bitset>](bitset.md) , [\<cstdlib>](cstdlib.md) , \<execution> <sup>17</sup>, [\<functional>](functional.md) , [\<memory>](memory.md) , \<memory_resource> <sup>17</sup>, \<optional> <sup>17</sup>, [\<ratio>](ratio.md) <sup>11</sup>, [\<scoped_allocator>](scoped-allocator.md) <sup>11</sup>, [\<tuple>](tuple.md) <sup>11</sup>, [\<type_traits>](type-traits.md) <sup>11</sup>, [\<typeindex>](typeindex.md) <sup>11</sup>, [\<utility>](utility.md) , \<variant> <sup>17</sup> |
| [G/ç ve biçimlendirme](../text/string-and-i-o-formatting-modern-cpp.md) | [\<cinttypes>](cinttypes.md)<sup>11</sup>, [\<cstdio>](cstdio.md) , [\<filesystem>](filesystem.md) <sup>17</sup>, [\<fstream>](fstream.md) , [\<iomanip>](iomanip.md) , [\<ios>](ios.md) , [\<iosfwd>](iosfwd.md) , [\<iostream>](iostream.md) , [\<istream>](istream.md) , [\<ostream>](ostream.md) , [\<sstream>](sstream.md) , [\<streambuf>](streambuf.md) , [\<strstream>](strstream.md) <sup>c</sup>, \<syncstream> <sup>20</sup> |
| Yineleyiciler | [\<iterator>](iterator.md) |
| Dil desteği | [\<cfloat>](cfloat.md), [\<climits>](climits.md) , [\<codecvt>](codecvt.md) <sup>11 a</sup>, \<compare> <sup>20</sup>, \<contract> <sup>20</sup>, \<coroutine> <sup>20</sup>, [\<csetjmp>](csetjmp.md) , [\<csignal>](csignal.md) , [\<cstdarg>](cstdarg.md) , [\<cstddef>](cstddef.md) , 11,,, [\<cstdint>](cstdint.md) <sup>11</sup> [\<cstdlib>](cstdlib.md) [\<exception>](exception.md) [\<initializer_list>](initializer-list.md) <sup>11</sup>, [\<limits>](limits.md) , [\<new>](new.md) , [\<typeinfo>](typeinfo.md) , \<version> <sup>20</sup> |
| Yerelleştirme | [\<clocale>](clocale.md), [\<codecvt>](codecvt.md) <sup>11 a</sup>, [\<cvt/wbuffer>](cvt-wbuffer.md) , [\<cvt/wstring>](cvt-wstring.md) ,[\<locale>](locale.md) |
| Matematik ve sayı | \<bit><sup>20</sup>, [\<cfenv>](cfenv.md) <sup>11</sup>, [\<cmath>](cmath.md) , [\<complex>](complex.md) , [\<cstdlib>](cstdlib.md) , [\<limits>](limits.md) , [\<numeric>](numeric.md) , [\<random>](random.md) <sup>11</sup>, [\<ratio>](ratio.md) <sup>11</sup>,[\<valarray>](valarray.md) |
| [Bellek yönetimi](../cpp/smart-pointers-modern-cpp.md) | [\<allocators>](allocators-header.md), [\<memory>](memory.md) , \<memory_resource> <sup>17</sup>, [\<new>](new.md) , [\<scoped_allocator>](scoped-allocator.md) <sup>11</sup> |
| Çoklu iş parçacığı kullanımı | [\<atomic>](atomic.md)<sup>11</sup>, [\<condition_variable>](condition-variable.md) <sup>11</sup>, [\<future>](future.md) <sup>11</sup>, [\<mutex>](mutex.md) <sup>11</sup>, [\<shared_mutex>](shared-mutex.md) <sup>14</sup>, [\<thread>](thread.md) <sup>11</sup> |
| Aralıklar | \<ranges><sup>2.0</sup> |
| Normal ifadeler | [\<regex>](regex.md)<sup>üst</sup> |
| Dizeler ve karakter verileri | [\<charconv>](charconv.md)<sup>17</sup>, [\<cctype>](cctype.md) , [\<cstdlib>](cstdlib.md) , [\<cstring>](cstring.md) , [\<cuchar>](cuchar.md) <sup>11</sup>, [\<cwchar>](cwchar.md) , [\<cwctype>](cwctype.md) , [\<regex>](regex.md) <sup>11</sup>, [\<string>](string.md) , [\<string_view>](string-view.md) <sup>17</sup> |
| Zaman | [\<chrono>](chrono.md)<sup>11</sup>,[\<ctime>](ctime.md) |

<sup>11</sup> c++ 11 standardına eklenmiştir. \
<sup>14</sup> c++ 14 standardına eklendi. \
<sup>17</sup> c++ 17 standardına eklendi. \
<sup>20</sup> , taslak c++ 20 standardına eklenmiştir. \
C++ 17 <sup>standardında kullanım dışı</sup> . \
<sup>b</sup> , taslak c++ 20 standardına göre kaldırılır. \
<sup>c</sup> , c++ 98 standardında kullanım dışıdır.

::: moniker-end

::: moniker range="vs-2015"

|Kategori|Üst bilgiler|
|-|-|
|[Algoritmalar](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|C Kitaplığı sarmalayıcıları|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[Kapsayıcılar](../cpp/containers-modern-cpp.md)||
|Dizi kapsayıcıları|[\<array>](array.md), [\<deque>](deque.md), [\<forward_list>](forward-list.md), [\<list>](list.md), [\<vector>](vector.md)|
|Sıralı ilişkilendirilebilir kapsayıcılar| [\<map>](map.md), [\<set>](set.md)|
|Sırasız ilişkilendirilebilir kapsayıcılar|[\<unordered_map>](unordered-map.md), [\<unordered_set>](unordered-set.md)|
|Bağdaştırıcı kapsayıcıları|[\<queue>](queue.md), [\<stack>](stack.md)|
|[Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)|[\<exception>](exception.md), [\<stdexcept>](stdexcept.md), [\<system_error>](system-error.md)|
|[G/ç ve biçimlendirme](../text/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|Yineleyiciler|[\<iterator>](iterator.md)|
|Yerelleştirme|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|Matematik ve sayı|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[Bellek yönetimi](../cpp/smart-pointers-modern-cpp.md)|[\<allocators>](allocators-header.md), [\<memory>](memory.md), [\<new>](new.md), [\<scoped_allocator>](scoped-allocator.md)|
|Çoklu iş parçacığı kullanımı|[\<atomic>](atomic.md), [\<condition_variable>](condition-variable.md), [\<future>](future.md), [\<mutex>](mutex.md), [\<shared_mutex>](shared-mutex.md), [\<thread>](thread.md)|
|Diğer yardımcı programlar|[\<bitset>](bitset.md), [\<chrono>](chrono.md), [\<functional>](functional.md), [\<initializer_list>](initializer-list.md), [\<tuple>](tuple.md), [\<type_traits>](type-traits.md), [\<typeinfo>](typeinfo.md), [\<typeindex>](typeindex.md), [\<utility>](utility.md)|
|Dizeler ve karakter verileri|[\<regex>](regex.md), [\<string>](string.md), [\<string_view>](string-view.md)

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[C++ Kitaplığı üstbilgilerini kullanma](using-cpp-library-headers.md)\
[C++ standart kütüphanesi](cpp-standard-library-reference.md)
