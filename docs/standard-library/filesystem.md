---
title: '&lt;:::no-loc(filesystem):::&gt;'
description: 'Standart C++ kitaplığının üstbilgisindeki sınıfları, işlevleri ve türleri açıklar :::no-loc(filesystem)::: .'
ms.date: 01/22/2020
f1_keywords:
- <:::no-loc(filesystem):::>
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
no-loc:
- ':::no-loc(filesystem):::'
- ':::no-loc(experimental):::'
- ':::no-loc(char):::'
- ':::no-loc(wchar_t):::'
- ':::no-loc(char16_t):::'
- ':::no-loc(char32_t):::'
ms.openlocfilehash: 1b3f541619bde85131915a4d1586a44675c2906a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219150"
---
# &lt;:::no-loc(filesystem):::&gt;

&lt; :::no-loc(filesystem)::: Yollar, dosyalar ve dizinler hakkındaki bilgileri işleyen ve alan sınıflara ve işlevlere erişim için üst bilgi> ekleyin.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <:::no-loc(filesystem):::> // C++17 standard header file name
#include <:::no-loc(experimental):::/:::no-loc(filesystem):::> // Header file for pre-standard implementation
using namespace std:::::no-loc(experimental)::::::::no-loc(filesystem):::::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 sürümünde \<:::no-loc(filesystem):::> başlık henüz bir C++ standardı değildi. Visual Studio 2017 RTW 'de C++, [ISO/ıEC JTC 1/SC 22/WG 21 N4100](https://wg21.link/n4100)içinde bulunan son taslak standardını uygular. Visual Studio 2017 sürüm 15,7 ve üzeri yeni C++ 17 standardını destekler \<:::no-loc(filesystem):::> .
> Bu, önceki sürümle uyumlu olmayan tamamen yeni bir uygulama `std:::::no-loc(experimental):::` . Oluşturmaksızın desteği, hata düzeltmeleri ve standart-gerekli davranıştaki değişiklikler tarafından gerekli hale getirilir. Şu anda, dahil \<:::no-loc(filesystem):::> Yeni `std:::::no-loc(filesystem):::` ve önceki bir sağlar `std:::::no-loc(experimental)::::::::no-loc(filesystem):::` . Dahil olmak üzere \<:::no-loc(experimental):::/:::no-loc(filesystem):::> yalnızca eski :::no-loc(experimental)::: uygulamayı sağlar. :::no-loc(experimental):::Uygulama, kitaplıkların sonrakı ABI-kırılımı sürümünde kaldırılacak.

Bu üst bilgi, ana bilgisayar işletim sistemi sınıfının iki geniş sınıfından biri için dosya sistemlerini destekler: Microsoft Windows ve POSIX.

Çoğu işlevsellik her iki işletim sisteminde de yaygın olsa da, bu belge farkların nerede olduğunu tanımlar. Örnek:

