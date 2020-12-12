---
description: 'Hakkında daha fazla bilgi edinin: ATL_URL_SCHEME'
title: ATL_URL_SCHEME numaralandırması
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 72c149345a0e1edd41bfc9b32d1e94ab6477d488
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165140"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

Bu numaralandırmanın üyeleri, [kıvrımlı](curl-class.md)tarafından anlaşılan şemalar için sabitler sağlar.

## <a name="syntax"></a>Syntax

```cpp
enum ATL_URL_SCHEME{
   ATL_URL_SCHEME_UNKNOWN = -1,
   ATL_URL_SCHEME_FTP     = 0,
   ATL_URL_SCHEME_GOPHER  = 1,
   ATL_URL_SCHEME_HTTP    = 2,
   ATL_URL_SCHEME_HTTPS   = 3,
   ATL_URL_SCHEME_FILE    = 4,
   ATL_URL_SCHEME_NEWS    = 5,
   ATL_URL_SCHEME_MAILTO  = 6,
   ATL_URL_SCHEME_SOCKS   = 7
};
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../active-template-library-atl-concepts.md)<br/>
[Kıvır:: SetScheme](curl-class.md#setscheme)<br/>
[Kıvır:: GetScheme](curl-class.md#getscheme)
