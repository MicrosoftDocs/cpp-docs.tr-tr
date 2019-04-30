---
title: Dosya Sistemi Gezintisi
ms.date: 11/04/2016
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: cfdc789daab5b476566f2072109d23fb9310094f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405202"
---
# <a name="file-system-navigation"></a>Dosya Sistemi Gezintisi

\<Filesystem > Üstbilgi uygular C++ dosya sistemi teknik belirtimi ISO/IEC TS 18822:2015 (son taslak: [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)) ve türleri ve dosya sisteminde gezinmek için platformdan bağımsız kod yazmanıza olanak sağlayan işlevler içerir. Platformlar arası olduğundan, Windows sistemleri için ilgili olmayan API'leri içerir. Örneğin, yani `is_fifo(const path&)` her zaman döndürür **false** Windows üzerinde.

## <a name="overview"></a>Genel Bakış

Kullanım \<filesystem > API'leri aşağıdaki görevler için:

- dosyalar ve dizinler belirtilen yolun altındaki üzerinden yineleme yapma

- Dosya oluşturulma saati de dahil olmak üzere, boyutu, uzantı ve kök dizini hakkında bilgi edinin

- Oluştur, parçalayın ve yolları karşılaştırın

- oluşturma, kopyalama ve dizinleri silme

- dosyaları kopyalar ve siler

Dosya GÇ standart kitaplığı kullanma hakkında daha fazla bilgi için bkz. [iostream programlama](../standard-library/iostream-programming.md).

## <a name="paths"></a>Yolları

### <a name="constructing-and-composing-paths"></a>Yollar oluşturma ve oluşturma

Windows (XP itibaren) yollarında Unicode yerel olarak depolanır. [Yolu](../standard-library/path-class.md) sınıfı, tüm gerekli dize dönüştürmeleri otomatik olarak gerçekleştirir. Bağımsız değişkenleri iki geniş ve dar karakter dizileri kabul yanı `std::string` ve `std::wstring` türleri, UTF8 veya UTF16 olarak biçimlendirilmiş. `path` Sınıfı da otomatik olarak, yol ayırıcıları normalleştirir. Oluşturucu bağımsız dizin ayırıcı olarak eğik çizgi tek kullanabilirsiniz. Bu, hem Windows hem de UNIX ortamlarında yolları depolamak için aynı dizeler kullanmanıza olanak sağlar:

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

İki yolu birleştirmek için aşırı yüklenmiş kullanabileceğiniz `/` ve `/=` alınmak üzere işleçleri `+` ve `+=` işleçlerini `std::string` ve `std::wstring`. `path` Nesne rahatça tedarik ayırıcılar Aksi takdirde.

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>Yolları inceleme

Yol sınıfı için başvurabilir dosya sistemi varlık as distinct from yolun kendisindeki, çeşitli bölümlerini ilgili bilgi döndüren çeşitli yöntemler vardır. Kök, göreli yol, dosya adı, dosya uzantısı ve daha fazla bilgi alabilirsiniz. Hiyerarşideki tüm klasörleri incelemek için bir yol nesnesi üzerinde yinelenir. Aşağıdaki örnek, bir yol (başvurduğu dizin değil) üzerinden yineleme yapma ve bölümleri hakkında bilgi almak için nasıl gösterir.

