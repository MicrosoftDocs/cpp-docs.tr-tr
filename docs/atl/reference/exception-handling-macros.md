---
title: Özel durum işleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b503e36dfe04eaa3180809033187957ff8d970a0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766821"
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

*e*  
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

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
