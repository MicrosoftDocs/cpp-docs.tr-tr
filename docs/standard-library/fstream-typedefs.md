---
title: '&lt;fstream&gt; tür tanımları'
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
ms.openlocfilehash: 6144826254c6acc509db2c0285b21811fe37bd4e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454049"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; tür tanımları

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>filebuf

Char şablon `basic_filebuf` parametreleri üzerinde  özelleştirilmiş bir tür.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_filebuf](../standard-library/basic-filebuf-class.md)için bir eş anlamlıdır.

## <a name="fstream"></a>fstream

Char şablon `basic_fstream` parametreleri üzerinde  özelleştirilmiş bir tür.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_fstream](../standard-library/basic-fstream-class.md)için bir eş anlamlıdır.

## <a name="ifstream"></a>ifstream

Bir dosyadan tek baytlık karakter verilerini okumak için kullanılacak bir akış tanımlar. `ifstream`, `basic_ifstream` **char**için şablon sınıfını özelleştirtiren bir typedef.

Ayrıca, `wifstream` **wchar_t** çift geniş karakterleri okumak `basic_ifstream` için uzmanlaşmış bir typedef de vardır. Daha fazla bilgi için bkz. [wifstream](../standard-library/fstream-typedefs.md#wifstream).

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile char türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_ifstream](../standard-library/basic-ifstream-class.md)için bir eş anlamlıdır. Örnek,

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a>ofstream

Char şablon `basic_ofstream` parametreleri üzerinde  özelleştirilmiş bir tür.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_ofstream](../standard-library/basic-ofstream-class.md)için bir eş anlamlıdır.

## <a name="wfstream"></a>wfstream

Wchar_t şablon `basic_fstream` parametrelerine özel  bir tür.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_fstream](../standard-library/basic-fstream-class.md)için bir eş anlamlıdır.

## <a name="wifstream"></a>wifstream

Wchar_t şablon `basic_ifstream` parametrelerine özel  bir tür.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_ifstream](../standard-library/basic-ifstream-class.md)için bir eş anlamlıdır.

## <a name="wofstream"></a>wofstream

Wchar_t şablon `basic_ofstream` parametrelerine özel  bir tür.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_ofstream](../standard-library/basic-ofstream-class.md)için bir eş anlamlıdır.

## <a name="wfilebuf"></a>wfilebuf

Wchar_t şablon `basic_filebuf` parametrelerine özel  bir tür.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_filebuf](../standard-library/basic-filebuf-class.md)için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)
