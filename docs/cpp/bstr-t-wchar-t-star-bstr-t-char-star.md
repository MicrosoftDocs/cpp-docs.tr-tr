---
title: _bstr_t::wchar_t *, _bstr_t::char* | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs:
- C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abd0b53c178e028b975e2b26d36317b773c2cfa5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102768"
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t *, _bstr_t::char*

**Microsoft'a özgü**

BSTR karakter, bir dar veya geniş karakter dizisi olarak döndürür.

## <a name="syntax"></a>Sözdizimi

```
operator const wchar_t*( ) const throw( ); 
operator wchar_t*( ) const throw( ); 
operator const char*( ) const; 
operator char*( ) const;
```

## <a name="remarks"></a>Açıklamalar

Bu işleçler yalıtılan karakter verileri ayıklamak için kullanılabilir `BSTR` nesne. Yeni bir değer döndürülen işaretçi atama orijinal BSTR verileri değiştirmez.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)