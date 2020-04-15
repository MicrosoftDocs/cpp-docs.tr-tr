---
title: Özel Durum İşleme Makroları
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 2beffbbed0efee799005190bd7fd071a2087e4d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330080"
---
# <a name="exception-handling-macros"></a>Özel Durum İşleme Makroları

Bu makrolar özel durum işleme desteği sağlar.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|Ekstre(ler) ilişkili `_ATLTRY`de oluşan hataları işlemek için .|
|[_ATLCATCHALL](#_atlcatchall)|Ekstre(ler) ilişkili `_ATLTRY`de oluşan hataları işlemek için .|
|[_ATLTRY](#_atltry)|Bir hatanın oluşabileceği korunan bir kod bölümünü işaretler.|

## <a name="requirements"></a>Gereksinimler:

**Üstbilgi:** atldef.h

## <a name="_atlcatch"></a><a name="_atlcatch"></a>_ATLCATCH

Ekstre(ler) ilişkili `_ATLTRY`de oluşan hataları işlemek için .

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Parametreler

*E*<br/>
Yakalamanın istisnası.

### <a name="remarks"></a>Açıklamalar

`_ATLTRY`ile birlikte kullanılır. Belirli bir C++ özel durum türünü işlemek için C++ [catch(CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) giderir.

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a>_ATLCATCHALL

Ekstre(ler) ilişkili `_ATLTRY`de oluşan hataları işlemek için .

```
_ATLCATCHALL
```

### <a name="remarks"></a>Açıklamalar

`_ATLTRY`ile birlikte kullanılır. C++ [catch(...)](../../cpp/try-throw-and-catch-statements-cpp.md) için tüm C++ özel durumlarını işlemek için çözümler.

## <a name="_atltry"></a><a name="_atltry"></a>_ATLTRY

Bir hatanın oluşabileceği korunan bir kod bölümünü işaretler.

```
_ATLTRY
```

### <a name="remarks"></a>Açıklamalar

[_ATLCATCH](#_atlcatch) veya [_ATLCATCHALL](#_atlcatchall)ile birlikte kullanılır. C++ simgesine [gider.](../../cpp/try-throw-and-catch-statements-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