```cpp
// filesystem_path_example.cpp
// compile by using: /EHsc
#include <string>
#include <iostream>
#include <sstream>
#include <filesystem>

using namespace std;
using namespace std::experimental::filesystem;

wstring DisplayPathInfo()
{
    // This path may or may not refer to an existing file. We are
    // examining this path string, not file system objects.
    path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt ");

    wostringstream wos;
    int i = 0;
    wos << L"Displaying path info for: " << pathToDisplay << endl;
    for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr)
    {
        wos << L"path part: " << i++ << L" = " << *itr << endl;
    }

    wos << L"root_name() = " << pathToDisplay.root_name() << endl
        << L"root_path() = " << pathToDisplay.root_path() << endl
        << L"relative_path() = " << pathToDisplay.relative_path() << endl
        << L"parent_path() = " << pathToDisplay.parent_path() << endl
        << L"filename() = " << pathToDisplay.filename() << endl
        << L"stem() = " << pathToDisplay.stem() << endl
        << L"extension() = " << pathToDisplay.extension() << endl;

    return wos.str();
}

void main(int argc, char* argv[])
{
    wcout << DisplayPathInfo() << endl;
    // wcout << ComparePaths() << endl; // see following example
    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

Kod, bu çıktıyı üretir:

```Output
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt
path part: 0 = C:
path part: 1 = \
path part: 2 = FileSystemTest
path part: 3 = SubDir3
path part: 4 = SubDirLevel2
path part: 5 = File2.txt
root_name() = C:
root_path() = C:\
relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt
parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2
filename() = File2.txt
stem() = File2
extension() = .txt
```

### <a name="comparing-paths"></a>Yolları karşılaştırma

`path` Sınıf olarak aynı Karşılaştırma işleçleri aşırı `std::string` ve `std::wstring`. İki yolu karşılaştırırken ayırıcılar normalleştirilmiş sonra bir dize karşılaştırmasının yapıyorsunuz. Sondaki eğik çizgi (veya ters eğik çizgi) yoksa eklenmez ve karşılaştırma etkiler. Aşağıdaki örnek nasıl yol değerlerini karşılaştırmak gösterir:

```cpp
wstring ComparePaths()
{
    path p0(L"C:/Documents");                 // no trailing separator
    path p1(L"C:/Documents/");                // p0 < p1
    path p2(L"C:/Documents/2013/");           // p1 < p2
    path p3(L"C:/Documents/2013/Reports/");   // p2 < p3
    path p4(L"C:/Documents/2014/");           // p3 < p4
    path p5(L"D:/Documents/2013/Reports/");   // p4 < p5

    wostringstream wos;
    wos << boolalpha <<
        p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl <<
        p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl <<
        p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl <<
        p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl <<
        p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl;
    return wos.str();
}
```

```Output
C:\Documents < C:\Documents\: true
C:\Documents\ < C:\Documents\2013\: true
C:\Documents\2013\ < C:\Documents\2013\Reports\: true
C:\Documents\2013\Reports\ < C:\Documents\2014\: true
C:\Documents\2014\ < D:\Documents\2013\Reports\: true
```

Bu kodu çalıştırmak için önce yukarıdaki tam örnek yapıştırın `main` ve çağrı yaptığı ana satırı açıklamadan çıkarın.

### <a name="converting-between-path-and-string-types"></a>Yol ve dize türleri arasında dönüştürme

A `path` nesnedir örtük olarak dönüştürülebilir `std::wstring` veya `std::string`. Yani, geçirebilirsiniz yol işlevler gibi [wofstream::open](../standard-library/basic-ofstream-class.md#open), bu örnekte gösterildiği gibi:

```cpp
// filesystem_path_conversion.cpp
// compile by using: /EHsc
#include <string>
#include <iostream>
#include <fstream>
#include <filesystem>

using namespace std;
using namespace std::experimental::filesystem;

void main(int argc, char* argv[])
{
    wchar_t* p = L"C:/Users/Public/Documents";
    path filePath(p);

    filePath /= L"NewFile.txt";

    // Open, write to, and close the file.
    wofstream writeFile(filePath, ios::out);  // implicit conversion
    writeFile << L"Lorem ipsum\nDolor sit amet";
    writeFile.close();

    // Open, read, and close the file.
    wifstream readFile;
    wstring line;
    readFile.open(filePath);  // implicit conversions
    wcout << L"File " << filePath << L" contains:" << endl;
    while (readFile.good())
    {
        getline(readFile, line);
        wcout << line << endl;
    }
    readFile.close();

    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

```Output
File C:\Users\Public\Documents\NewFile.txt contains:
Lorem ipsum
Dolor sit amet

Press Enter to exit
```

## <a name="iterating-directories-and-files"></a>Yineleme dizinler ve dosyalar

\<Filesystem > Üstbilgi sağlar [directory_iterator](../standard-library/directory-iterator-class.md) tek dizinleri yineleme türü ve [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) yinelemeli olarak gezinilen sınıfı bir Dizin ve alt dizinleri. Bir yineleyicinin çağırıp oluşturduktan sonra bir `path` nesne, yineleyici yolunda ilk directory_entry işaret eder. Varsayılan Oluşturucu çağırarak end yineleyici oluşturun.

Bir dizin yineleme olduğunda çeşitli türlerde öğeler, ancak bunlarla sınırlı olmamak dizinleri, dosyaları, simgesel bağlantılar ve yuva dosyaları dahil olmak üzere, karşılaşabilirsiniz. `directory_iterator` Alt öğeleri olarak döndürür [directory_entry](../standard-library/directory-entry-class.md) nesneleri.
