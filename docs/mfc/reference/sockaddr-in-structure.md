---
title: Sockaddr_ın yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aeb9e61f94ddd5f41ff3de26728c1fbe155f809d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373644"
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
