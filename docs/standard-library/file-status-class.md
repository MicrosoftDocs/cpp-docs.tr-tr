---
description: 'Hakkında daha fazla bilgi edinin: file_status sınıfı'
title: file_status Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.openlocfilehash: 8bc789d97f9b90b18214407fadab19e9644012a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324377"
---
# <a name="file_status-class"></a>file_status Sınıfı

Bir [file_type](../standard-library/filesystem-enumerations.md#file_type) [ve dosya avantajları](../standard-library/filesystem-enumerations.md#perms)sarar.

## <a name="syntax"></a>Syntax

```cpp
class file_status;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[file_status](#file_status)|[File_type](../standard-library/filesystem-enumerations.md#file_type) ve dosya [izinleri](../standard-library/filesystem-enumerations.md#perms)için bir sarmalayıcı oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[türüyle](#type)|Alır veya ayarlar `file_type` .|
|[izinleri](#permissions)|Dosya izinlerini alır veya ayarlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<filesystem>

**Ad alanı:** std:: deneysel:: FileSystem, std:: deneysel:: FileSystem

## <a name="file_statusfile_status"></a><a name="file_status"></a> file_status:: file_status

[File_type](../standard-library/filesystem-enumerations.md#file_type) ve dosya [izinleri](../standard-library/filesystem-enumerations.md#perms)için bir sarmalayıcı oluşturur.

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Type*\
Belirtildi `file_type` , varsayılan olarak olur `file_type::none` .

*maskesi*\
Belirtilen dosya `perms` , varsayılan olarak olur `perms::unknown` .

*file_status*\
Saklı nesne.

## <a name="file_statusoperator"></a><a name="op_as"></a> file_status:: operator =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>Parametreler

*file_status*\
İçine kopyalandığı [file_status](../standard-library/file-status-class.md) `file_status` .

## <a name="type"></a><a name="type"></a> türüyle

Alır veya ayarlar `file_type` .

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>Parametreler

*Type*\
Belirtildi `file_type` .

## <a name="permissions"></a><a name="permissions"></a> izinleri

Dosya izinlerini alır veya ayarlar.

Bir dosya oluşturmak `readonly` veya özniteliği kaldırmak için ayarlayıcısı 'nı kullanın `readonly` .

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>Parametreler

*maskesi*\
Belirtildi `perms` .

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[yol sınıfı](../standard-library/path-class.md)\
[\<filesystem>](../standard-library/filesystem.md)
