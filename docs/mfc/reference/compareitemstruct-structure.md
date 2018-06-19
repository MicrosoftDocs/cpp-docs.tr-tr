---
title: COMPAREITEMSTRUCT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a94d39c6b6c256444cd2850f7e55a7e4b87f6d7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368637"
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT Yapısı
`COMPAREITEMSTRUCT` Tanımlayıcıları ve bir sıralanmış, sahip tarafından çizilmiş liste kutusu veya açılan kutu iki öğe için uygulama tarafından sağlanan veri yapısı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CtlType`  
 **ODT_LISTBOX** (sahip çizim liste kutusu belirtir) veya **ODT_COMBOBOX** (sahip çizim birleşik giriş kutusu belirtir).  
  
 `CtlID`  
 Liste kutusu veya birleşik giriş kutusu denetimi kimliği.  
  
 `hwndItem`  
 Denetimin pencere tanıtıcısı.  
  
 *itemID1*  
 Liste kutusu veya birleşik giriş kutusu karşılaştırılan ilk öğenin dizini.  
  
 *itemData1*  
 Karşılaştırılan ilk öğe için uygulama tarafından sağlanan verileri. Bu değer açılan veya liste kutusunu eklenen öğe çağrısı geçirildi.  
  
 *itemID2*  
 Liste kutusu veya açılan kutu karşılaştırılan ikinci öğenin dizini.  
  
 *itemData2*  
 Karşılaştırılan ikinci öğe için uygulama tarafından sağlanan verileri. Bu değer açılan veya liste kutusunu eklenen öğe çağrısı geçirildi.  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir uygulama bir sahip tarafından çizilmiş liste kutusu için yeni bir öğe ekler veya birleşik giriş kutusu oluşturulan ile **CBS_SORT** veya **LBS_SORT** stili Windows gönderir, sahibi bir `WM_COMPAREITEM` ileti. `lParam` İletinin parametre içeren uzun bir işaretçi bir `COMPAREITEMSTRUCT` yapısı. İletiyi alır almaz, sahibi iki öğeyi karşılaştırır ve hangi öğesinin önce diğer sıralar belirten bir değer döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

