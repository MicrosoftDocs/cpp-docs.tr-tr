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
ms.openlocfilehash: 3f4104b28f5becfdbf62ede16faa81e855fcac8c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421781"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; tür tanımları

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>filebuf

Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_filebuf`.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş [basic_filebuf](../standard-library/basic-filebuf-class.md)sınıf şablonu için bir eş anlamlı.

## <a name="fstream"></a>fstream

Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_fstream`.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş [basic_fstream](../standard-library/basic-fstream-class.md)sınıf şablonu için bir eş anlamlı.

## <a name="ifstream"></a>ifstream

Bir dosyadan tek baytlık karakter verilerini okumak için kullanılacak bir akış tanımlar. `ifstream`, **char**için `basic_ifstream` sınıf şablonunu özelleştirtiren bir typedef 'dir.

Ayrıca, **wchar_t** çift geniş karakterleri okumak için `basic_ifstream` uzmanlaşmış bir typedef `wifstream`de vardır. Daha fazla bilgi için bkz. [wifstream](../standard-library/fstream-typedefs.md#wifstream).

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile char türündeki öğeler için özelleştirilmiş [basic_ifstream](../standard-library/basic-ifstream-class.md)sınıf şablonu için bir eş anlamlı. Örnek,

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

Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_ofstream`.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş [basic_ofstream](../standard-library/basic-ofstream-class.md)sınıf şablonu için bir eş anlamlı.

## <a name="wfstream"></a>wfstream

Bir tür **wchar_t** şablon parametrelerine özelleştirilmiş `basic_fstream`.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_fstream](../standard-library/basic-fstream-class.md)sınıf şablonu için bir eş anlamlıdır.

## <a name="wifstream"></a>wifstream

Bir tür **wchar_t** şablon parametrelerine özelleştirilmiş `basic_ifstream`.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_ifstream](../standard-library/basic-ifstream-class.md)sınıf şablonu için bir eş anlamlıdır.

## <a name="wofstream"></a>wofstream

Bir tür **wchar_t** şablon parametrelerine özelleştirilmiş `basic_ofstream`.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_ofstream](../standard-library/basic-ofstream-class.md)sınıf şablonu için bir eş anlamlıdır.

## <a name="wfilebuf"></a>wfilebuf

Bir tür **wchar_t** şablon parametrelerine özelleştirilmiş `basic_filebuf`.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_filebuf](../standard-library/basic-filebuf-class.md)sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)
