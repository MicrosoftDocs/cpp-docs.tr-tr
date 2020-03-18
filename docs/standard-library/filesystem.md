---
title: '&lt;filesystem&gt;'
description: Standart C++ kitaplığın filesystem üstbilgisindeki sınıfları, işlevleri ve türleri açıklar.
ms.date: 01/22/2020
f1_keywords:
- <filesystem>
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
no-loc:
- filesystem
- experimental
- char
- wchar_t
- char16_t
- char32_t
ms.openlocfilehash: f9e384953a4e675ad6235a274c447031976a1585
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441716"
---
# &lt;filesystem&gt;

Yollar, dosyalar ve dizinler hakkında bilgi işleyen ve alan sınıflara ve işlevlere erişim için &lt;filesystem> üst bilgisini ekleyin.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <filesystem> // C++17 standard header file name
#include <experimental/filesystem> // Header file for pre-standard implementation
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 ' un sürümünde, \<filesystem> üst bilgisi henüz C++ standart değildi. C++Visual Studio 2017 RTW ' de, [ISO/ıEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)içinde bulunan son taslak standardını uygular. Visual Studio 2017 sürüm 15,7 ve üzeri, yeni C++ 17 \<filesystem> standardını destekler.
> Bu, önceki `std::experimental` sürümüyle uyumlu olmayan tamamen yeni bir uygulama. Oluşturmaksızın desteği, hata düzeltmeleri ve standart-gerekli davranıştaki değişiklikler tarafından gerekli hale getirilir. Şu anda \<filesystem> dahil, yeni `std::filesystem` ve önceki `std::experimental::filesystem`sağlar. \<experimental/filesystem> dahil olmak üzere yalnızca eski experimental uygulamasını sağlar. experimental uygulama, kitaplıkların sonraki ABı-kırılımı sürümünde kaldırılacak.

Bu üst bilgi, ana bilgisayar işletim sistemi sınıfının iki geniş sınıfından biri için dosya sistemlerini destekler: Microsoft Windows ve POSIX.

Çoğu işlevsellik her iki işletim sisteminde de yaygın olsa da, bu belge farkların nerede olduğunu tanımlar. Örnek:

