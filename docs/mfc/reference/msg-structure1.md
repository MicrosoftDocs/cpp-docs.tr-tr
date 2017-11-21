---
title: MSG Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MSG
dev_langs: C++
helpviewer_keywords: MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b856ea17e4542bee68d55b22069e559592199939
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="msg-structure1"></a>MSG Structure1
`MSG` Yapısı bir iş parçacığının ileti kuyruğundan ileti bilgilerini içerir.  
  
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
 İleti, pencere yordamı alır penceresi tanımlar.  
  
 `message`  
 İleti sayısını belirtir.  
  
 `wParam`  
 İletiyle ilgili ayrıntılı bilgileri belirtir. Tam anlamını değerine bağlıdır **ileti** üyesi.  
  
 `lParam`  
 İletiyle ilgili ayrıntılı bilgileri belirtir. Tam anlamını değerine bağlıdır **ileti** üyesi.  
  
 `time`  
 Hangi ileti deftere süreyi belirtir.  
  
 `pt`  
 İleti amaçlı ekran koordinatları, imleç konumu belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

