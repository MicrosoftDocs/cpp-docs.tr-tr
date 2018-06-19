---
title: 'ODBC: ODBC veri kaynağını yapılandırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 93b2158005b7cd31fc6a3710812d54a3968ee014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089158"
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