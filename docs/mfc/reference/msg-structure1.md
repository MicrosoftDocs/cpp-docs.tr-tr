---
title: MSG Structure1 | Microsoft Docs
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
ms.openlocfilehash: 41dbbcdd3404705a9ac7c6c7969a9ebeeb0238f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372263"
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

