---
title: CDataConnection::OpenNewSession | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
dev_langs: C++
helpviewer_keywords: OpenNewSession method
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 733834dcb7df6addd9b3953019b367f9e12951dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionopennewsession"></a>CDataConnection::OpenNewSession
Geçerli bağlantı nesnesinin veri kaynağı kullanarak yeni bir oturum açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT OpenNewSession(   
   CSession & session    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `session`  
 [Giriş/Çıkış] Yeni bir oturum nesnesi referansı.  
  
 **Açıklamalar**  
 Yeni oturum kendi üst öğesi olarak geçerli bağlantı nesnesinin içerdiği veri kaynağı nesnesi kullanır ve tüm veri kaynağını aynı bilgilerine erişebilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataConnection sınıfı](../../data/oledb/cdataconnection-class.md)