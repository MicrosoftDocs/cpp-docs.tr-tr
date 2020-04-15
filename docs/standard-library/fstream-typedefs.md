---
title: '&lt;fstream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: 57e481c131a6e4a1111b1ed88217b891d6fc96a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317187"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[Ifstream](#ifstream)|
|[Ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a><a name="filebuf"></a>filebuf

**Char** `basic_filebuf` şablon parametreleri üzerinde uzmanlaşmış bir tür.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Açıklamalar

Türü sınıf şablonu [basic_filebuf](../standard-library/basic-filebuf-class.md)için eşanlamlıdır, varsayılan karakter özellikleri ile tür **char** öğeleri için özel.

## <a name="fstream"></a><a name="fstream"></a>fstream

**Char** `basic_fstream` şablon parametreleri üzerinde uzmanlaşmış bir tür.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip **tür char** öğeleri için özelleştirilmiş sınıf [şablonu basic_fstream](../standard-library/basic-fstream-class.md)eşanlamlıdır.

## <a name="ifstream"></a><a name="ifstream"></a>Ifstream

Bir dosyadan tek bayt karakter verilerini seri olarak okumak için kullanılacak bir akışı tanımlar. `ifstream``basic_ifstream` **char**için sınıf şablonu uzmanlaşmış bir typedef olduğunu.

Ayrıca, `wifstream`çift geniş karakterler `basic_ifstream` **wchar_t** okumak için uzmanlaşmış bir typedef vardır. Daha fazla bilgi için [wifstream'e](../standard-library/fstream-typedefs.md#wifstream)bakın.

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip tür char öğeleri için özelleştirilmiş sınıf şablonu [basic_ifstream](../standard-library/basic-ifstream-class.md)eşanlamlıdır. Bir örnek

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a><a name="ofstream"></a>Ofstream

**Char** `basic_ofstream` şablon parametreleri üzerinde uzmanlaşmış bir tür.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip **tür char** öğeleri için özelleştirilmiş sınıf şablonu [basic_ofstream](../standard-library/basic-ofstream-class.md)eşanlamlıdır.

## <a name="wfstream"></a><a name="wfstream"></a>wfstream

şablon `basic_fstream` **parametreleri wchar_t** özelleştirilmiş bir tür.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip tür **wchar_t** öğeleri için özelleştirilmiş sınıf şablonu [basic_fstream](../standard-library/basic-fstream-class.md)eşanlamlıdır.

## <a name="wifstream"></a><a name="wifstream"></a>wifstream

şablon `basic_ifstream` **parametreleri wchar_t** özelleştirilmiş bir tür.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip tür **wchar_t** öğeleri için özelleştirilmiş sınıf [şablonu basic_ifstream](../standard-library/basic-ifstream-class.md)eşanlamlıdır.

## <a name="wofstream"></a><a name="wofstream"></a>wofstream

şablon `basic_ofstream` **parametreleri wchar_t** özelleştirilmiş bir tür.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [basic_ofstream](../standard-library/basic-ofstream-class.md)ile eş anlamlıdır, varsayılan karakter özelliklerine sahip **tür wchar_t** öğeleri için özelleştirilmiştir.

## <a name="wfilebuf"></a><a name="wfilebuf"></a>wfilebuf

şablon `basic_filebuf` **parametreleri wchar_t** özelleştirilmiş bir tür.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip tür **wchar_t** öğeleri için özelleştirilmiş sınıf şablonu [basic_filebuf](../standard-library/basic-filebuf-class.md)eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream>](../standard-library/fstream.md)
