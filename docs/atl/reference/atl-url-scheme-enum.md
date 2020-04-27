---
title: ATL_URL_SCHEME numaralandırması
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 6d8307d6ea51c5ec7e63735360b8628a4c1ed782
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168585"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

Bu numaralandırmanın üyeleri, [kıvrımlı](curl-class.md)tarafından anlaşılan şemalar için sabitler sağlar.

## <a name="syntax"></a>Sözdizimi

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
