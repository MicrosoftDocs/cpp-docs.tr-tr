---
description: 'Hakkında daha fazla bilgi edinin: &lt; system_error&gt;'
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: 77ff4cae7d40ae4edb393e5d4f6743be1563556c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259415"
---
# <a name="ltsystem_errorgt"></a>&lt;system_error&gt;

\<system_error> `system_error` Alt düzey sistem hatalarını işlemek için özel durum sınıfını ve ilgili şablonları tanımlayan üstbilgiyi ekleyin.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<system_error>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="objects"></a>Nesneler

|Ad|Açıklama|
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Genel hataların kategorisini temsil eder.|
|[is_error_code_enum_v](../standard-library/system-error-functions.md#is_error_code_enum_v)||
|[is_error_condition_enum_v](../standard-library/system-error-functions.md#is_error_condition_enum_v)||
|[system_category](../standard-library/system-error-functions.md#system_category)|Alt düzey sistem taşmasından kaynaklanan hataların kategorisini temsil eder.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Bir `error_code` nesnesi oluşturur.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Bir `error_condition` nesnesi oluşturur.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç = =](../standard-library/system-error-operators.md#op_eq_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[işleç! =](../standard-library/system-error-operators.md#op_neq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[işleç<](../standard-library/system-error-operators.md#op_lt)|Bir nesnenin karşılaştırma için içeri geçirilen nesneden küçük olup olmadığını sınar.|
|[işleç<<](../standard-library/system-error-operators.md#op_ostream)||

### <a name="enums"></a>Numaralandırmalar

|Ad|Açıklama|
|-|-|
|[ERRC](../standard-library/system-error-enums.md#errc)|İçinde POSIX tarafından tanımlanan tüm hata kodu makroları için simgesel adlar sağlar `<errno.h>` .|

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|Ad|Açıklama|
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
