---
title: "Sockaddr_ın yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e5350e48570a564361328e7b666a1cbb976221a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN Yapısı
Internet adresi ailesindeki `SOCKADDR_IN` yapısı yuva bağlantı kurmak için bir yerel veya uzak uç noktası adresi belirtmek için Windows Sockets tarafından kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct sockaddr_in{  
    short sin_family;  
    unsigned short sin_port;  
struct in_addr sin_addr;  
    char sin_zero[8];  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sin_family*  
 Adres ailesi (olmalıdır **AF_INET**).  
  
 *sin_port*  
 IP bağlantı noktası.  
  
 *sin_addr*  
 IP adresi.  
  
 *sin_zero*  
 Aynı boyutta yapısı yapmak için doldurma `SOCKADDR`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu biçimidir `SOCKADDR` Internet adresi ailesine belirli yapısı ve için cast `SOCKADDR`.  
  
 Bu yapı IP adresi bileşeninin türünde **IN_ADDR**. **IN_ADDR** yapısı Windows Sockets üstbilgi dosyası WINSOCK tanımlanır. H şekilde:  
  
```  
struct in_addr {
    union {
        struct {  
            unsigned char s_b1, s_b2, s_b3, s_b4;  
        } S_un_b;  
        struct {  
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winsock2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR Yapısı](../../mfc/reference/sockaddr-structure.md)
