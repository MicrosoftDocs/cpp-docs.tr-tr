---
title: filesystem_error Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: add1e0da43a44c35f39c96e8d65e36aeea0d3afb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628988"
---
# <a name="filesystemerror-class"></a>filesystem_error Sınıfı

Bir düzey sistemi taşması bildirmek için oluşturulan tüm özel durumlar için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Açıklamalar

Sınıfı bir hata rapor için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir \<filesystem > işlevleri. Türünde bir nesne depolar `string`adlı `mymesg` exposition amaçları için burada. Türünden iki nesne de depolar `path`adlı `mypval1` ve `mypval2`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[filesystem_error](#filesystem_error)|Oluşturur bir `filesystem_error` ileti.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[yol1](#path1)|döndürür `mypval1`|
|[yol2](#path2)|döndürür `mypval2`|
|[ne](#what)|Bir işaretçi döndüren bir `NTBS`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error::filesystem_error

İlk Oluşturucu, ileti oluşturur *what_arg* ve *ec*. İkinci oluşturucu Ayrıca, ileti oluşturur *pval1*, içinde depoladığı `mypval1`. Üçüncü Oluşturucu, ayrıca kendi ileti oluşturur *pval1*, içinde depoladığı `mypval1`, gelen ve giden *pval2*, içinde depoladığı `mypval2`.

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

### <a name="parameters"></a>Parametreler

*what_arg*<br/>
Belirtilen ileti.

*EC*<br/>
Belirtilen hata kodu.

*mypval1*<br/>
Daha fazla belirtilen iletiyi parametresi.

*mypval2*<br/>
Daha fazla belirtilen iletinin parametresi.

## <a name="path1"></a> filesystem_error::path1

Üye işlevi döndürür `mypval1`

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> filesystem_error::path2

Üye işlevi döndürür `mypval2`

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> filesystem_error::What

Üye işlevi işaretçisi döndüren bir `NTBS`, tercihen oluşan gelen `runtime_error::what()`, `system_error::what()`, `mymesg`, `mypval1.native_string()`, ve `mypval2.native_string()`.

```cpp
const char *what() const noexcept;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[system_error Sınıfı](../standard-library/system-error-class.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
[\<Özel Durum >](../standard-library/exception.md)<br/>
