---
title: "DHtmlUrlEventMapEntry yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea92126cf57bf122ebd720d6bd8e6f12a98f65ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry Yapısı
`DHtmlUrlEventMapEntry` Yapısı çok URL olay eşlemesi desteği sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct DHtmlUrlEventMapEntry  
{  
LPCTSTR szUrl;  
const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szUrl`  
 URL.  
  
 *pEventMap*  
 URL ile ilişkili olay eşlemesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdhtml.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

