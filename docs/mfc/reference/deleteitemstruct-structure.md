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
ms.openlocfilehash: 5c844ad428143c82e8214eab74262b326bf2c9a4
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123246"
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
 *CtlType*  
 ODT_LISTBOX (sahip tarafından çizilmiş liste kutusu) veya ODT_COMBOBOX (sahip tarafından çizilmiş birleşik giriş kutusu) belirtir.  
  
 *CtlID*  
 Liste kutusu veya birleşik giriş kutusu tanımlayıcısını belirtir.  
  
 *öğe kimliği*  
 Liste kutusu veya açılan kutuda kaldırılmakta olan öğenin dizinini belirtir.  
  
 *hwndItem*  
 Denetim tanımlar.  
  
 *ItemData*  
 Uygulama tanımlı bir veri öğesi için belirtir. Bu değer denetim tarafından geçirilen *lParam* liste kutusu veya birleşik giriş kutusu öğesi ekler iletinin parametresi.  
  
## <a name="remarks"></a>Açıklamalar  
 Liste kutusu veya birleşik giriş kutusu veya liste kutusu veya birleşik giriş kutusu bozulduğunda bir öğe kaldırıldığında, Windows her silinmiş öğeyi sahibi WM_DELETEITEM ileti gönderir. *LParam* iletinin parametresi bu yapısına yönelik işaretçinin içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


