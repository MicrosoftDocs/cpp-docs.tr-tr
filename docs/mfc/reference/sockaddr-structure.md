---
title: "SOCKADDR yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 55b310ec83aae35c7386d61849663752811651d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

