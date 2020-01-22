---
title: Dosya Sistemi Gezintisi
ms.date: 11/04/2016
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: ea9bf44a11087180d3bd02c5dcd5d1acfa4b9e57
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518510"
---
# <a name="file-system-navigation"></a>Dosya Sistemi Gezintisi

\<FileSystem > üstbilgisi, C++ dosya sistemi teknık belirtimi ISO/ıec TS 18822:2015 (son taslak: [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)) öğesini uygular ve dosya sistemine gezinmek için platforma bağımsız kod yazmanıza olanak tanıyan tür ve işlevlere sahiptir. Platformlar arası olduğundan, Windows sistemlerine uygun olmayan API 'Leri içerir. Örneğin bu, `is_fifo(const path&)` her zaman Windows üzerinde **false** olarak döndürdüğü anlamına gelir.

## <a name="overview"></a>Genel bakış

Aşağıdaki görevler için \<FileSystem > API 'Leri kullanın:

- Belirtilen bir yol altındaki dosya ve dizinleri yineleme

- oluşturulan saat, boyut, uzantı ve kök dizin gibi dosyalar hakkında bilgi alın

- yolları oluşturma, kaldırma ve karşılaştırma

- Dizin oluşturma, kopyalama ve silme

- dosyaları kopyala ve Sil

Standart kitaplığı kullanarak dosya GÇ hakkında daha fazla bilgi için bkz. [ıostream programlama](../standard-library/iostream-programming.md).

## <a name="paths"></a>Yollar

### <a name="constructing-and-composing-paths"></a>Yolları oluşturma ve oluşturma

Windows 'daki (XP 'den beri) yollar yerel olarak Unicode 'da depolanır. [Path](../standard-library/path-class.md) sınıfı tüm gerekli dize dönüştürmelerini otomatik olarak gerçekleştirir. Hem geniş hem de dar karakter dizilerinin bağımsız değişkenlerini, hem `std::string` hem de UTF8 veya UTF16 olarak biçimlendirilmiş `std::wstring` türlerini kabul eder. `path` sınıfı ayrıca yol ayırıcıları otomatik olarak normalleştirir. Oluşturucu bağımsız değişkenlerinde dizin ayırıcı olarak tek eğik çizgi kullanabilirsiniz. Bu, yolları hem Windows hem de UNIX ortamlarında depolamak için aynı dizeleri kullanmanıza olanak sağlar:

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

İki yolu birleştirmek için, `std::string` ve `std::wstring``+` ve `+=` işleçlerine benzer olan aşırı yüklenmiş `/` ve `/=` işleçlerini kullanabilirsiniz. `path` nesnesi, aksi takdirde ayırıcıları kolayca sağlar.

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>Yolları İnceleme

Yol sınıfında, başvurabileceği dosya sistemi varlığından ayrı olarak yolun kendisi hakkında bilgi döndüren çeşitli yöntemler vardır. Kökünü, göreli yolu, dosya adını, dosya uzantısını ve daha fazlasını alabilirsiniz. Hiyerarşideki tüm klasörleri incelemek için bir yol nesnesi üzerinde yineleme yapabilirsiniz. Aşağıdaki örnek, bir yol üzerinde (başvurduğu dizin değil) nasıl yineleş, ve bölümleri hakkında bilgi almanızı gösterir.

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

int main(int argc, char* argv[])
{
    wcout << DisplayPathInfo() << endl;
    // wcout << ComparePaths() << endl; // see following example
    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

Kod bu çıktıyı oluşturur:

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

`path` sınıfı, `std::string` ve `std::wstring`aynı karşılaştırma işleçlerini aşırı yükler. İki yolu karşılaştırdığınızda, ayırıcılar normalleştirildikten sonra bir dize karşılaştırması gerçekleştirmekten olursunuz. Sondaki eğik çizgi (veya ters eğik çizgi) eksikse, eklenmez ve karşılaştırmayı etkiler. Aşağıdaki örnek, yol değerlerinin nasıl karşılaştırılacağını göstermektedir:

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

Bu kodu çalıştırmak için `main` önce yukarıdaki tam örneğe yapıştırın ve Main içinde onu çağıran satırın açıklamasını kaldırın.

### <a name="converting-between-path-and-string-types"></a>Yol ve dize türleri arasında dönüştürme

`path` nesne `std::wstring` veya `std::string`örtük olarak dönüştürülebilir. Bu, aşağıdaki örnekte gösterildiği gibi, [wofstream:: Open](../standard-library/basic-ofstream-class.md#open)gibi işlevlere bir yol geçirebilmeniz anlamına gelir:

```cpp
// filesystem_path_conversion.cpp
// compile by using: /EHsc
#include <string>
#include <iostream>
#include <fstream>
#include <filesystem>

using namespace std;
using namespace std::experimental::filesystem;

int main(int argc, char* argv[])
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

## <a name="iterating-directories-and-files"></a>Dizinleri ve dosyaları yineleme

\<dosya sistemi > üst bilgisi, tek dizinleri yinelemek için [Directory_iterator](../standard-library/directory-iterator-class.md) türünü ve bir dizin ve alt dizinleri üzerinde yinelemeli olarak yinelemek için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) sınıfını sağlar. Bir `path` nesnesi geçirerek Yineleyici oluşturduktan sonra, yineleyici yoldaki ilk directory_entry işaret eder. Varsayılan oluşturucuyu çağırarak son yineleyiciyi oluşturun.

Bir dizin üzerinden yineleme yaparken dizinler, dosyalar, Simgesel bağlantılar ve yuva dosyalarıyla sınırlı olmamak üzere, karşılaşabileceğiniz birçok öğe türü vardır. `directory_iterator` öğelerini [directory_entry](../standard-library/directory-entry-class.md) nesneleri olarak döndürür.
