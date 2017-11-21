---
title: "SOCKADDR yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SOCKADDR
dev_langs: C++
helpviewer_keywords: SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ce8207ea1e8f82b635029861493262a5f6237f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="sockaddr-structure"></a>SOCKADDR Yapısı
`SOCKADDR` Yapısı Windows Sockets iletişime katılan bir makine için bir Internet Protokolü (IP) adresi depolamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sa_family*  
 Yuva Adres ailesi.  
  
 *sa_data*  
 Tüm farklı yuva adresi yapıları en büyük boyutu.  
  
## <a name="remarks"></a>Açıklamalar  
 Microsoft TCP/IP'yi yuva Geliştirme Seti yalnızca Internet adresi etki alanlarını destekler. Gerçekte bir adresi her kısmı için değerleri doldurmak için kullandığınız `SOCKADDR_IN` özellikle bu adresi biçimi için veri yapısı. `SOCKADDR` Ve `SOCKADDR_IN` veri yapılarını olan aynı boyutta. Yalnızca iki yapı türleri arasında geçiş yapmak için atayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winsock2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Sockaddr_ın yapısı](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)

