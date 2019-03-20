---
title: '&lt;system_error&gt; işlevleri'
ms.date: 03/15/2019
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 78be83af678b553babbf1cde3d96c1507940b611
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58172913"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; işlevleri

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|||

## <a name="generic_category"></a> generic_category

Genel hataları kategorisini temsil eder.

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>Açıklamalar

`generic_category` Nesnedir uygulaması [error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a>  make_error_code

Bir hata kodu nesnesi oluşturur.

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>Parametreler

*Hata*\
`std::errc` Hata kodu nesnesi içinde saklamak için numaralandırma değeri.

### <a name="return-value"></a>Dönüş Değeri

Hata kodu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="make_error_condition"></a>  make_error_condition

Bir hata koşulu nesnesi oluşturur.

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>Parametreler

*Hata*\
`std::errc` Hata kodu nesnesi içinde saklamak için numaralandırma değeri.

### <a name="return-value"></a>Dönüş Değeri

Hata koşulu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="system_category"></a>  system_category

Alt düzey sistemi taşıyor tarafından neden olduğu hata kategorisini temsil eder.

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>Açıklamalar

`system_category` Nesnedir uygulaması [error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[\<system_error>](../standard-library/system-error.md)<br/>
