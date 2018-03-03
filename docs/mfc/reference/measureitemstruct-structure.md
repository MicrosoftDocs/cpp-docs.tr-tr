---
title: "MEASUREITEMSTRUCT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MEASUREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce5221943ba1591a01ddebe2c261e4197fa18501
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT Yapısı
`MEASUREITEMSTRUCT` Yapısına sahip tarafından çizilmiş bir denetim veya menü öğesini boyutlarının Windows bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagMEASUREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    UINT itemWidth;  
    UINT itemHeight;  
    DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CtlType`  
 Denetim türü içerir. Denetim türleri için değerleri aşağıdaki gibidir:  
  
- **ODT_COMBOBOX** sahip çizim birleşik giriş kutusu  
  
- **ODT_LISTBOX** sahip çizim liste kutusu  
  
- **ODT_MENU** sahibi Çiz Menüsü  
  
 `CtlID`  
 Birleşik giriş kutusu, liste kutusu veya düğmesi denetim Kimliğini içerir. Bu üye için bir menü kullanılmaz.  
  
 `itemID`  
 Bir menüyü menü öğesi kimliği veya değişken yükseklikli birleşik giriş kutusu veya liste kutusu liste kutusu öğesi Kimliğini içerir. Bu üye için sabit yükseklik birleşik giriş kutusu veya liste kutusu ya da bir düğme için kullanılmaz.  
  
 *itemWidth*  
 Menü öğesi genişliğini belirtir. Gelen iletiyi döndürmeden önce sahip çizim menü öğesi sahibi bu üye doldurmanız gerekir.  
  
 *itemHeight*  
 Liste kutusu veya menü ayrı bir öğe yüksekliğini belirtir. İleti, sahibi tarafından çizilen birleşik giriş kutusu sahibi döndürmeden önce liste kutusu veya menü öğesi bu üye doldurmanız gerekir. Liste kutusu öğesi en fazla yüksekliği 255'tir.  
  
 `itemData`  
 Birleşik giriş kutusu veya liste kutusu için bu üye için liste kutusu aşağıdakilerden biri tarafından geçirilen değer içeriyor:  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 Bir menüyü bu üye menüsüne aşağıdakilerden biri tarafından geçirilen değer içeriyor:  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
 Bu, kullanıcı etkileşimi denetimi ile düzgün şekilde Windows sağlar. Uygun üyeleri doldurmak için hata `MEASUREITEMSTRUCT` yapısı, denetimin yanlış işlemi neden olur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

