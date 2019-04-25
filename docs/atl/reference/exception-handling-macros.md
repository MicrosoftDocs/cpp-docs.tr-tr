---
title: Özel durum işleme makroları
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 8afb2019e38f7548467e85d9a2c1c12c538cf744
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276269"
---
# <a name="exception-handling-macros"></a>Özel durum işleme makroları

Bu makrolar, özel durum işleme için destek sağlar.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|Deyim ilişkili oluşan hataları işleyecek `_ATLTRY`.|
|[_ATLCATCHALL](#_atlcatchall)|Deyim ilişkili oluşan hataları işleyecek `_ATLTRY`.|
|[_ATLTRY](#_atltry)|Burada bir hata büyük olasılıkla oluşabilir bir korumalı kod bölümünde işaretler.|

## <a name="requirements"></a>Gereksinimler:

**Başlık:** atldef.h

##  <a name="_atlcatch"></a>  _ATLCATCH

Deyim ilişkili oluşan hataları işleyecek `_ATLTRY`.

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Parametreler

*e*<br/>
Yakalamak için özel durum.

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılan `_ATLTRY`. C++ için çözümler [(CAtlException e) catch](../../cpp/try-throw-and-catch-statements-cpp.md) C++ özel durumlarını belirli bir tür işlemek için.

##  <a name="_atlcatchall"></a>  _ATLCATCHALL

Deyim ilişkili oluşan hataları işleyecek `_ATLTRY`.

```
_ATLCATCHALL
```

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılan `_ATLTRY`. C++ için çözümler [gt;catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) türlü C++ özel durumlarını işlemek için.

##  <a name="_atltry"></a>  _ATLTRY

Burada bir hata büyük olasılıkla oluşabilir bir korumalı kod bölümünde işaretler.

```
_ATLTRY
```

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılan [_ATLCATCH](#_atlcatch) veya [_ATLCATCHALL](#_atlcatchall). C++ sembole çözümler [deneyin](../../cpp/try-throw-and-catch-statements-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Makroları](../../atl/reference/atl-macros.md)
