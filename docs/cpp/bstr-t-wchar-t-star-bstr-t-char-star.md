---
description: ': _Bstr_t:: wchar_t *, _bstr_t:: char* hakkında daha fazla bilgi edinin'
title: _bstr_t::wchar_t *, _bstr_t::char*
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
ms.openlocfilehash: 278b122bbc208addab8e9a40e61300ce91a530cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278824"
---
# <a name="_bstr_twchar_t-_bstr_tchar"></a>_bstr_t::wchar_t\*, _bstr_t::char\*

**Microsoft'a Özgü**

BSTR karakterlerini dar veya geniş bir karakter dizisi olarak döndürür.

## <a name="syntax"></a>Syntax

```
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>Açıklamalar

Bu işleçler, nesne tarafından kapsüllenmiş karakter verilerini ayıklamak için kullanılabilir `BSTR` . Döndürülen işaretçiye yeni bir değer atanması orijinal BSTR verilerini değiştirmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
