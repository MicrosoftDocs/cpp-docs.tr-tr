---
title: DRAWITEMSTRUCT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DRAWITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff4596a52170d0c6d197a0bda431963b5f0e9344
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120948"
---
# <a name="drawitemstruct-structure"></a>DRAWITEMSTRUCT Yapısı
`DRAWITEMSTRUCT` Yapısı sahip pencereyi sahip tarafından çizilmiş bir denetim veya menü öğesini boyamak nasıl belirleneceği olmalıdır bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagDRAWITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    UINT itemAction;  
    UINT itemState;  
    HWND hwndItem;  
    HDC hDC;  
    RECT rcItem;  
    DWORD itemData;  
} DRAWITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *CtlType*  
 Denetim türü. Denetim türleri için değerleri aşağıdaki gibidir:  
  
- Sahip tarafından çizilmiş ODT_BUTTON düğmesi  
  
- ODT_COMBOBOX sahip tarafından çizilmiş birleşik giriş kutusu  
  
- ODT_LISTBOX sahip tarafından çizilmiş liste kutusu  
  
- Sahip tarafından çizilmiş ODT_MENU menüsü  
  
- ODT_LISTVIEW liste görünümü denetimi  
  
- ODT_STATIC sahip tarafından çizilmiş statik denetimi  
  
- ODT_TAB sekme denetimi  
  
 *CtlID*  
 Birleşik giriş kutusu, liste kutusu veya düğmesi denetim kimliği. Bu üye için bir menü kullanılmaz.  
  
 *öğe kimliği*  
 Menü öğesi kimliği bir menüsü veya bir liste kutusu veya açılan kutusu öğenin dizini. Bir boş liste kutusu veya açılan kutu için bu üye, kendisini tarafından belirtilen koordinatları, yalnızca odak dikdörtgeni çizmek uygulama izin verir negatif bir değer olan `rcItem` üye denetiminde öğe olsa bile. Bu nedenle kullanıcı liste kutusu veya birleşik giriş kutusu giriş odağını sahip olup olmadığını da gösterilecek. Ayar bitleri `itemAction` üye dikdörtgen liste kutusu veya birleşik giriş kutusu odak giriş gibi sorgulamanıza çizilecek olup olmadığını belirler.  
  
 *itemAction*  
 Gerekli bir çizim eylemi tanımlar. Bu, bir veya daha fazla aşağıdaki BITS olacaktır:  
  
- Tüm denetim çizilmesi gerektiğinde ODA_DRAWENTIRE bu bit ayarlanır.  
  
- Denetim kazanır veya giriş odağı kaybettiğinde ODA_FOCUS bu bit ayarlanır. `itemState` Denetimi odağa sahip olup olmadığını belirlemek için üye işaretlenmelidir.  
  
- Tek seçim durum değiştiğinde ODA_SELECT bu bit ayarlanır. `itemState` Yeni seçim durumu belirlemek için üye işaretlenmelidir.  
  
 *itemState*  
 Geçerli çizim eylem gerçekleştirildikten sonra öğesi visual durumunu belirtir. Diğer bir deyişle, menü öğesi soluk ise, durumu bayrağı ODS_GRAYED ayarlanır. Durumu bayrakları aşağıdaki gibidir:  
  
- Menü öğesi denetlenecek ise ODS_CHECKED bu bit ayarlanır. Bu bit yalnızca menüde kullanılır.  
  
- Öğesini devre dışı olarak çizilecek ise ODS_DISABLED bu bit ayarlanır.  
  
- Öğenin odağa giriş ODS_FOCUS bu bit ayarlanır.  
  
- Öğe soluk ise ODS_GRAYED bu bit ayarlanır. Bu bit yalnızca menüde kullanılır.  
  
- Öğenin durumunu seçtiyseniz ODS_SELECTED bu bit ayarlanır.  
  
- ODS_COMBOBOXEDIT çizim ownerdrawn birleşik giriş kutusu seçim alanında (düzenleme denetimi) gerçekleşir.  
  
- ODS_DEFAULT öğesi varsayılan öğesidir.  
  
 *hwndItem*  
 Birleşik giriş kutuları, liste kutuları ve düğmeleri için Denetim pencere tanıtıcısı belirtir. Menü öğesi içeren menüyü (HMENU) tanıtıcısı belirtir.  
  
 *hDC*  
 Bir cihaz bağlamı tanımlar. Bu cihaz bağlamı denetimindeki çizim işlemleri gerçekleştirirken kullanılması gerekir.  
  
 *rcItem*  
 Dikdörtgene tarafından belirtilen cihaz bağlamı *hDC* çizilecek denetimin sınırları tanımlar üye. Windows otomatik olarak birleşik giriş kutuları, liste kutuları ve düğmeleri için cihaz bağlamda sahibi çizer herhangi bir şey küçük, ancak menü öğeleri küçük değil. Menü öğeleri çizerken sahibi tarafından tanımlanan dikdörtgenin sınırlarının dışında çekmek gerekir değil `rcItem` üyesi.  
  
 *ItemData*  
 Birleşik giriş kutusu veya liste kutusu için bu üye için liste kutusu aşağıdakilerden biri tarafından geçirilen değer içeriyor:  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 Bir menüyü bu üye menüsüne aşağıdakilerden biri tarafından geçirilen değer içeriyor:  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
## <a name="remarks"></a>Açıklamalar  
 Sahip tarafından çizilmiş denetim veya menü öğesini sahibi pencerenin bu yapı işaretçi alır *lParam* WM_DRAWITEM iletisinin parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

