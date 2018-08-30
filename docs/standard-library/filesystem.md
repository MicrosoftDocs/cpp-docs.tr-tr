---
title: '&lt;dosya sistemi&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
dev_langs:
- C++
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81046c8472a2a741d5e59622986326ab4b399871
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207929"
---
# <a name="ltfilesystemgt"></a>&lt;dosya sistemi&gt;

Üstbilgisini &lt;filesystem > erişim sınıfları ve işlevleri değiştirmek ve yolları, dosyalar ve dizinler hakkında bilgi almak için.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <experimental/filesystem> // C++-standard header file name
#include <filesystem> // Microsoft-specific implementation header file name
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 sürümü itibarıyla \<filesystem > Üstbilgi değildi henüz bir C++ standart. Visual C++ 2017 son taslak standardı uygular, bulunan [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf).

Dosya sistemleri, konak işletim sistemlerinin iki geniş sınıflardan biri için bu üst bilginin destekler: Microsoft Windows ve POSIX.

Çoğu işlevi her iki işletim sistemleri için yaygın olsa da, bu belgenin nereye farklar meydana tanımlar. Örneğin:

- Windows c: gibi birden çok kök adlarını destekler veya \\\network_name. Bir dosya sistemi ağaçları, c:\ gibi kendi kök dizinine sahip her bir orman oluşur veya \\\network_name\\ve her bir göreli yol (bir mutlak bir yol adı değil) tamamlamak için kendi geçerli dizin.

- POSIX destekleyen tek kök dizinini hiçbir kök adı ile tek bir ağaç / ve tek bir geçerli dizin.

Başka bir önemli fark, yol adlarını, yerel temsilidir:

- Windows, wchar_t, UTF-16 (her karakter için bir veya iki öğe) olarak kodlanmış null ile sonlandırılmış bir dizisini kullanır.

- POSIX null ile sonlandırılmış bir UTF-8 (her karakter için bir veya daha fazla öğe) olarak kodlanmış karakter dizisini kullanır.

- Sınıf yolu bir nesnenin yol yerel biçiminde depolar, ancak bu arasında kolay dönüştürme destekler formu ve birkaç dış formları depolanan:

- Null ile sonlandırılmış bir sıra char, işletim sistemi tarafından ayrıcalıklı olarak kodlanmış.

- Null ile sonlandırılmış bir sıra char, UTF-8 olarak kodlanmış.

- İşletim sistemi tarafından ayrıcalıklı olarak kodlanmış wchar_t, null ile sonlandırılmış dizisi.

- UTF-16 olarak kodlanmış char16_t, null ile sonlandırılmış dizisi.

- UTF-32 kodlanmış char32_t, null ile sonlandırılmış dizisi.

Bu temsilleri arasında interconversions cout, gerektiğinde bir veya daha fazla kullandığı `codecvt` modeller. Belirli bir yerel ayar nesnesi belirlenmemişse, bu modellerin genel yerel ayardan elde edilir.

Başka bir farktır ile her işletim sistemi, dosya veya dizin erişim izinleri belirtmenize olanak tanıyan Ayrıntısı:

1. Windows kayıt yalnızca veya yazılabilir dosya okuma olup, hiçbir anlamı dizinler için bir öznitelik.

1. POSIX dosya, (bir dizin, taranan), yazılan veya yürütülen okunup okunamayacağını sahibi, sahibin grubu veya herkesin yanı sıra bazı diğer izinler tarafından kaydeder.

Kök adı aldıktan sonra her iki sistemleri için ortak yapı üzerinde bir yol uygulanmaktadır. Pathname c:/abc/xyz/def.ext için:

- C: kök adıdır.

- Kök dizin /.

- Kök yolu şöyledir /.

- Abc/xyz/def.ext göreli yoludur.

- C:/abc/xyz üst yoludur.

- Dosya def.ext adıdır.

- Def olarak gövdesi olan

- Uzantı. dahili

Küçük bir fark var mı **tercih edilen ayırıcı**, arasında bir dizi dizinleri yol adı. Her iki işletim sistemi eğik yazmanıza olanak /, ancak bazı bağlamlarda Windows ters eğik çizgi tercih \\.

Son olarak, önemli bir özelliği, yol nesneleri üstbilgisinde tanımlanan sınıfların bir dosya adı bağımsız değişkeni gerekli olursa olsun, bunları kullanabilmenizdedir \<fstream >.

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[directory_entry Sınıfı](../standard-library/directory-entry-class.md)|Tarafından döndürülen bir nesne tanımlayan bir `directory_iterator` veya `recursive_directory_iterator` ve bir yol içeriyor.|
|[directory_iterator Sınıfı](../standard-library/directory-iterator-class.md)|Bir dosya sistemi dizindeki dosya adlarını aracılığıyla dizilerinin bir giriş yineleyici açıklar.|
|[filesystem_error Sınıfı](../standard-library/filesystem-error-class.md)|Bir düzey sistemi taşması bildirmek için oluşturulan özel durumlar için temel sınıf.|
|[path Sınıfı](../standard-library/path-class.md)|Şablon türü bir nesne depolayan bir sınıf tanımlar `String` olan bir dosya adı olarak kullanmak için uygundur.|
|[recursive_directory_iterator Sınıfı](../standard-library/recursive-directory-iterator-class.md)|Bir dosya sistemi dizindeki dosya adlarını aracılığıyla dizilerinin bir giriş yineleyici açıklar. Yineleyici içinde alt dizinler de düzen.|
|[file_status Sınıfı](../standard-library/file-status-class.md)|Saran bir `file_type`.|

## <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[space_info Yapısı](../standard-library/space-info-structure.md)|Bir birim ilgili bilgileri tutar.|

## <a name="functions"></a>İşlevler

[\<FileSystem > işlevleri](../standard-library/filesystem-functions.md)

## <a name="operators"></a>İşleçler

[\<dosya sistemi > işleçleri](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|İle kullanılan bir numaralandırma [copy_file](https://msdn.microsoft.com/4af7a9b0-8861-45ed-b84e-0307f0669d60) ve hedef dosya zaten mevcutsa davranışını belirler.|
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|Dizin yineleyicileri için seçenekleri belirten bir sabit listesi.|
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|Dosya türleri için bir sabit listesi.|
|[izinleri](../standard-library/filesystem-enumerations.md#perms)|İzinler ve izinleri seçenekleri iletmek için kullanılan bir bit maskesi türü|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
