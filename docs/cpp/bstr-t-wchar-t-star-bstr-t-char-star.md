---
description: ': _Bstr_t:: wchar_t *, _bstr_t:: char* hakkında daha fazla bilgi edinin'
title: _bstr_t::wchar_t *, _bstr_t::char*
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.openlocfilehash: b2e98ea4b62d4a2e346b552d31d66d23f301817c
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522553"
---
# <a name="_bstr_twchar_t-_bstr_tchar"></a>`_bstr_t::wchar_t*`, `_bstr_t::char*`

**Microsoft'a Özgü**

`BSTR`Karakterleri dar veya geniş bir karakter dizisi olarak döndürür.

## <a name="syntax"></a>Syntax

```cpp
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>Açıklamalar

Bu işleçler, nesne tarafından kapsüllenmiş karakter verilerini ayıklamak için kullanılabilir `BSTR` . Döndürülen işaretçiye yeni bir değer atamak özgün `BSTR` verileri değiştirmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)
