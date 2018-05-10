---
title: '&lt;system_error&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 6135a3dc51b372c85545f01f52c70cbc6f236e64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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

`generic_category` Nesnesidir uygulaması [error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a>  make_error_code

Bir hata kodu nesnesi oluşturur.

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`_Errno`|Hata kodu nesnesinde saklamak için numaralandırma değeri.|

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
|`_Errno`|Hata koşulu nesnesinde saklamak için numaralandırma değeri.|

### <a name="return-value"></a>Dönüş Değeri

Hata koşulu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="system_category"></a>  system_category

Alt düzey sistem taşan tarafından kaynaklanan hataları kategorisini temsil eder.

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>Açıklamalar

`system_category` Nesnesidir uygulaması [error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[<system_error>](../standard-library/system-error.md)<br/>
