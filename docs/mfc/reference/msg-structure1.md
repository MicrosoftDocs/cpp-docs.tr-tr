---
title: MSG yapısı1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe629c2f279b6b258f4824229490f7b72b4ce4d
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338818"
---
# <a name="msg-structure1"></a>MSG yapısı1
`MSG` Yapısı, bir iş parçacığının ileti kuyruğundan ileti bilgileri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagMSG {     // msg    
    HWND hwnd;  
    UINT message;  
    WPARAM wParam;  
    LPARAM lParam;  
    DWORD time;  
    POINT pt;  
} MSG;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *HWND*  
 Pencere yordamı olan iletiyi alır penceresi tanımlar.  
  
 *message*  
 İleti sayısını belirtir.  
  
 *wParam*  
 İleti hakkında ek bilgi belirtir. Tam anlamı değerine bağlıdır `message` üyesi.  
  
 *lParam*  
 İleti hakkında ek bilgi belirtir. Tam anlamı değerine bağlıdır `message` üyesi.  
  
 *saat*  
 Başlangıçtan iletinin gönderildiği saati belirtir.  
  
 *PT*  
 İletinin gönderildiği sırada ekran koordinatlarında imleç konumu belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

