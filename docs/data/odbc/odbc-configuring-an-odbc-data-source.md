---
title: "ODBC: ODBC veri kaynağını yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8e347683a079227226513ce82f9623860e826228
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC: ODBC Veri Kaynağını Yapılandırma
Kullanılacak bir [veri kaynağı](../../data/odbc/data-source-odbc.md) geliştirdiğinizde uygulamayla yapılandırmak için ODBC Yöneticisi kullanmanız gerekir. ODBC Yöneticisi kullanılabilir veri kaynaklarını ve bunların bağlantı bilgileri Windows kayıt defterinde izler. Eklemek, değiştirmek ve veri kaynaklarını silmek için ODBC Yöneticisi'ni kullanma **veri kaynakları** iletişim kutusu ekleyin ve ODBC sürücüleri silin.  
  
> [!NOTE]
>  Bu bilgiler ODBC erişimi için MFC veri erişim nesnesi (DAO) sınıfları kullandığınızda ve MFC ODBC sınıfları kullandığınızda geçerlidir.  
  
 ODBC Yöneticisi Microsoft Foundation sınıfları (MFC) Kitaplığı veritabanı desteği ile birlikte otomatik olarak yüklenir. ODBC Yöneticisi programı hakkında daha fazla bilgi için bkz: [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md) ve çevrimiçi ODBC API başvuru Yardım sistemi.  
  
 MFC veritabanı uygulamaları için ODBC Kurulum ve yönetim programları yazma hakkında bilgi için[Teknik Not 48](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC temelleri](../../data/odbc/odbc-basics.md)   
 [ODBC: ODBC API işlevlerini doğrudan çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)