---
title: '&lt;Biçimlendiri&gt;'
ms.date: 11/04/2016
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
ms.openlocfilehash: 6f97ad75dcf3f01406f305b713b9d14cbe527c52
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457018"
---
# <a name="ltfilesystemgt"></a>&lt;Biçimlendiri&gt;

Yollar, dosyalar &lt;ve dizinler hakkındaki bilgileri işleyen ve alan sınıflara ve işlevlere erişim için üstbilgi dosya sistemi > ekleyin.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <experimental/filesystem> // C++-standard header file name
#include <filesystem> // Microsoft-specific implementation header file name
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 \<sürümünden itibaren FileSystem > üst bilgisi henüz bir C++ standart değildi. C++Visual Studio 2017 ' de (MSVC v141), [ISO/ıEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)içinde bulunan son taslak standardını uygular.

Bu üst bilgi, konak işletim sistemlerinden oluşan iki geniş sınıftan biri için dosya sistemlerini destekler: Microsoft Windows ve POSIX.

Çoğu işlevsellik her iki işletim sisteminde de yaygın olsa da, bu belge farkların nerede olduğunu tanımlar. Örneğin:

- Windows, c: veya \\\network_adı gibi birden çok kök adı destekler. Bir dosya sistemi, her biri kendi kök dizinine (örneğin, c:\) sahip bir ağaç ormanından oluşur. ya \\da \network_adı\\ve bir göreli yol adını (mutlak yol adı olmayan bir değer) tamamlamak için kendi geçerli diziniyle birlikte.

- POSIX, kök adı, tek köklü dizin/ve tek bir geçerli dizin içermeyen tek bir ağacı destekler.

Diğer önemli fark, pathnames 'in yerel gösterimidir:

- Windows, UTF-16 olarak kodlanmış (her karakter için bir veya iki öğe), null olarak sonlandırılmış bir wchar_t sırası kullanır.

- Posix UTF-8 (her karakter için bir veya daha fazla öğe) olarak kodlanmış, boş sonlandırılmış bir karakter dizisi kullanır.

- Bir sınıf yolu nesnesi, yol adını yerel biçimde depolar, ancak bu depolanmış form ve çeşitli harici formlar arasında kolay dönüştürmeyi destekler:

- İşletim sistemi tarafından sık kullanılanları olarak kodlanan, null sonlandırılmış bir karakter dizisi.

- UTF-8 olarak kodlanmış, null ile sonlandırılan bir karakter dizisi.

- İşletim sistemi tarafından sık kullanılanlara olarak kodlanan, null ile sonlandırılan bir wchar_t sırası.

- UTF-16 olarak kodlanmış, null ile sonlandırılan bir char16_t dizisi.

- UTF-32 olarak kodlanan, null ile sonlandırılan bir char32_t dizisi.

Bu gösterimler arasındaki karşılıklı dönüştürmeler, gerektiğinde bir veya daha fazla `codecvt` model kullanılarak desteklenmez. Belirli bir yerel ayar nesnesi atanmamışsa, bu modeller genel yerel ayardan alınır.

Diğer bir farkı, her işletim sisteminin dosya veya dizin erişim izinleri belirtmenize izin veren ayrıntıdır:

1. Windows, bir dosyanın salt okunurdur veya yazılabilir olduğunu, dizinler için anlamı olmayan bir özniteliği kaydeder.

1. POSIX, bir dosyanın okunabilir, yazılabilir veya çalıştırılabilir (bir dizin ise taranan), sahibe göre, sahibine ait Grup veya herkes tarafından, diğer birkaç izin olup olmadığını kaydeder.

Her iki sistem için ortak, kök adı aşıldıktan sonra bir yol adı üzerine getirilen yapıdır. C:/abc/xyz/def. ext yol adı için:

- Kök adı c 'dir

- Kök dizin/olur.

- Kök yolu c:/olur.

- Göreli yol abc/xyz/def. ext ' dır.

- Üst yol c:/abc/xyz ' dir.

- Dosya adı def. ext olur.

- Gövde def ' dir.

- Uzantı. ext.

Bir yol adındaki dizinlerin sırası arasındaki küçük bir fark, **tercih edilen ayırıcıdır**. Her iki işletim sistemi de eğik çizgi yazmanıza izin verir, ancak bazı bağlamlarda Windows ters eğik çizgi \\tercih eder.

Son olarak, yol nesnelerinin önemli bir özelliği, üst bilgi \<fstream > tanımlanmış sınıflarda bir dosya adı bağımsız değişkeninin gerekli olduğu her durumda bunları kullanmanıza yardımcı olur.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[directory_entry Sınıfı](../standard-library/directory-entry-class.md)|`directory_iterator` Bir`recursive_directory_iterator` veya tarafından döndürülen ve bir yol içeren bir nesnesi tanımlar.|
|[directory_iterator Sınıfı](../standard-library/directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar.|
|[filesystem_error Sınıfı](../standard-library/filesystem-error-class.md)|Düşük düzey sistem taşmasını raporlamak için oluşturulan özel durumlar için temel sınıf.|
|[path Sınıfı](../standard-library/path-class.md)|Bir dosya adı olarak kullanılmak üzere uygun şablon türünde `String` bir nesne depolayan bir sınıf tanımlar.|
|[recursive_directory_iterator Sınıfı](../standard-library/recursive-directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar. Yineleyici, alt dizinlere da göz alabilir.|
|[file_status Sınıfı](../standard-library/file-status-class.md)|Bir `file_type`olarak kaydırır.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[space_info Yapısı](../standard-library/space-info-structure.md)|Bir birimle ilgili bilgileri tutar.|

## <a name="functions"></a>İşlevler

[\<FileSystem > işlevleri](../standard-library/filesystem-functions.md)

## <a name="operators"></a>İşleçler

[\<dosya sistemi > işleçleri](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[Copy_file](../standard-library/filesystem-functions.md#copy_file) ile kullanılan ve bir hedef dosya zaten varsa davranışı belirleyen bir sabit listesi.|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[Copy_file](../standard-library/filesystem-functions.md#copy_file) ile kullanılan ve bir hedef dosya zaten varsa davranışı belirleyen bir sabit listesi.|
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|Dizin yineleyiciler için seçenekleri belirten bir sabit listesi.|
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|Dosya türleri için bir sabit listesi.|
|[perm_options](../standard-library/filesystem-enumerations.md#perm_options)||
|[izinleri](../standard-library/filesystem-enumerations.md#perms)|İzinlere ve seçeneklere izinleri iletmek için kullanılan bir bit maskesi türü|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
