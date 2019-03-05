---
title: DHtmlUrlEventMapEntry Yapısı
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c9b58067a9c8b6a71cd22b654a2f82ba0f8bfe36
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292659"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry Yapısı

`DHtmlUrlEventMapEntry` Yapısı çok URL'li olay eşleme desteği sağlar.

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
Olay eşlemesi URL'si ile ilişkili.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdhtml.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
