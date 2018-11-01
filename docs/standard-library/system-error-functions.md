---
title: '&lt;system_error&gt; işlevleri'
ms.date: 11/04/2016
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
ms.openlocfilehash: 24890830456e3c1026b02960aa650a43da3b6067
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554406"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; işlevleri

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a>  generic_category

Genel hataları kategorisini temsil eder.

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>Açıklamalar

`generic_category` Nesnedir uygulaması [error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a>  make_error_code

Bir hata kodu nesnesi oluşturur.

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Gt; _errno &*|Hata kodu nesnesi içinde saklamak için numaralandırma değeri.|

### <a name="return-value"></a>Dönüş Değeri

Hata kodu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="make_error_condition"></a>  make_error_condition

Bir hata koşulu nesnesi oluşturur.

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Gt; _errno &*|Hata koşulu nesnesi içinde saklamak için numaralandırma değeri.|

### <a name="return-value"></a>Dönüş Değeri

Hata koşulu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="system_category"></a>  system_category

Alt düzey sistemi taşıyor tarafından neden olduğu hata kategorisini temsil eder.

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>Açıklamalar

`system_category` Nesnedir uygulaması [error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[<system_error>](../standard-library/system-error.md)<br/>
