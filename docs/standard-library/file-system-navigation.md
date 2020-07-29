---
title: Dosya Sistemi Gezintisi
description: Dosya sisteminde gezinmek için C++ standart kitaplık dosya API 'Lerini kullanma.
ms.date: 04/13/2020
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: 26abe2fad6cacf8959507f15e967278e85254024
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203293"
---
# <a name="file-system-navigation"></a>Dosya Sistemi Gezintisi

\<filesystem>Üst bilgi, C++ dosya sistemi teknik BELIRTIMI ISO/ıEC TS 18822:2015 (son taslak: [ISO/ıEC JTC 1/SC 22/WG 21 N4100](https://wg21.link/n4100)) uygular ve dosya sistemine gezinmek için platformdan bağımsız kod yazmanıza olanak tanıyan tür ve işlevlere sahiptir. Platformlar arası olduğundan, Windows sistemleri için uygun olmayan API 'Leri içerir. Örneğin, `is_fifo(const path&)` her zaman **`false`** Windows 'u döndürür.

## <a name="overview"></a>Genel Bakış

\<filesystem>Aşağıdaki görevler için API 'leri kullanın:

- Belirtilen bir yol altındaki dosya ve dizinleri yineleme

- oluşturulan saat, boyut, uzantı ve kök dizin gibi dosyalar hakkında bilgi alın

- yolları oluşturma, kaldırma ve karşılaştırma

- Dizin oluşturma, kopyalama ve silme

- dosyaları kopyala ve Sil

Standart kitaplığı kullanarak dosya GÇ hakkında daha fazla bilgi için bkz. [ıostream programlama](../standard-library/iostream-programming.md).

## <a name="paths"></a>Yollar

### <a name="constructing-and-composing-paths"></a>Yolları oluşturma ve oluşturma

Windows 'daki (XP 'den beri) yollar yerel olarak Unicode 'da depolanır. [Path](../standard-library/path-class.md) sınıfı tüm gerekli dize dönüştürmelerini otomatik olarak yapar. Hem geniş hem de dar karakter dizilerinin bağımsız değişkenlerini, hem hem de `std::string` `std::wstring` UTF8 veya UTF16 olarak biçimlendirilen türleri kabul eder. `path`Sınıf Ayrıca yol ayırıcılarını otomatik olarak normalleştirir. Oluşturucu bağımsız değişkenlerinde dizin ayırıcı olarak tek eğik çizgi kullanabilirsiniz. Bu ayırıcı, yolları hem Windows hem de UNIX ortamlarında depolamak için aynı dizeleri kullanmanıza olanak sağlar:

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

İki yolu birleştirmek için, `/` `/=` `+` `+=` ve üzerindeki ve işleçlerine benzeyen aşırı yüklenmiş ve işleçleri kullanabilirsiniz `std::string` `std::wstring` . `path`Aksi takdirde nesne, ayırıcıları kolayca sağlar.

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>Yolları İnceleme

Yol sınıfında yolun kendisi hakkında bilgi döndüren çeşitli yöntemler vardır. Bu bilgiler, başvurabileceği dosya sistemi varlığı hakkındaki bilgilerden farklıdır. Kökünü, göreli yolu, dosya adını, dosya uzantısını ve daha fazlasını alabilirsiniz. Hiyerarşideki tüm klasörleri incelemek için bir yol nesnesi üzerinde yineleme yapabilirsiniz. Aşağıdaki örnek, bir yol nesnesi üzerinde nasıl yineleme yapılacağını gösterir. Ve bölümleri hakkında bilgi alma.

```cpp
// filesystem_path_example.cpp
// compile by using: /EHsc /W4 /permissive- /std:c++17 (or /std:c++latest)
#include <string>
#include <iostream>
#include <sstream>
#include <filesystem>

using namespace std;
using namespace std::filesystem;

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

int main()
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

`path`Sınıfı, ve ile aynı karşılaştırma işleçlerini aşırı `std::string` yükler `std::wstring` . İki yolu karşılaştırdığınızda, ayırıcılar normalleştirildikten sonra bir dize karşılaştırması yaparsınız. Sondaki eğik çizgi (veya ters eğik çizgi) eksikse, eklenmez ve bu karşılaştırmayı etkiler. Aşağıdaki örnek, yol değerlerinin nasıl karşılaştırılacağını göstermektedir:

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

Bu kodu çalıştırmak için, önce yukarıdaki tam örneğe yapıştırın `main` ve Main içinde onu çağıran satırın açıklamasını kaldırın.

### <a name="converting-between-path-and-string-types"></a>Yol ve dize türleri arasında dönüştürme

Bir `path` nesne, veya öğesine örtük olarak dönüştürülebilir `std::wstring` `std::string` . Bu örnekte gösterildiği gibi, [wofstream:: Open](../standard-library/basic-ofstream-class.md#open)gibi işlevlere bir yol geçirebilmeniz anlamına gelir:

```cpp
// filesystem_path_conversion.cpp
// compile by using: /EHsc /W4 /permissive- /std:c++17 (or /std:c++latest)
#include <string>
#include <iostream>
#include <fstream>
#include <filesystem>

using namespace std;
using namespace std::filesystem;

int main()
{
    const wchar_t* p{ L"C:/Users/Public/Documents" };
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

\<filesystem>Üst bilgi, tek dizinleri yinelemek için [Directory_iterator](../standard-library/directory-iterator-class.md) türünü ve bir dizin ve alt dizinleri üzerinde yinelemeli olarak yinelemek için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) sınıfını sağlar. Bir yineleyiciyi bir nesne geçirerek oluşturduktan sonra `path` Yineleyici, yoldaki ilk directory_entry gösterir. Varsayılan oluşturucuyu çağırarak son yineleyiciyi oluşturun.

Bir dizin üzerinden yineleme yaparken, keşfedeolabileceğiniz birkaç öğe türü vardır. Bu öğeler arasında dizinler, dosyalar, sembolik bağlantılar, soket dosyaları ve diğerleri bulunur. , `directory_iterator` Öğelerini [directory_entry](../standard-library/directory-entry-class.md) nesne olarak döndürür.
