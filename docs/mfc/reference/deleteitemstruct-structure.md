---
title: DELETEITEMSTRUCT Yapısı
ms.date: 11/04/2016
f1_keywords:
- DELETEITEMSTRUCT
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
ms.openlocfilehash: dd1f48fd584016dab740bc8a6bd05ff3b756e41b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486891"
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT Yapısı

`DELETEITEMSTRUCT` Silinmiş bir sahip tarafından çizilmiş liste kutusu ya da birleşik giriş kutusu öğeyi yapısını açıklar.

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

*CtlType*<br/>
ODT_LISTBOX (bir sahip tarafından çizilmiş liste kutusu) veya ODT_COMBOBOX (çizimli birleşik giriş kutusu) belirtir.

*CtlID*<br/>
Birleşik giriş kutusu ve liste kutusu tanımlayıcısını belirtir.

*öğe kimliği*<br/>
Liste kutusu veya açılan kutuda kaldırılmakta olan öğenin dizinini belirtir.

*hwndItem*<br/>
Denetimi tanımlar.

*ItemData*<br/>
Uygulama tanımlı veri öğesi için belirtir. Bu değer denetim tarafından geçirilen *lParam* parametresi iletisinin liste kutusu veya açılan kutusu öğe ekler.

## <a name="remarks"></a>Açıklamalar

Liste kutusu ya da birleşik giriş kutusu veya birleşik giriş kutusu ve liste kutusu yok edildiğinde bir öğe kaldırıldığında, Windows silinmiş her öğenin sahibi WM_DELETEITEM ileti gönderir. *LParam* iletinin parametresi bu yapıya bir işaretçi içerir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)

