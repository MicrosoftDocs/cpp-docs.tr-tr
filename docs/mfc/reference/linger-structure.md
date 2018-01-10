---
title: "LINGER yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LINGER
dev_langs: C++
helpviewer_keywords: LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 747a793e64e7f3ec1e76f383a807f15c67417a83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linger-structure"></a>LINGER Yapısı
`LINGER` Yapısını işlemek için kullanılan **SO_LINGER** ve **SO_DONTLINGER** seçeneklerini `CAsyncSocket::GetSockOpt`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Ayarı **SO_DONTLINGER** seçeneği engeller üye işlevini engelleme **Kapat** gönderilecek gönderilmemiş verileri beklenirken. Bu seçeneğin ayarlanması eşdeğerdir ayarına **SO_LINGER** ile **l_onoff** 0 olarak ayarlayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winsock2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

