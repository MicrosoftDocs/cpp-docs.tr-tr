---
title: "DHtmlUrlEventMapEntry yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DHtmlUrlEventMapEntry
dev_langs: C++
helpviewer_keywords: DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 37e43514c116f93841b1479103a6f29ec708bfa0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