- Windows, `c:` veya `\\network_name`gibi birden çok kök adı destekler. Bir dosya sistemi, her biri kendi kök dizinine sahip `c:\` veya `\\network_name\`ve her biri bir göreli yol adını (mutlak yol adı olmayan bir yol değil) tamamlamak için kendi geçerli dizinine sahip bir ağaç ormanından oluşur.

- POSIX, kök adı, tek kök dizin `/`ve tek bir geçerli dizin olmadan tek bir ağacı destekler.

Diğer önemli fark, pathnames 'in yerel gösterimidir:

- Windows, UTF-16 (her karakter için bir veya daha fazla öğe) olarak kodlanmış **wchar_t** , null ile sonlandırılmış bir sıra kullanır.

- POSIX, UTF-8 (her karakter için bir veya daha fazla öğe) olarak kodlanmış **char** null sonlandırılmış bir sıra kullanır.

- `path` sınıfının bir nesnesi, yol adını yerel biçimde depolar, ancak bu depolanmış form ve çeşitli harici formlar arasında kolay dönüştürmeyi destekler:

  - İşletim sistemi tarafından sık kullanılanları olarak kodlanan, **char** null sonlandırılmış bir dizi.

  - UTF-8 olarak kodlanmış **char** , null ile sonlandırılmış bir dizi.

  - İşletim sistemi tarafından sık kullanılanları olarak kodlanan, **wchar_t** null sonlandırılmış bir dizi.

  - UTF-16 olarak kodlanan, null ile sonlandırılmış **char16_t** sırası.

  - UTF-32 olarak kodlanan **char32_t** , null ile sonlandırılmış bir dizi.

  Bu temsiller arasındaki karşılıklı dönüştürmeler, gerektiğinde bir veya daha fazla `codecvt` modellerinin kullanılması halinde ortalandırılır. Belirli bir yerel ayar nesnesi belirtilmemişse, bu modeller genel yerel ayardan alınır.

Diğer bir farkı, her işletim sisteminin dosya veya dizin erişim izinleri belirtmenize izin veren ayrıntıdır:

- Windows, bir dosyanın salt okunurdur veya yazılabilir olduğunu, dizinler için anlamı olmayan bir özniteliği kaydeder.

- POSIX, bir dosyanın okunup okunamayacağını, yazılabileceğini veya yürütülüp yürütülmeyeceğini (bir dizin ise taranan) kaydeder. Ayrıca, her bir işleme sahip için izin, sahibin grubu, veya herkes gövdesi için izin verilip verilmediği ve diğer birkaç izin olup olmadığı.

Her iki sistem için ortak, kök adı aşıldıktan sonra bir yol adı üzerine getirilen yapıdır. Yol adı için `c:/abc/xyz/def.ext`:

- Kök adı `c:`.

- Kök dizin `/`.

- Kök yolu `c:/`.

- Göreli yol `abc/xyz/def.ext`.

- Üst yol `c:/abc/xyz`.

- Dosya adı `def.ext`.

- Gövde `def`.

- Uzantı `.ext`.

Küçük bir fark, bir yol adındaki dizinlerin sırası arasındaki tercih edilen ayırıcıdır. Her iki işletim sistemi de eğik çizgi `/`yazmanızı sağlar, ancak bazı bağlamlarda Windows ters eğik çizgi `\`tercih eder. Uygulama, `path`içindeki veri üyesinde `preferred_separator` tercih edilen ayırıcısını depolar.

Son olarak, `path` nesneleri önemli bir özelliğe sahiptir: üstbilgi [\<fstream >](fstream.md)içinde tanımlanan sınıflarda bir dosya adı bağımsız değişkeninin gerekli olduğu her yerde kullanabilirsiniz.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[directory_entry sınıfı](../standard-library/directory-entry-class.md)|Bir `directory_iterator` veya `recursive_directory_iterator` tarafından döndürülen ve bir `path`içeren bir nesnesi tanımlar.|
|[directory_iterator sınıfı](../standard-library/directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar.|
|[filesystem_error sınıfı](../standard-library/filesystem-error-class.md)|Düşük düzey sistem taşmasını raporlamak için oluşturulan özel durumlar için temel sınıf.|
|[yol sınıfı](../standard-library/path-class.md)|Bir dosya adı olarak kullanılmak üzere uygun `String` şablon türünde bir nesne depolayan bir sınıf tanımlar.|
|[recursive_directory_iterator sınıfı](../standard-library/recursive-directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar. Yineleyici, alt dizinlere da göz alabilir.|
|[file_status sınıfı](../standard-library/file-status-class.md)|Bir `file_type`kaydırır.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[space_info yapısı](../standard-library/space-info-structure.md)|Bir birimle ilgili bilgileri tutar.|

## <a name="functions"></a>İşlevler

[\<filesystem> işlevleri](../standard-library/filesystem-functions.md)

## <a name="operators"></a>İşleçler

[\<filesystem> işleçleri](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[Copy_file](../standard-library/filesystem-functions.md#copy_file) ile kullanılan ve bir hedef dosya zaten varsa davranışı belirleyen bir sabit listesi.|
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|Dizin yineleyiciler için seçenekleri belirten bir sabit listesi.|
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|Dosya türleri için bir sabit listesi.|
|[perm_options](../standard-library/filesystem-enumerations.md#perm_options)| `permissions` işlevi için seçenekleri numaralandırır. |
|[izinleri](../standard-library/filesystem-enumerations.md#perms)|İzinlere ve seçeneklere izinleri iletmek için kullanılan bir bit maskesi türü|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
