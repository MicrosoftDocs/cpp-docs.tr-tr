---
title: Hse_versıon_ınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08b16c59f155864a781feccbfd08842380cccd01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433809"
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

