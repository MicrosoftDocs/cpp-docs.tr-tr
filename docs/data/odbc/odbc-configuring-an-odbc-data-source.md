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
ms.openlocfilehash: db65e27feee5ac8001cb25592e695831c431742b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104524"
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC: ODBC Veri Kaynağını Yapılandırma

Kullanılacak bir [veri kaynağı](../../data/odbc/data-source-odbc.md) geliştirdiğinizde, bir uygulama ile yapılandırmak için ODBC Yöneticisi kullanmanız gerekir. ODBC Yöneticisi kullanılabilir veri kaynakları ve bağlantı bilgilerini Windows kayıt defterinde izler. Eklemek, değiştirmek ve veri kaynakları silmek için ODBC Yöneticisi'ni kullanma **veri kaynakları** iletişim kutusu ekleyin ve ODBC sürücüleri silin.  
  
> [!NOTE]
>  Bu bilgiler, veri erişim nesnesi (DAO) MFC sınıfları için ODBC erişim kullandığınızda ve MFC ODBC sınıfları kullanırken geçerlidir.  
  
ODBC Yöneticisi, Microsoft Foundation Classes (MFC) Kitaplığı veritabanı desteği ile birlikte otomatik olarak yüklenir. ODBC Yöneticisi programı hakkında daha fazla bilgi için bkz. [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md) ve çevrimiçi ODBC API başvuru Yardım sistemi.  
  
MFC veritabanı uygulamaları için ODBC Kurulum ve yönetim programları yazma hakkında daha fazla bilgi için[Teknik Not 48](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[ODBC Temelleri](../../data/odbc/odbc-basics.md)<br/>
[ODBC: ODBC API İşlevlerini Doğrudan Çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)