- Windows, veya gibi birden çok kök adı `c:` destekler `\\network_name` . Bir dosya sistemi, her biri veya gibi kendi kök dizinine `c:\` `\\network_name\` ve her biri bir göreli yol adını (mutlak yol adı olmayan bir yol değil) tamamlamak için kendi geçerli dizinine sahip bir ağaç ormanından oluşur.

- POSIX, kök adı, tek kök dizin `/` ve tek bir geçerli dizin içermeyen tek bir ağacı destekler.

Diğer önemli fark, pathnames 'in yerel gösterimidir:

- Windows **`:::no-loc(wchar_t):::`** , UTF-16 (her bir bir veya daha fazla öğe için bir veya daha fazla öğe) olarak kodlanmış, null sonlandırılmış bir dizi kullanır :::no-loc(char)::: .

- POSIX **`:::no-loc(char):::`** , UTF-8 (her bir veya daha fazla öğe için bir veya daha fazla öğe) olarak kodlanmış, null sonlandırılmış bir dizi kullanır :::no-loc(char)::: .

- Sınıfının bir nesnesi `path` , yol adını yerel biçimde depolar, ancak bu depolanmış form ve çeşitli dış formlar arasında kolay dönüştürmeyi destekler:

  - **`:::no-loc(char):::`** İşletim sistemi tarafından sık kullanılanlara göre kodlanmış, null sonlandırılmış bir dizi.

  - **`:::no-loc(char):::`** UTF-8 olarak kodlanmış, null ile sonlandırılmış bir dizi.

  - **`:::no-loc(wchar_t):::`** İşletim sistemi tarafından sık kullanılanlara göre kodlanmış, null sonlandırılmış bir dizi.

  - **`:::no-loc(char16_t):::`** UTF-16 olarak kodlanmış, null sonlandırılmış bir dizi.

  - **`:::no-loc(char32_t):::`** UTF-32 olarak kodlanan, null ile sonlandırılmış bir dizi.

  Bu gösterimler arasındaki karşılıklı dönüştürmeler, gerektiğinde bir veya daha fazla model kullanılarak desteklenmez `codecvt` . Belirli bir yerel ayar nesnesi belirtilmemişse, bu modeller genel yerel ayardan alınır.

Diğer bir farkı, her işletim sisteminin dosya veya dizin erişim izinleri belirtmenize izin veren ayrıntıdır:

- Windows, bir dosyanın salt okunurdur veya yazılabilir olduğunu, dizinler için anlamı olmayan bir özniteliği kaydeder.

- POSIX, bir dosyanın okunup okunamayacağını, yazılabileceğini veya yürütülüp yürütülmeyeceğini (bir dizin ise taranan) kaydeder. Ayrıca, her bir işleme sahip için izin, sahibin grubu, veya herkes gövdesi için izin verilip verilmediği ve diğer birkaç izin olup olmadığı.

Her iki sistem için ortak, kök adı aşıldıktan sonra bir yol adı üzerine getirilen yapıdır. Yol adı için `c:/abc/xyz/def.ext` :

- Kök adı `c:` .

- Kök dizin `/` .

- Kök yolu `c:/` .

- Göreli yol `abc/xyz/def.ext` .

- Üst yol `c:/abc/xyz` .

- Dosya adı `def.ext` .

- Gövdesi `def` .

- Uzantı `.ext` .

Küçük bir fark, bir yol adındaki dizinlerin sırası arasındaki tercih edilen ayırıcıdır. Her iki işletim sistemi de eğik çizgi yazmanıza izin verir `/` , ancak bazı bağlamlarda Windows ters eğik çizgi tercih eder `\` . Uygulama, içindeki veri üyesinde tercih edilen ayırıcısını depolar `preferred_separator` `path` .

Son olarak, `path` nesneler önemli bir özelliğe sahiptir: üst bilgide tanımlanan sınıflarda bir dosya adı bağımsız değişkeninin gerekli olduğu her yerde bunları kullanabilirsiniz [\<fstream>](fstream.md) .

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[directory_entry sınıfı](../standard-library/directory-entry-class.md)|Ya da tarafından döndürülen ve içeren bir nesneyi tanımlar `directory_iterator` `recursive_directory_iterator` `path` .|
|[directory_iterator sınıfı](../standard-library/directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar.|
|[:::no-loc(filesystem):::_error sınıfı](../standard-library/:::no-loc(filesystem):::-error-class.md)|Düşük düzey sistem taşmasını raporlamak için oluşturulan özel durumlar için temel sınıf.|
|[path sınıfı](../standard-library/path-class.md)|`String`Bir dosya adı olarak kullanılmak üzere uygun şablon türünde bir nesne depolayan bir sınıf tanımlar.|
|[recursive_directory_iterator sınıfı](../standard-library/recursive-directory-iterator-class.md)|Dosya sistemi dizinindeki dosya adlarıyla oluşan bir giriş yineleyicisini açıklar. Yineleyici, alt dizinlere da göz alabilir.|
|[file_status sınıfı](../standard-library/file-status-class.md)|Bir olarak kaydırır `file_type` .|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[space_info yapısı](../standard-library/space-info-structure.md)|Bir birimle ilgili bilgileri tutar.|

## <a name="functions"></a>İşlevler

[\<:::no-loc(filesystem):::>lerdir](../standard-library/:::no-loc(filesystem):::-functions.md)

## <a name="operators"></a>İşleçler

[\<:::no-loc(filesystem):::>işletmenlerinin](../standard-library/:::no-loc(filesystem):::-operators.md)

## <a name="enumerations"></a>Listelemeler

|||
|-|-|
|[copy_options](../standard-library/:::no-loc(filesystem):::-enumerations.md#copy_options)|[Copy_file](../standard-library/:::no-loc(filesystem):::-functions.md#copy_file) ile kullanılan ve bir hedef dosya zaten varsa davranışı belirleyen bir sabit listesi.|
|[directory_options](../standard-library/:::no-loc(filesystem):::-enumerations.md#directory_options)|Dizin yineleyiciler için seçenekleri belirten bir sabit listesi.|
|[file_type](../standard-library/:::no-loc(filesystem):::-enumerations.md#file_type)|Dosya türleri için bir sabit listesi.|
|[perm_options](../standard-library/:::no-loc(filesystem):::-enumerations.md#perm_options)| İşlevin seçeneklerini numaralandırır `permissions` . |
|[izinleri](../standard-library/:::no-loc(filesystem):::-enumerations.md#perms)|İzinlere ve seçeneklere izinleri iletmek için kullanılan bir bit maskesi türü|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
