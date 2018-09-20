---
title: DHtmlUrlEventMapEntry yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbac4b372f06f288eede8c578372d45334a5d707
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427530"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

