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
ms.openlocfilehash: d5a4b0e2d671bb787501767d4321bd3ed61deb88
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159545"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; tür tanımları

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>  filebuf

Bir tür `basic_filebuf` üzerinde özelleştirilmiş **char** şablon parametreleri.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_filebuf](../standard-library/basic-filebuf-class.md), türü öğeler için özelleştirilmiş **char** varsayılan karakter nitelikleri ile.

## <a name="fstream"></a>  fstream

Bir tür `basic_fstream` üzerinde özelleştirilmiş **char** şablon parametreleri.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_fstream](../standard-library/basic-fstream-class.md), türü öğeler için özelleştirilmiş **char** varsayılan karakter nitelikleri ile.

## <a name="ifstream"></a>  ifstream

Tek baytlı karakter verilerini bir dosyadan seri olarak okumak için kullanılacak bir akışı tanımlar. `ifstream` Şablon sınıfı uzmanlaşmış bir TypeDef `basic_ifstream` için **char**.

Ayrıca `wifstream`, uzmanlaşmış bir typedef `basic_ifstream` okunacak **wchar_t** çift-geniş karakter. Daha fazla bilgi için [wifstream](../standard-library/fstream-typedefs.md#wifstream).

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ifstream](../standard-library/basic-ifstream-class.md), char türü ile varsayılan karakter nitelikleri öğeler için özelleştirilmiş. Bir örnek verilmiştir

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a>  ofstream

Bir tür `basic_ofstream` üzerinde özelleştirilmiş **char** şablon parametreleri.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ofstream](../standard-library/basic-ofstream-class.md), türü öğeler için özelleştirilmiş **char** varsayılan karakter nitelikleri ile.

## <a name="wfstream"></a>  wfstream

Bir tür `basic_fstream` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_fstream](../standard-library/basic-fstream-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="wifstream"></a>  wifstream

Bir tür `basic_ifstream` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ifstream](../standard-library/basic-ifstream-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="wofstream"></a>  wofstream

Bir tür `basic_ofstream` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ofstream](../standard-library/basic-ofstream-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="wfilebuf"></a>  wfilebuf

Bir tür `basic_filebuf` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_filebuf](../standard-library/basic-filebuf-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)<br/>
