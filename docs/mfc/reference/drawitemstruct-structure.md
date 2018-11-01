---
title: DRAWITEMSTRUCT Yapısı
ms.date: 11/04/2016
f1_keywords:
- DRAWITEMSTRUCT
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
ms.openlocfilehash: 9c5bfc12bd371761682102dad6d7bcb75ef44151
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624438"
---
# <a name="drawitemstruct-structure"></a>DRAWITEMSTRUCT Yapısı

`DRAWITEMSTRUCT` Yapısı, sahip penceresine bir sahip tarafından çizilmiş denetimi ya da menü öğesi boyama nasıl dağıtılacağını belirlemenin olmalıdır bilgi sağlar.

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

*CtlType*<br/>
Denetim türü. Denetim tipleri için değerler aşağıdaki gibidir:

- ODT_BUTTON çizimli düğmesi

- ODT_COMBOBOX çizimli birleşik giriş kutusu

- ODT_LISTBOX sahip tarafından çizilmiş liste kutusu

- Sahip tarafından çizilmiş ODT_MENU menüsü

- ODT_LISTVIEW liste görünümü denetimi

- Sahip tarafından çizilmiş statik denetimi ODT_STATIC

- ODT_TAB sekme denetimi

*CtlID*<br/>
Birleşik giriş kutusu, liste kutusu ve düğme denetiminin kimliği. Bu üye için bir menü kullanılmaz.

*öğe kimliği*<br/>
Bir menü veya birleşik giriş kutusu ya da liste kutusu öğenin dizinini menü öğesi kimliği. Bir boş liste kutusu veya açılan kutu için bu üye tarafından belirtilen koordinatlarda odak dikdörtgen çizmek uygulama izin veren negatif bir değer olan `rcItem` üye denetiminde öğe olsa bile. Kullanıcı, bu nedenle birleşik giriş kutusu ve liste kutusu Girintiyi aldığını gösterilebilir. Ayar bitleri `itemAction` üye dikdörtgen birleşik giriş kutusu ve liste kutusu odağı giriş ancak olarak çizilecek olup olmadığını belirler.

*itemAction*<br/>
Gerekli bir çizim eylemi tanımlar. Bu, bir veya daha fazla aşağıdaki bit olacaktır:

- Tüm denetim çizilmesi gerektiğinde ODA_DRAWENTIRE bu bit ayarlanır.

- Denetim kazanır veya giriş odağını kaybediyor ODA_FOCUS bu bit ayarlanır. `itemState` Üye denetim odağa sahip olup olmadığını belirlemek için işaretlenmelidir.

- Seçim durumu değiştiğinde ODA_SELECT bu bit ayarlanır. `itemState` Üyesi yeni seçim durumu belirlemek için işaretlenmelidir.

*itemState*<br/>
Geçerli çizim eylem gerçekleştirildikten sonra görsel durum öğesi belirtir. Diğer bir deyişle, bir menü öğesi soluk ise, durumu bayrağı ODS_GRAYED ayarlanır. Durumu bayrakları aşağıdaki gibidir:

- Menü öğesinin denetlenmesi için ise ODS_CHECKED bu bit ayarlanır. Bu bit yalnızca menüde kullanılır.

- Öğe devre dışı olarak çizilecek ise ODS_DISABLED bu bit ayarlanır.

- Öğenin odak giriş ODS_FOCUS bu bit ayarlanır.

- Öğe soluk ise ODS_GRAYED bu bit ayarlanır. Bu bit yalnızca menüde kullanılır.

- Öğenin durumu seçtiyseniz ODS_SELECTED bu bit ayarlanır.

- ODS_COMBOBOXEDIT çizim bir ownerdrawn birleşik giriş kutusu seçim alanında (düzenleme denetimi) gerçekleşir.

- Varsayılan öğe ODS_DEFAULT öğesi değil.

*hwndItem*<br/>
Birleşik giriş kutuları, liste kutuları ve düğmeler için denetimin pencere tutucu belirtir. Öğesi menülerini için içeren (HMENU) menü tanıtıcısı belirtir.

*hDC*<br/>
Bir cihaz bağlamı tanımlar. Bu cihaz bağlamı denetiminde çizim işlemlerini gerçekleştirirken kullanılması gerekir.

*rcItem*<br/>
Tarafından belirtilen cihaz bağlamında bir dikdörtgen *hDC* çizilecek denetimin sınırlarını tanımlar üyesi. Windows birleşik giriş kutuları, liste kutuları ve düğmeler için cihaz bağlamı sahibi çizer herhangi bir şey otomatik küçük ancak menü öğeleri küçük değil. Menü öğesi çizim, sahibi tarafından tanımlanan dikdörtgen sınırları dışında çizin gerekir değil `rcItem` üyesi.

*ItemData*<br/>
Birleşik giriş kutusu veya liste kutusunda, bu üye liste kutusuna aşağıdakilerden biri tarafından geçirilen değeri içerir:

- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)

- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)

- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)

- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)

Bir menü için bu üye menüsüne aşağıdakilerden biri tarafından geçirilen değeri içerir:

- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)

- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)

- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)

## <a name="remarks"></a>Açıklamalar

Sahip tarafından çizilmiş denetimi ya da menü öğesi, sahip penceresine bir işaretçi bu yapı için alan *lParam* WM_DRAWITEM iletisinin parametresi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

