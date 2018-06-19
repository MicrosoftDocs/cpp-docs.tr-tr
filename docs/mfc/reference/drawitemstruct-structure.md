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
ms.openlocfilehash: bdb7daba666e8aaf983eadc77417cad46180e7df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378275"
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
 `CtlType`  
 Denetim türü. Denetim türleri için değerleri aşağıdaki gibidir:  
  
- **ODT_BUTTON** sahip tarafından çizilmiş düğmesi  
  
- **ODT_COMBOBOX** sahip tarafından çizilmiş birleşik giriş kutusu  
  
- **ODT_LISTBOX** sahip tarafından çizilmiş liste kutusu  
  
- **ODT_MENU** sahip tarafından çizilmiş menüsü  
  
- **ODT_LISTVIEW** liste görünümü denetimi  
  
- **ODT_STATIC** sahip tarafından çizilmiş statik denetimi  
  
- **ODT_TAB** sekme denetimi  
  
 `CtlID`  
 Birleşik giriş kutusu, liste kutusu veya düğmesi denetim kimliği. Bu üye için bir menü kullanılmaz.  
  
 `itemID`  
 Menü öğesi kimliği bir menüsü veya bir liste kutusu veya açılan kutusu öğenin dizini. Bir boş liste kutusu veya açılan kutu için bu üye, kendisini tarafından belirtilen koordinatları, yalnızca odak dikdörtgeni çizmek uygulama izin verir negatif bir değer olan **rcItem** üye denetiminde öğe olsa bile. Bu nedenle kullanıcı liste kutusu veya birleşik giriş kutusu giriş odağını sahip olup olmadığını da gösterilecek. Ayar bitleri **itemAction** üye dikdörtgen liste kutusu veya birleşik giriş kutusu odak giriş gibi sorgulamanıza çizilecek olup olmadığını belirler.  
  
 `itemAction`  
 Gerekli bir çizim eylemi tanımlar. Bu, bir veya daha fazla aşağıdaki BITS olacaktır:  
  
- **ODA_DRAWENTIRE** tüm denetim çizilmesi gerektiğinde bu bit ayarlanır.  
  
- **ODA_FOCUS** bu bit denetimi kazanır veya giriş odağı kaybettiğinde ayarlanır. **İtemState** denetimi odağa sahip olup olmadığını belirlemek için üye işaretlenmelidir.  
  
- **ODA_SELECT** yalnızca seçim durumu değiştiğinde bu bit ayarlanır. **İtemState** üye, yeni seçim durumu belirlemek için işaretlenmelidir.  
  
 *itemState*  
 Geçerli çizim eylem gerçekleştirildikten sonra öğesi visual durumunu belirtir. Diğer bir deyişle, menü öğesi durumunda olduğu olmasını görünüyorsa, durum bayrağı **ODS_GRAYED** ayarlanır. Durumu bayrakları aşağıdaki gibidir:  
  
- **ODS_CHECKED** menü öğesi denetlenecek ise bu bit ayarlanır. Bu bit yalnızca menüde kullanılır.  
  
- **ODS_DISABLED** öğesi devre dışı olarak çizilecek ise bu bit ayarlanır.  
  
- **ODS_FOCUS** odak öğe girişi değilse bu bit ayarlanır.  
  
- **ODS_GRAYED** öğe soluk ise bu bit ayarlanır. Bu bit yalnızca menüde kullanılır.  
  
- **ODS_SELECTED** öğenin durumunu seçtiyseniz bu bit ayarlanır.  
  
- **ODS_COMBOBOXEDIT** çizim ownerdrawn birleşik giriş kutusu seçim alanında (düzenleme denetimi) gerçekleşir.  
  
- **ODS_DEFAULT** varsayılan öğe öğedir.  
  
 `hwndItem`  
 Birleşik giriş kutuları, liste kutuları ve düğmeleri için Denetim pencere tanıtıcısı belirtir. Menü tanıtıcısı belirtir (`HMENU`) menü öğesi içerir.  
  
 `hDC`  
 Bir cihaz bağlamı tanımlar. Bu cihaz bağlamı denetimindeki çizim işlemleri gerçekleştirirken kullanılması gerekir.  
  
 *rcItem*  
 Dikdörtgene tarafından belirtilen cihaz bağlamı `hDC` çizilecek denetimin sınırları tanımlar üye. Windows otomatik olarak birleşik giriş kutuları, liste kutuları ve düğmeleri için cihaz bağlamda sahibi çizer herhangi bir şey küçük, ancak menü öğeleri küçük değil. Menü öğeleri çizerken sahibi tarafından tanımlanan dikdörtgenin sınırlarının dışında çekmek gerekir değil **rcItem** üyesi.  
  
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
  
## <a name="remarks"></a>Açıklamalar  
 Sahip tarafından çizilmiş denetim veya menü öğesini sahibi pencerenin bu yapı işaretçi alır `lParam` parametresinin `WM_DRAWITEM` ileti.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

