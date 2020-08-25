---
title: Özel durum Işleme makroları
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 7fcd8221ba5f121749cf366a93cc8a6d8d00ed7c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833445"
---
# <a name="exception-handling-macros"></a>Özel durum Işleme makroları

Bu makrolar özel durum işleme desteği sağlar.

|Ad|Açıklama|
|-|-|
|[_ATLCATCH](#_atlcatch)|İlişkili içinde oluşan hataları işlemek için deyimler `_ATLTRY` .|
|[_ATLCATCHALL](#_atlcatchall)|İlişkili içinde oluşan hataları işlemek için deyimler `_ATLTRY` .|
|[_ATLTRY](#_atltry)|Bir hata oluşması durumunda, korunan bir kod bölümünü işaretler.|

## <a name="requirements"></a>Gereksinimler:

**Üstbilgi:** atldef. h

## <a name="_atlcatch"></a><a name="_atlcatch"></a> _ATLCATCH

İlişkili içinde oluşan hataları işlemek için deyimler `_ATLTRY` .

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Parametreler

*a*<br/>
Catch için özel durum.

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılır `_ATLTRY` . Verilen bir tür C++ özel durumunu işlemek için C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) olarak çözümlenir.

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a> _ATLCATCHALL

İlişkili içinde oluşan hataları işlemek için deyimler `_ATLTRY` .

```
_ATLCATCHALL
```

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılır `_ATLTRY` . Tüm C++ özel durum türlerini işlemek için C++ [catch (...)](../../cpp/try-throw-and-catch-statements-cpp.md) olarak çözümlenir.

## <a name="_atltry"></a><a name="_atltry"></a> _ATLTRY

Bir hata oluşması durumunda, korunan bir kod bölümünü işaretler.

```
_ATLTRY
```

### <a name="remarks"></a>Açıklamalar

[_ATLCATCH](#_atlcatch) veya [_ATLCATCHALL](#_atlcatchall)birlikte kullanılır. C++ sembolü [TRY](../../cpp/try-throw-and-catch-statements-cpp.md)' de çözümleniyor.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
