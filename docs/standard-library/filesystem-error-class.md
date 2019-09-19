---
title: filesystem_error Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: 7bd6b2d3d716ba25999388d44e7bd5a8d0750eb5
ms.sourcegitcommit: 76cc69b482ada8ebf0837e8cdfd4459661f996dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71127207"
---
# <a name="filesystem_error-class"></a>filesystem_error Sınıfı

Düşük düzey sistem taşmasını raporlamak için oluşturulan tüm özel durumlar için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, \<FileSystem > işlevlerde hata bildirmek üzere oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar. Buradan, Exposition 'ın amaçları doğrultusunda `string`çağrılan `mymesg` , türünde bir nesne depolar. Ayrıca, ve `path` `mypval1`olarakadlandırılantüründe ikinesnedepolar`mypval2`.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[filesystem_error](#filesystem_error)|Bir `filesystem_error` ileti oluşturur.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[path1](#path1)|Döndürdüğü`mypval1`|
|[yol2](#path2)|Döndürdüğü`mypval2`|
|[Yazdırılacak](#what)|Bir `NTBS`işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<dosya sistemi >

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="filesystem_error"></a>filesystem_error

İlk Oluşturucu, iletisini *what_arg* ve *EC*'den oluşturur. İkinci Oluşturucu Ayrıca, içinde `mypval1`depoladığı *Pval1*öğesinden iletisini oluşturur. Üçüncü Oluşturucu Ayrıca, *Pval1*adresinden, içinde `mypval1`depoladığı ve *Pval2*' den depoladığı `mypval2`iletiyi de oluşturur.

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

## <a name="path1"></a>path1

Üye işlevi şunu döndürür`mypval1`

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a>yol2

Üye işlevi şunu döndürür`mypval2`

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a>Yazdırılacak

Üye `NTBS`işlevi, `system_error::what()` `runtime_error::what()` tercihen,`mymesg`,, ve`mypval2.native_string()`öğesinden oluşan bir işaretçi döndürür. `mypval1.native_string()`

```cpp
const char *what() const noexcept;
```
