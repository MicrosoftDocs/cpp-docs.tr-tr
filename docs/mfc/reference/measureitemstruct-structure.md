---
title: MEASUREITEMSTRUCT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MEASUREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcf4bd41d00f6999b4158f0884c39e7a16d10bcc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336965"
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT Yapısı
`MEASUREITEMSTRUCT` Yapısı Windows özelleştirilmiş olarak çizilen bir denetimi ya da menü öğesi boyutlarının bildirir.  
  
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
 *CtlType*  
 Denetim türünü içerir. Denetim tipleri için değerler aşağıdaki gibidir:  
  
- ODT_COMBOBOX özelleştirilmiş çizimli birleşik giriş kutusu  
  
- ODT_LISTBOX sahip çizim liste kutusu  
  
- ODT_MENU sahip çizim menüsü  
  
 *CtlID*  
 Birleşik giriş kutusu, liste kutusu ve düğme denetim Kimliğini içerir. Bu üye için bir menü kullanılmaz.  
  
 *öğe kimliği*  
 Bir menü menü öğesi kimliği veya liste kutusu ya da değişken birleşik giriş kutusu liste kutusu öğesi kimliği içerir. Bu üye için sabit yükseklik birleşik giriş kutusu ya da liste kutusu ya da bir düğme için kullanılmaz.  
  
 *itemWidth*  
 Bir menü öğesinin genişliğini belirtir. Sahip çizim menüsü öğenin sahibi, ileti döndürülmeden önce bu üye doldurmanız gerekir.  
  
 *itemHeight*  
 Liste kutusu veya menü ayrı bir öğe yüksekliğini belirtir. İleti, özelleştirilmiş çizimli birleşik giriş kutusu sahibi döndürmeden önce liste kutusu veya menü öğesi bu üye doldurmanız gerekir. Bir liste kutusu öğesinin yükseklik en fazla 255'tir.  
  
 *ItemData*  
 Birleşik giriş kutusu veya liste kutusunda, bu üye liste kutusuna aşağıdakilerden biri tarafından geçirilen değeri içerir:  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 Bir menü için bu üye menüsüne aşağıdakilerden biri tarafından geçirilen değeri içerir:  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
 Bu, kullanıcı etkileşimi denetimi ile doğru şekilde işlemek Windows sağlar. Uygun üyeleri doldurmak için hata `MEASUREITEMSTRUCT` yapısı, denetimin yanlış işlemi neden olur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

