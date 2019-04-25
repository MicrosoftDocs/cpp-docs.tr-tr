---
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
ms.openlocfilehash: 81ce4ecc1673087db8e985f94e297798dd712a6e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160023"
---
# <a name="filestatus-class"></a>file_status Sınıfı

Saran bir [file_type](../standard-library/filesystem-enumerations.md#file_type) ve dosya [izinleri](../standard-library/filesystem-enumerations.md#perms).

## <a name="syntax"></a>Sözdizimi

```cpp
class file_status;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[file_status](#file_status)|İçin bir sarmalayıcı oluşturur [file_type](../standard-library/filesystem-enumerations.md#file_type) ve dosya [izinleri](../standard-library/filesystem-enumerations.md#perms).|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[type](#type)|Alır veya ayarlar `file_type`.|
|[izinleri](#permissions)|Alır veya dosya izinlerini ayarlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_as)|Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** std::experimental::filesystem, std::experimental::filesystem

## <a name="file_status"></a> file_status::file_status

İçin bir sarmalayıcı oluşturur [file_type](../standard-library/filesystem-enumerations.md#file_type) ve dosya [izinleri](../standard-library/filesystem-enumerations.md#perms).

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>Parametreler

*ftype*<br/>
Belirtilen `file_type`, varsayılan olarak `file_type::none`.

*mask*<br/>
Belirtilen dosya `perms`, varsayılan olarak `perms::unknown`.

*file_status*<br/>
Depolanan nesne.

## <a name="op_as"></a> file_status::operator =

Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>Parametreler

*file_status*<br/>
[File_status](../standard-library/file-status-class.md) içine kopyalanan `file_status`.

## <a name="type"></a> Türü

Alır veya ayarlar `file_type`.

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>Parametreler

*ftype*<br/>
Belirtilen `file_type`.

## <a name="permissions"></a> İzinleri

Alır veya dosya izinlerini ayarlar.

Ayarlayıcı dosya yapma `readonly` Kaldır `readonly` özniteliği.

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>Parametreler

*mask*<br/>
Belirtilen `perms`.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[path Sınıfı](../standard-library/path-class.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
