---
title: '&lt;iosfwd&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iosfwd>
helpviewer_keywords:
- iosfwd header
ms.assetid: 964442eb-17f1-43ef-a0e0-c5bb77f9c187
ms.openlocfilehash: 7b21e6e92c1fa1d01826ad8f6805d9a52b0fde42
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518326"
---
# <a name="ltiosfwdgt"></a>&lt;iosfwd&gt;

İostreams kullanılan birkaç şablon sınıfları İleri başvurulara bildirir. Bu şablonu sınıfları diğer standart üstbilgisinde tanımlanır. Yalnızca kendi bildirimleri, ancak kendi tanımının birini gerektiğinde bu başlığı açıkça içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <iosfwd>
```

## <a name="typedefs"></a>Tür tanımları

```cpp
typedef T1 streamoff;
typedef T2 streamsize;
typedef fpos streampos;

// wchar_t TYPE DEFINITIONS
typedef basic_ios<char, char_traits<char>> ios;
typedef basic_streambuf<char, char_traits<char>> streambuf;
typedef basic_istream<char, char_traits<char>> istream;
typedef basic_ostream<char, char_traits<char>> ostream;
typedef basic_iostream<char, char_traits<char>> iostream;
typedef basic_stringbuf<char, char_traits<char>> stringbuf;
typedef basic_istringstream<char, char_traits<char>> istringstream;
typedef basic_ostringstream<char, char_traits<char>> ostringstream;
typedef basic_stringstream<char, char_traits<char>> stringstream;
typedef basic_filebuf<char, char_traits<char>> filebuf;
typedef basic_ifstream<char, char_traits<char>> ifstream;
typedef basic_ofstream<char, char_traits<char>> ofstream;
typedef basic_fstream<char, char_traits<char>> fstream;

// wchar_t TYPE DEFINITIONS
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
typedef basic_stringbuf<wchar_t, char_traits<wchar_t>> wstringbuf;
typedef basic_istringstream<wchar_t, char_traits<wchar_t>> wistringstream;
typedef basic_ostringstream<wchar_t, char_traits<wchar_t>> wostringstream;
typedef basic_stringstream<wchar_t, char_traits<wchar_t>> wstringstream;
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
};
```

## <a name="forward-declarationstemplate-classes"></a>İletme bildirimleri/şablon sınıfları

```cpp
template <class _Statetype>
class fpos;

template <class Elem>;
class char_traits;

class char_traits<char>;

class char_traits<wchar_t>;

template <class T>
class allocator;

class ios_base;

template <class Elem, class Tr = char_traits<Elem>>
class basic_ios;

template <class Elem, class Tr = char_traits<Elem>>
class istreambuf_iterator;

template <class Elem, class Tr = char_traits<Elem>>
class ostreambuf_iterator;

template <class Elem, class Tr = char_traits<Elem>>
class basic_streambuf;

template <class Elem, class Tr = char_traits<Elem>>
class basic_istream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_stringbuf;

template <class Elem, class Tr = char_traits<Elem>>
class basic_istringstream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_ostringstream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_stringstream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf;

template <class Elem, class Tr = char_traits<Elem>>
class basic_ifstream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream;

template <class Elem, class Tr = char_traits<Elem>>
class basic_fstream;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
