---
title: Dosya Sistemi Gezintisi
description: Dosya sisteminde gezinmek için C++ Standart kitaplık dosya sistemi API'leri nasıl kullanılır?
ms.date: 04/13/2020
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: 412d865582a14da7b8c31d9f07a43106b0c49491
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368437"
---
# <a name="file-system-navigation"></a>Dosya Sistemi Gezintisi

Dosya \<sistemi> başlık, C++ Dosya Sistemi Teknik Şartnamesi ISO/IEC TS 18822:2015 (Son taslak: [ISO/IEC JTC 1/SC 22/WG 21 N4100)](https://wg21.link/n4100)uygular ve dosya sisteminde gezinmek için platformdan bağımsız kod yazmanızı sağlayan tür ve işlevlere sahiptir. Çapraz platform olduğundan, Windows sistemleri yle alakalı olmayan API'ler içerir. Örneğin, `is_fifo(const path&)` Windows'da her zaman **yanlış** döndürür.

## <a name="overview"></a>Genel Bakış

Aşağıdaki \<görevler için dosya sistemini> API'leri kullanın:

- belirli bir yol altında dosyalar ve dizinler üzerinde yineleyin

- oluşturulan zaman, boyut, uzantı ve kök dizini de dahil olmak üzere dosyalar hakkında bilgi almak

- yolları oluşturmak, ayrıştırmak ve karşılaştırmak

- dizinoluşturma, kopyalama ve silme

- dosyaları kopyalama ve silme

Standart Kitaplığı kullanarak Dosya IO hakkında daha fazla bilgi için [iostream Programming'e](../standard-library/iostream-programming.md)bakın.

## <a name="paths"></a>Yollar

### <a name="constructing-and-composing-paths"></a>Yollar oluşturma ve oluşturma

Windows'daki yollar (XP'den beri) yerel olarak Unicode'da depolanır. [Yol](../standard-library/path-class.md) sınıfı gerekli tüm dize dönüşümlerini otomatik olarak yapar. Hem geniş hem de dar karakter dizilerinin `std::string` bağımsız `std::wstring` değişkenlerini ve UTF8 veya UTF16 olarak biçimlendirilmiş her iki ve türü de kabul eder. Sınıf `path` ayrıca yol ayırıcılarını otomatik olarak normalleştirir. Tek bir ileri eğik çizgi yi oluşturucu bağımsız değişkenlerinde dizin ayırıcısı olarak kullanabilirsiniz. Bu ayırıcı, yolları hem Windows hem de UNIX ortamlarında depolamak için aynı dizeleri kullanmanıza olanak tanır:

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

İki yolu birbirine ayırmak için, aşırı `/` yüklü `/=` ve işleçleri kullanabilirsiniz, `std::string` bu `std::wstring`da işleçlere `+` `+=` benzer ve . Eğer `path` yapmazsan nesne ayırıcıları rahatlıkla tedarik edecektir.

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>Yolların incelenmesi

Yol sınıfı, yolun çeşitli bölümleri hakkında bilgi döndüren çeşitli yöntemlere sahiptir. Bu bilgiler, başvurabileceği dosya sistemi varlığı hakkındaki bilgilerden farklıdır. Kök, göreli yol, dosya adı, dosya uzantısı ve daha fazlasını alabilirsiniz. Hiyerarşideki tüm klasörleri incelemek için bir yol nesnesi üzerinde yineleyebilirsiniz. Aşağıdaki örnek, bir yol nesnesi üzerinde nasıl yinelenebildiğini gösterir. Ve, parçaları hakkında bilgi almak için nasıl.

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

Kod bu çıktıyı üretir:

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

Sınıf `path` aynı karşılaştırma işleçleri `std::string` `std::wstring`overloads ve . İki yolu karşılaştırdığınızda, ayırıcılar normalleştirildikten sonra bir dize karşılaştırması yaparsınız. Sondaki eğik çizgi (veya ters eğik çizgi) eksikse, eklenmez ve bu karşılaştırmayı etkiler. Aşağıdaki örnek, yol değerlerinin nasıl karşılaştırışolduğunu gösterir:

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

Bu kodu çalıştırmak için, yukarıdaki `main` tam örneğe yapıştırın ve ana çağrıda bulunan satırı açıklamayapmayı bırakın.

### <a name="converting-between-path-and-string-types"></a>Yol ve dize türleri arasında dönüştürme

Bir `path` nesne dolaylı olarak `std::wstring` dönüştürülebilir veya `std::string`. Bu, bu örnekte gösterildiği gibi [wofstream::open](../standard-library/basic-ofstream-class.md#open), gibi işlevlere bir yol geçebileceğiniz anlamına gelir:

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

## <a name="iterating-directories-and-files"></a>Dizinleri ve dosyaları yinele

Dosya \<sistemi> üstbilgi, tek dizinler üzerinde yinelemek için [directory_iterator](../standard-library/directory-iterator-class.md) türünü ve [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) sınıfının bir dizin ve alt dizinleri üzerinde yinelemesini sağlar. Bir `path` nesneyi geçirerek bir yineleyici inşa ettikten sonra, yineleyici yoldaki ilk directory_entry işaret edin. Varsayılan oluşturucuyu çağırarak son yineleyiciyi oluşturun.

Bir dizin aracılığıyla yinelenirken, keşfedebileceğin çeşitli öğeler vardır. Bu öğeler dizinler, dosyalar, sembolik bağlantılar, soket dosyaları ve diğerleri içerir. Öğeleri `directory_iterator` [ni directory_entry](../standard-library/directory-entry-class.md) nesne olarak döndürür.
