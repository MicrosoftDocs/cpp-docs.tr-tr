---
title: HSE_VERSION_INFO Yapısı
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: 6bdb668be037dfaa07e1121e4b61ea332e430e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577300"
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO Yapısı

Bu yapı tarafından işaret edilen *pVer* parametresinde `CHttpServer::GetExtensionVersion` üye işlevi. ISA sürüm numarasını ve ISA metin açıklamasını sağlar

## <a name="syntax"></a>Sözdizimi

```
typedef struct _HSE_VERSION_INFO {
    DWORD dwExtensionVersion;
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;
```

#### <a name="parameters"></a>Parametreler

*dwExtensionVersion*<br/>
ISA sürüm numarası

*lpszExtensionDesc*<br/>
ISA açıklama metni Varsayılan uygulama, yer tutucu metni sağlar. geçersiz kılma `CHttpServer::GetExtensionVersion` kendi açıklama.

## <a name="requirements"></a>Gereksinimler

**Başlık:** httpext.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

