---
title: filesystem_error Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: 1d142057859f1ca173f8953b34c07bbb3803ecba
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835876"
---
# <a name="filesystem_error-class"></a>filesystem_error Sınıfı

Düşük düzey sistem taşmasını raporlamak için oluşturulan tüm özel durumlar için temel sınıf.

## <a name="syntax"></a>Syntax

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, işlevlerde hata bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir \<filesystem> . `string` `mymesg` Buradan, Exposition 'ın amaçları doğrultusunda çağrılan, türünde bir nesne depolar. Ayrıca `path` , ve olarak adlandırılan türünde iki nesne depolar `mypval1` `mypval2` .

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[filesystem_error](#filesystem_error)|Bir `filesystem_error` ileti oluşturur.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[path1](#path1)|Döndürdüğü `mypval1`|
|[yol2](#path2)|Döndürdüğü `mypval2`|
|[Yazdırılacak](#what)|Bir işaretçi döndürür `NTBS` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<filesystem>

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="filesystem_error"></a><a name="filesystem_error"></a> filesystem_error

İlk Oluşturucu, *what_arg* ve *EC*'den mesajını oluşturur. İkinci Oluşturucu Ayrıca, içinde depoladığı *Pval1*öğesinden iletisini oluşturur `mypval1` . Üçüncü Oluşturucu Ayrıca, *Pval1*adresinden, içinde depoladığı `mypval1` ve *Pval2*' den depoladığı iletiyi de oluşturur `mypval2` .

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

*what_arg*\
Belirtilen ileti.

*EC*\
Belirtilen hata kodu.

*mypval1*\
Daha fazla belirtilmiş ileti parametresi.

*mypval2*\
Daha fazla belirtilmiş ileti parametresi.

## <a name="path1"></a><a name="path1"></a> path1

Üye işlevi şunu döndürür `mypval1`

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a><a name="path2"></a> yol2

Üye işlevi şunu döndürür `mypval2`

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a><a name="what"></a> Yazdırılacak

Üye işlevi, tercihen,,, `NTBS` ve öğesinden oluşan bir işaretçi `runtime_error::what()` döndürür `system_error::what()` `mymesg` `mypval1.native_string()` `mypval2.native_string()` .

```cpp
const char *what() const noexcept;
```
