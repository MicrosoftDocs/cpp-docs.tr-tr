---
title: "DELETEITEMSTRUCT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DELETEITEMSTRUCT
dev_langs: C++
helpviewer_keywords: DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5be80d8b139f04daa0c44fc2808f61538843e3e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT Yapısı
`DELETEITEMSTRUCT` Yapısını silinmiş bir sahip tarafından çizilmiş liste kutusu veya açılan kutu öğeyi açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CtlType`  
 Belirtir **ODT_LISTBOX** (sahip tarafından çizilmiş liste kutusu) veya **ODT_COMBOBOX** (sahip tarafından çizilmiş birleşik giriş kutusu).  
  
 `CtlID`  
 Liste kutusu veya birleşik giriş kutusu tanımlayıcısını belirtir.  
  
 `itemID`  
 Liste kutusu veya açılan kutuda kaldırılmakta olan öğenin dizinini belirtir.  
  
 `hwndItem`  
 Denetim tanımlar.  
  
 `itemData`  
 Uygulama tanımlı bir veri öğesi için belirtir. Bu değer denetim tarafından geçirilen **lParam** liste kutusu veya birleşik giriş kutusu öğesi ekler iletinin parametresi.  
  
## <a name="remarks"></a>Açıklamalar  
 Liste kutusu veya birleşik giriş kutusu veya liste kutusu veya birleşik giriş kutusu bozulduğunda bir öğe kaldırıldığında, Windows gönderir `WM_DELETEITEM` sahibine silinen her öğe için ileti. **LParam** iletinin parametresi bu yapısına yönelik işaretçinin içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


