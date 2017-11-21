---
title: "COMPAREITEMSTRUCT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMPAREITEMSTRUCT
dev_langs: C++
helpviewer_keywords: COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ae9a4b8ab74ef4bf8b3a6445cf5d7faa8818c5a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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

