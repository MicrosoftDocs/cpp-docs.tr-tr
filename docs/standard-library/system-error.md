---
title: '&lt;system_error&gt;'
ms.date: 11/04/2016
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: cb4870a22fd06039751f87f26dfa40e8ddcf2500
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662767"
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;

Üstbilgisini \<system_error > özel durum sınıfı tanımlamak için `system_error` ve ilgili alt düzey sistemi hataları işlemek için şablonlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <system_error>
```

### <a name="objects"></a>Nesneler

|||
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Genel hataları kategorisini temsil eder.|
|[system_category](../standard-library/system-error-functions.md#system_category)|Alt düzey sistemi taşıyor tarafından neden olduğu hata kategorisini temsil eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[generic_errno](../standard-library/system-error-typedefs.md#generic_errno)|Posıx'te tarafından tanımlanan tüm hata kodu makroları için simgesel adlar sağlar numaralandırma temsil eden bir tür `<errno.h>`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Oluşturur bir `error_code` nesne.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Oluşturur bir `error_condition` nesne.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](../standard-library/system-error-operators.md#op_eq_eq)|İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.|
|[operator!=](../standard-library/system-error-operators.md#op_neq)|İşlecin sol tarafındaki nesne işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/system-error-operators.md#op_lt)|Bir nesnenin karşılaştırma için içeri geçirilen nesneden küçük olup olmadığını sınar.|

### <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[errc](../standard-library/system-error-enums.md#errc)|Posıx'te tarafından tanımlanan tüm hata kodu makroları için simgesel adlar sağlar `<errno.h>`.|

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|||
|-|-|
|[error_category](../standard-library/error-category-class.md)|Nesneler için bir kategori hata kodlarının tanımlayan soyut, ortak temel temsil eder.|
|[error_code](../standard-library/error-code-class.md)|Uygulamaya özel alt düzey sistemi hataları temsil eder.|
|[error_condition](../standard-library/error-condition-class.md)|Kullanıcı tanımlı hata kodları temsil eder.|
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|İçin test eden bir tür koşulu temsil eden [error_code sınıfı](../standard-library/error-code-class.md) sabit listesi.|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|İçin test eden bir tür koşulu temsil eden [error_condition sınıfı](../standard-library/error-condition-class.md) sabit listesi.|
|[system_error](../standard-library/system-error-class.md)|Bir düzey sistemi taşması bildirmek için oluşturulan tüm özel durumlar için temel sınıfı temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<system_error >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
