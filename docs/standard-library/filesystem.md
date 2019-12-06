---
title: '&lt;dosya sistemi&gt;'
ms.date: 11/04/2016
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
ms.openlocfilehash: 0f2c90bd7c1d88a94d1dab05b98442111faa71a2
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898809"
---
# <a name="ltfilesystemgt"></a>&lt;dosya sistemi&gt;

Yollar, dosyalar ve dizinler hakkında bilgi işleyen ve alan sınıflar ve işlevlere erişim için &lt;dosya sistemi > üst bilgisini dahil edin.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <experimental/filesystem> // C++-standard header file name
#include <filesystem> // Microsoft-specific implementation header file name
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 sürümünden itibaren, \<dosya sistemi > üst bilgisi henüz bir C++ standart değildi. C++Visual Studio 2017 ' de (MSVC v141), [ISO/ıEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)içinde bulunan son taslak standardını uygular.

Bu üst bilgi, ana bilgisayar işletim sistemi sınıflarından biri için dosya sistemlerini destekler: Microsoft Windows ve POSIX.

Çoğu işlevsellik her iki işletim sisteminde de yaygın olsa da, bu belge farkların nerede olduğunu tanımlar. Örneğin:

- Windows, c: veya \\\ network_name gibi birden çok kök adı destekler. Bir dosya sistemi, her biri kendi kök dizinine (örneğin, c:\) sahip bir ağaç ormanından oluşur. ya da bir göreli yol adını (mutlak yol adı olmayan) tamamlamak için, her biri kendi geçerli diziniyle birlikte \\\ network_name\\.

- POSIX, kök adı, tek köklü dizin/ve tek bir geçerli dizin içermeyen tek bir ağacı destekler.

Diğer önemli fark, pathnames 'in yerel gösterimidir:

- Windows, UTF-16 (her karakter için bir veya iki öğe) olarak kodlanmış wchar_t, null ile sonlandırılmış bir sıra kullanır.

- POSIX UTF-8 (her karakter için bir veya daha fazla öğe) olarak kodlanmış, boş sonlandırılmış bir karakter dizisi kullanır.

- Bir sınıf yolu nesnesi, yol adını yerel biçimde depolar, ancak bu depolanmış form ve çeşitli harici formlar arasında kolay dönüştürmeyi destekler:

- İşletim sistemi tarafından sık kullanılanları olarak kodlanan, null sonlandırılmış bir karakter dizisi.

- UTF-8 olarak kodlanmış, null ile sonlandırılan bir karakter dizisi.

- İşletim sistemi tarafından sık kullanılanları olarak kodlanan, wchar_t null sonlandırılmış bir dizi.

- UTF-16 olarak kodlanan, null ile sonlandırılmış char16_t sırası.

- UTF-32 olarak kodlanan char32_t, null ile sonlandırılmış bir dizi.

Bu temsiller arasındaki karşılıklı dönüştürmeler, gerektiğinde bir veya daha fazla `codecvt` modellerinin kullanılması halinde ortalandırılır. Belirli bir yerel ayar nesnesi atanmamışsa, bu modeller genel yerel ayardan alınır.

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

Son olarak, yol nesnelerinin önemli bir özelliği, \<fstream > üst bilgisinde tanımlanan sınıflarda bir dosya adı bağımsız değişkeninin gerekli olduğu her yerde kullanılabilir.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[directory_entry Sınıfı](../standard-library/directory-entry-class.md)|Bir `directory_iterator` veya `recursive_directory_iterator` tarafından döndürülen ve bir yol içeren bir nesneyi tanımlar.|
|[directory_iterator Sınıfı](../standard-library/directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar.|
|[filesystem_error Sınıfı](../standard-library/filesystem-error-class.md)|Düşük düzey sistem taşmasını raporlamak için oluşturulan özel durumlar için temel sınıf.|
|[path Sınıfı](../standard-library/path-class.md)|Bir dosya adı olarak kullanılmak üzere uygun `String` şablon türünde bir nesne depolayan bir sınıf tanımlar.|
|[recursive_directory_iterator Sınıfı](../standard-library/recursive-directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar. Yineleyici, alt dizinlere da göz alabilir.|
|[file_status Sınıfı](../standard-library/file-status-class.md)|Bir `file_type`kaydırır.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[space_info Yapısı](../standard-library/space-info-structure.md)|Bir birimle ilgili bilgileri tutar.|

## <a name="functions"></a>İşlevler

[\<dosya sistemi > işlevleri](../standard-library/filesystem-functions.md)

## <a name="operators"></a>İşleçler

[\<dosya sistemi > işleçleri](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>Listelemeler

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
