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
ms.openlocfilehash: fb5b9d710bef136893c66208480056f6bc6390d3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429714"
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


