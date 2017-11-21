---
title: "OLE DB sağlayıcısı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 07060be0c14adb4d509c23ab88914de4494e6862
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-an-ole-db-provider"></a>OLE DB Sağlayıcısı Oluşturma
OLE DB sağlayıcısı oluşturmak için önerilen yöntem ATL COM projesini ve sağlayıcı oluşturmak ve OLE DB Şablonları kullanarak dosyaları değiştirmek için sihirbazlar kullanmaktır. Sağlayıcınız özelleştirme gibi istenmeyen özellikleri açıklaması ve isteğe bağlı arabirimler ekleyin.  
  
 Temel adımlar aşağıdaki gibidir:  
  
1.  Temel proje dosyalarını ve ATL OLE DB sağlayıcısı sağlayıcısı oluşturmak için Sihirbazı oluşturmak için ATL Proje Sihirbazı'nı kullanın (seçin **ATL OLE DB sağlayıcısı** Visual C++ klasöründen **sınıfı Ekle**).  
  
2.  Kodda değişiklik `Execute` CMyProviderRS.h yöntemi. Bir örnek için bkz: [okuma dizeleri içine bir OLE DB sağlayıcısı](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  Özellik eşlemeleri MyProviderDS.h, MyProviderSess.h ve MyProviderRS.h düzenleyin. Sihirbazın bir sağlayıcının uygulayabileceği tüm özellikleri içeren bir özellik eşlemesi oluşturur. Özellik eşlemeleri üzerinden giderek kaldırabilir veya yorum sağlayıcınız destek gerekmez özellikleri çıkışı.  
  
4.  MyProviderRS.h öğesinde bulunan PROVIDER_COLUMN_MAP güncelleştirin. Bir örnek için bkz: [depolama dizeler, OLE DB sağlayıcısı](../../data/oledb/storing-strings-in-the-ole-db-provider.md).  
  
5.  Sağlayıcınızı test etmeye hazır olduğunuzda, sağlayıcı bir sağlayıcı numaralandırmasında bulmaya çalışarak test edebilirsiniz. Bir sabit listesinde bir sağlayıcı bulur test kodu örnekleri için bkz: [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) ve [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) örnekleri veya örnekte [basit tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  İstediğiniz herhangi bir ilave arabirimi ekleyin. Bir örnek için bkz: [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  Varsayılan olarak, OLE DB düzey 0 uyumlu olan kod sihirbazları oluşturur. Uygulamanızı düzey 0 uyumlu kalmasını sağlamak için sihirbaz tarafından oluşturulan arabirimleri hiçbirini koddan kaldırmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)