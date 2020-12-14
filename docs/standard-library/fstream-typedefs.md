---
description: 'Daha fazla bilgi edinin: &lt; fstream &gt; tür tanımları'
title: '&lt;fstream &gt; tür tanımları'
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
ms.openlocfilehash: cf3a7d686bb1e6d6004aaf91fa50294225f0362d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232258"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream &gt; tür tanımları

[filebuf](#filebuf)\
[fstream](#fstream)\
[ifstream](#ifstream)\
[ofstream](#ofstream)\
[wfilebuf](#wfilebuf)\
[wfstream](#wfstream)\
[wifstream](#wifstream)\
[wofstream](#wofstream)

## <a name="filebuf"></a><a name="filebuf"></a> filebuf

`basic_filebuf`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-filebuf-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_filebuf sınıf şablonu için bir eş anlamlıdır.

## <a name="fstream"></a><a name="fstream"></a> fstream

`basic_fstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-fstream-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_fstream sınıf şablonu için bir eş anlamlıdır.

## <a name="ifstream"></a><a name="ifstream"></a> ifstream

Bir dosyadan tek baytlık karakter verilerini okumak için kullanılacak bir akış tanımlar. `ifstream` , için sınıf şablonunu özelleştirtiren bir typedef `basic_ifstream` **`char`** .

`wifstream` `basic_ifstream` Çift geniş karakterleri okumak için uzmanlaşmış bir typedef de vardır **`wchar_t`** . Daha fazla bilgi için bkz. [wifstream](../standard-library/fstream-typedefs.md#wifstream).

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

## <a name="ofstream"></a><a name="ofstream"></a> ofstream

`basic_ofstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-ofstream-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ofstream sınıf şablonu için bir eş anlamlıdır.

## <a name="wfstream"></a><a name="wfstream"></a> wfstream

`basic_fstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-fstream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_fstream sınıf şablonu için bir eş anlamlıdır.

## <a name="wifstream"></a><a name="wifstream"></a> wifstream

`basic_ifstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-ifstream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ifstream sınıf şablonu için bir eş anlamlıdır.

## <a name="wofstream"></a><a name="wofstream"></a> wofstream

`basic_ofstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-ofstream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ofstream sınıf şablonu için bir eş anlamlıdır.

## <a name="wfilebuf"></a><a name="wfilebuf"></a> wfilebuf

`basic_filebuf`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-filebuf-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_filebuf sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream>](../standard-library/fstream.md)
