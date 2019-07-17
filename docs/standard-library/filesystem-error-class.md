---
title: filesystem_error Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: c3dbfc080f0a1494950016f42189d932be05b0f1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240738"
---
# <a name="filesystemerror-class"></a>filesystem_error Sınıfı

Bir düzey sistemi taşması bildirmek için oluşturulan tüm özel durumlar için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Açıklamalar

Sınıfı bir hata rapor için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir \<filesystem > işlevleri. Türünde bir nesne depolar `string`adlı `mymesg` exposition amaçları için burada. Türünden iki nesne de depolar `path`adlı `mypval1` ve `mypval2`.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[filesystem_error](#filesystem_error)|Oluşturur bir `filesystem_error` ileti.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[yol1](#path1)|döndürür `mypval1`|
|[yol2](#path2)|döndürür `mypval2`|
|[ne](#what)|Bir işaretçi döndüren bir `NTBS`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error

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

*what_arg*\
Belirtilen ileti.

*EC*\
Belirtilen hata kodu.

*mypval1*\
Daha fazla belirtilen iletiyi parametresi.

*mypval2*\
Daha fazla belirtilen iletinin parametresi.

## <a name="path1"></a> yol1

Üye işlevi döndürür `mypval1`

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> yol2

Üye işlevi döndürür `mypval2`

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> ne

Üye işlevi işaretçisi döndüren bir `NTBS`, tercihen oluşan gelen `runtime_error::what()`, `system_error::what()`, `mymesg`, `mypval1.native_string()`, ve `mypval2.native_string()`.

```cpp
const char *what() const noexcept;
```
