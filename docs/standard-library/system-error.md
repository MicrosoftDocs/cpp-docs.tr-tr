---
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: e6eef7152e45e8177c451fc25592fab85c58ccb5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449760"
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;

Özel durum sınıfını \< `system_error` ve alt düzey sistem hatalarını işlemeye yönelik ilgili şablonları tanımlamak için system_error > üst bilgisini ekleyin.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<system_error >

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="objects"></a>Nesneler

|||
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Genel hataların kategorisini temsil eder.|
|[is_error_code_enum_v](../standard-library/system-error-functions.md#is_error_code_enum_v)||
|[is_error_condition_enum_v](../standard-library/system-error-functions.md#is_error_condition_enum_v)||
|[system_category](../standard-library/system-error-functions.md#system_category)|Alt düzey sistem taşmasından kaynaklanan hataların kategorisini temsil eder.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Oluşturur bir `error_code` nesne.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Oluşturur bir `error_condition` nesne.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](../standard-library/system-error-operators.md#op_eq_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[operator!=](../standard-library/system-error-operators.md#op_neq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/system-error-operators.md#op_lt)|Bir nesnenin karşılaştırma için içeri geçirilen nesneden küçük olup olmadığını sınar.|
|[işleç < <](../standard-library/system-error-operators.md#op_ostream)||

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[ERRC](../standard-library/system-error-enums.md#errc)|İçinde `<errno.h>`POSIX tarafından tanımlanan tüm hata kodu makroları için simgesel adlar sağlar.|

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|||
|-|-|
|[error_category](../standard-library/error-category-class.md)|Bir hata kodları kategorisini açıklayan nesneler için soyut, ortak temeli temsil eder.|
|[error_code](../standard-library/error-code-class.md)|Uygulamaya özgü olan alt düzey sistem hatalarını temsil eder.|
|[error_condition](../standard-library/error-condition-class.md)|Kullanıcı tanımlı hata kodlarını temsil eder.|
|[yla](../standard-library/hash-structure.md#system_error)||
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|[Error_code sınıfı](../standard-library/error-code-class.md) numaralandırması için test edilen bir tür koşulunu temsil eder.|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|[Error_condition sınıfı](../standard-library/error-condition-class.md) numaralandırması için test edilen bir tür koşulunu temsil eder.|
|[system_error](../standard-library/system-error-class.md)|Düşük düzey sistem taşmasını raporlamak için oluşturulan tüm özel durumların temel sınıfını temsil eder.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
