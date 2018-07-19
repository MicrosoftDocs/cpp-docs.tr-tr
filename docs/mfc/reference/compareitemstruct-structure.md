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
ms.openlocfilehash: 6c42f356cb323bb7690b6c39b1fc7bd9ce0485f3
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850595"
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT Yapısı
`COMPAREITEMSTRUCT` Tanımlayıcıları ve iki sıralanmış, özelleştirilmiş olarak çizilen bir liste kutusu veya birleşik giriş kutusu öğeleri için uygulama tarafından sağlanan veri yapısı sağlar.  
  
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
 *CtlType*  
 (Bu bir sahip çizim liste kutusu belirtir) ODT_LISTBOX veya ODT_COMBOBOX (Bu bir özelleştirilmiş çizimli birleşik giriş kutusu belirtir).  
  
 *CtlID*  
 Birleşik giriş kutusu ve liste kutusu denetimi kimliği.  
  
 *hwndItem*  
 Denetimin pencere tanıtıcısı.  
  
 *itemID1*  
 Karşılaştırılan birleşik giriş kutusu ve liste kutusu ilk öğenin dizini.  
  
 *itemData1*  
 Karşılaştırılan ilk öğe için uygulama tarafından sağlanan verileri. Bu değer birleşik veya liste kutusuna eklenen öğe çağrı geçirildi.  
  
 *itemID2*  
 Liste kutusu veya açılan kutusu karşılaştırılan ikinci öğenin dizini.  
  
 *itemData2*  
 Karşılaştırılan ikinci öğe için uygulama tarafından sağlanan verileri. Bu değer birleşik veya liste kutusuna eklenen öğe çağrı geçirildi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama, bir sahip tarafından çizilmiş liste kutusu ya da birleşik giriş kutusu CBS_SORT veya LBS_SORT stil ile oluşturulan yeni bir öğe ekler. her Windows sahibi WM_COMPAREITEM ileti gönderir. *LParam* iletinin parametresi uzun bir işaretçi içeren bir `COMPAREITEMSTRUCT` yapısı. İletiyi alır almaz, sahibi iki öğeyi karşılaştıran ve hangi öğe diğerinden önce sıralar gösteren bir değer döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

