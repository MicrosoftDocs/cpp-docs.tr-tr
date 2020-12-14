---
description: 'Daha fazla bilgi edinin: HSE_VERSION_INFO yapısı'
title: HSE_VERSION_INFO Yapısı
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: fe03f3c4e00f9af62398993838927ce75410f17b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219635"
---
# <a name="hse_version_info-structure"></a>HSE_VERSION_INFO Yapısı

Bu yapı, üye işlevindeki *pver* parametresi tarafından işaret edilir `CHttpServer::GetExtensionVersion` . ISA sürüm numarasını ve ISA 'ın metin açıklamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
typedef struct _HSE_VERSION_INFO {
    DWORD dwExtensionVersion;
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;
```

#### <a name="parameters"></a>Parametreler

*dwExtensionVersion*<br/>
ISA sürüm numarası.

*lpszExtensionDesc*<br/>
ISA 'ın metin açıklaması. Varsayılan uygulama, yer tutucu metin sağlar; `CHttpServer::GetExtensionVersion` kendi açıklamanızı sağlamak için geçersiz kılın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Httpext. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
