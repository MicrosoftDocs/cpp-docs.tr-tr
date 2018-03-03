---
title: MSG Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b504f116dcbff7fa45e741ff9715070ee0c74583
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

