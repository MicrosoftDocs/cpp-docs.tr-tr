---
description: 'Hakkında daha fazla bilgi edinin: &lt; system_error &gt; işlevleri'
title: '&lt;system_error &gt; işlevleri'
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
ms.openlocfilehash: 6d0283ca2a094e6257841569fcf7043b51ba4b1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259441"
---
# <a name="ltsystem_errorgt-functions"></a>&lt;system_error &gt; işlevleri

## <a name="generic_category"></a><a name="generic_category"></a> generic_category

Genel hataların kategorisini temsil eder.

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>Açıklamalar

`generic_category`Nesnesi [error_category](../standard-library/error-category-class.md)uygulamasıdır.

## <a name="is_error_code_enum_v"></a><a name="is_error_code_enum_v"></a> is_error_code_enum_v

```cpp
template <class T>
    inline constexpr bool is_error_code_enum_v = is_error_code_enum<T>::value;
```

## <a name="is_error_condition_enum_v"></a><a name="is_error_condition_enum_v"></a> is_error_condition_enum_v

```cpp
template <class T>
    inline constexpr bool is_error_condition_enum_v = is_error_condition_enum<T>::value;
```

## <a name="make_error_code"></a><a name="make_error_code"></a> make_error_code

Bir hata kodu nesnesi oluşturur.

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>Parametreler

*hatayla*\
`std::errc`Hata kodu nesnesinde depolanacak numaralandırma değeri.

### <a name="return-value"></a>Dönüş Değeri

Hata kodu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="make_error_condition"></a><a name="make_error_condition"></a> make_error_condition

Bir hata koşulu nesnesi oluşturur.

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>Parametreler

*hatayla*\
`std::errc`Hata kodu nesnesinde depolanacak numaralandırma değeri.

### <a name="return-value"></a>Dönüş Değeri

Hata koşulu nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="system_category"></a><a name="system_category"></a> system_category

Alt düzey sistem taşmasından kaynaklanan hataların kategorisini temsil eder.

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>Açıklamalar

`system_category`Nesnesi [error_category](../standard-library/error-category-class.md)uygulamasıdır.
