---
description: 'Daha fazla bilgi edinin: Dhtmlurtaventmapentry yapısı'
title: DHtmlUrlEventMapEntry Yapısı
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c35e3ac70d8530042ca73397b0f7c6df13501497
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220064"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry Yapısı

`DHtmlUrlEventMapEntry`Yapı, çok URL olan olay haritası desteği sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct DHtmlUrlEventMapEntry
{
LPCTSTR szUrl;
const DHtmlEventMapEntry *pEventMap;
};
```

#### <a name="parameters"></a>Parametreler

*szUrl*<br/>
URL.

*pEventMap*<br/>
URL ile ilişkili olay haritası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
