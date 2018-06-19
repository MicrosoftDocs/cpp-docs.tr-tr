---
title: DELETEITEMSTRUCT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f56a09742276c7fcb1bd66ff1a36b1d17cdf882
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370952"
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


