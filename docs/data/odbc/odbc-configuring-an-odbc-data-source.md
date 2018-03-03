---
title: "ODBC: ODBC veri kaynağını yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5bf7d2b1708e74d50adb417f531c741a467ed889
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC: ODBC Veri Kaynağını Yapılandırma
Kullanılacak bir [veri kaynağı](../../data/odbc/data-source-odbc.md) geliştirdiğinizde uygulamayla yapılandırmak için ODBC Yöneticisi kullanmanız gerekir. ODBC Yöneticisi kullanılabilir veri kaynaklarını ve bunların bağlantı bilgileri Windows kayıt defterinde izler. Eklemek, değiştirmek ve veri kaynaklarını silmek için ODBC Yöneticisi'ni kullanma **veri kaynakları** iletişim kutusu ekleyin ve ODBC sürücüleri silin.  
  
> [!NOTE]
>  Bu bilgiler ODBC erişimi için MFC veri erişim nesnesi (DAO) sınıfları kullandığınızda ve MFC ODBC sınıfları kullandığınızda geçerlidir.  
  
 ODBC Yöneticisi Microsoft Foundation sınıfları (MFC) Kitaplığı veritabanı desteği ile birlikte otomatik olarak yüklenir. ODBC Yöneticisi programı hakkında daha fazla bilgi için bkz: [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md) ve çevrimiçi ODBC API başvuru Yardım sistemi.  
  
 MFC veritabanı uygulamaları için ODBC Kurulum ve yönetim programları yazma hakkında bilgi için[Teknik Not 48](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC temelleri](../../data/odbc/odbc-basics.md)   
 [ODBC: ODBC API İşlevlerini Doğrudan Çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)