---
title: "ODBC Yöneticisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- installing ODBC
- ODBC data sources [C++], ODBC Administrator
- ODBC drivers [C++], installing
- ODBC [C++], ODBC Administrator
- Administrator in ODBC
- administration ODBC Administrator
- ODBC Administrator [C++]
- drivers [C++], ODBC
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 834825b38eb8d5c81752dfed85f44202fbce3299
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-administrator"></a>ODBC Yöneticisi
ODBC Yöneticisi kaydeder ve yapılandırır [veri kaynaklarını](../../data/odbc/data-source-odbc.md) , kullanılabilir yerel olarak ya da bir ağ üzerinden. Sihirbazlar uygulamalarınızda kullanıcılarınızın veri kaynaklarına bağlayan kod oluşturmak için ODBC Yöneticisi tarafından sağlanan bilgileri kullanın.  
  
 MFC ODBC sınıfları veya MFC veri erişim nesnesi (DAO) sınıfları ile kullanmak için bir ODBC veri kaynağı ayarlamak için öncelikle kaydetmeniz ve veri kaynağı yapılandırın. ODBC Yöneticisi eklemek ve veri kaynaklarını kaldırmak için kullanın. ODBC sürücüsü bağlı olarak yeni veri kaynakları da oluşturabilirsiniz.  
  
 ODBC Yöneticisi Kurulum sırasında yüklenir. Seçerseniz **özel** yükleme ve herhangi bir ODBC sürücü seçmediyseniz **veritabanı seçenekleri** iletişim kutusunda, gerekli dosyaları yüklemek için Kur'u yeniden çalıştırmanız gerekir.  
  
 Kurulum sırasında yüklemek istediğiniz ODBC sürücüleri seçin. Daha sonra Visual C++ Kurulum programını kullanarak Visual C++ ile birlikte ek sürücüler yükleyebilirsiniz.  
  
 Visual C++ ile gönderilen ODBC sürücüleri yüklemek istiyorsanız, sürücüyle Kurulum programı çalıştırmanız gerekir.  
  
#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>Visual C++ ile birlikte gelen ODBC sürücüleri yüklemek için  
  
1.  Kurulum, Visual C++ dağıtım CD'den çalıştırılabilecek.  
  
     Açılan iletişim kutusudur Kurulum programının görüntülenir.  
  
2.  Tıklatın **sonraki** ulaşana kadar her iletişim kutusunda **yükleme seçenekleri** iletişim kutusu. Seçin **özel**ve ardından `Next`.  
  
3.  Tüm onay kutularını temizleyin **Microsoft Visual C++ Kurulumu** iletişim kutusu dışındaki **veritabanı seçenekleri** onay kutusunu işaretleyin ve ardından **ayrıntıları** görüntülenecek**Veritabanı seçenekleri** iletişim kutusu.  
  
4.  Clear **Microsoft Veri erişim nesneleri** onay kutusu, select **Microsoft ODBC sürücüleri** onay kutusunu işaretleyin ve ardından **ayrıntıları**.  
  
     **Microsoft ODBC sürücüleri** iletişim kutusu görüntülenir.  
  
5.  Yükleyin ve ardından istediğiniz sürücüleri seçin **Tamam** iki kez.  
  
6.  Tıklatın **sonraki** yüklemeyi başlatmak için kalan iletişim kutularında. Yükleme tamamlandığında, Kurulum bunu size bildirir.  
  
 Sürücüleri yüklü olduğunda veri kaynağını ODBC Yöneticisi kullanarak yapılandırabilirsiniz. ODBC simgesini Denetim Masası'nda bulabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)