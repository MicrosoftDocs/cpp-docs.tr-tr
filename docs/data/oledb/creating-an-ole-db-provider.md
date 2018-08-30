---
title: OLE DB sağlayıcısı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 16d78d590201ea637dd6153edb40a1c6d89a82c0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210347"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB Sağlayıcısı Oluşturma
Bir OLE DB sağlayıcısı oluşturmak için önerilen yöntem, ATL COM projesini ve sağlayıcı oluşturup ardından OLE DB Şablonları kullanarak dosyaları değiştirmek için sihirbazları kullanmaktır. Sağlayıcınız özelleştirme gibi istenmeyen özellikleri açıklaması ve isteğe bağlı arabirimler.  
  
 Temel adımlar aşağıdaki gibidir:  
  
1.  ATL projesi Sihirbazı, temel proje dosyalarını ve ATL OLE DB sağlayıcısı sağlayıcısı oluşturmak için Sihirbazı oluşturmak için kullanın (seçin **ATL OLE DB sağlayıcısı** Visual C++ klasöründeki **sınıfı Ekle**).  
  
2.  Kodda değişiklik `Execute` CMyProviderRS.h yöntemi. Bir örnek için bkz. [okuma dizeleri içine bir OLE DB sağlayıcısı](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  MyProviderDS.h üzerinde MyProviderSess.h ve MyProviderRS.h özellik eşlemeleri düzenleyin. Sihirbaz bir sağlayıcının uygulayabileceği tüm özellikleri içeren özellik eşlemeleri oluşturur. Özellik eşlemeleri üzerinden giderek kaldırabilir veya yorum sağlayıcınız destek gerekmez özellikleri.  
  
4.  MyProviderRS.h içinde bulunabilir PROVIDER_COLUMN_MAP güncelleştirin. Bir örnek için bkz. [depolama dizeleri, OLE DB sağlayıcısı](../../data/oledb/storing-strings-in-the-ole-db-provider.md).  
  
5.  Sağlayıcınızı test etmeye hazır olduğunuzda, sağlayıcı bir sağlayıcı numaralandırmada bulunamadı deneyerek test edebilirsiniz. Bir sabit listesinde bir sağlayıcı bulur test kod örnekleri için bkz. [CATDB](https://github.com/Microsoft/VCSamples) ve [DBVIEWER](https://github.com/Microsoft/VCSamples) örnekleri veya örnekte [bir Basit Tüketici Uygulama](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  İstediğiniz desteklenecek ek arabirimleri ekleyin. Bir örnek için bkz. [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  Varsayılan olarak, sihirbaz OLE DB düzeyi 0 uyumlu bir kod oluşturur. Uygulama düzeyi 0 uyumlu kalmasını sağlamak için herhangi bir sihirbazın ürettiği arabirimleri koddan kaldırmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CATDB](https://github.com/Microsoft/VCSamples)   
 [DBVIEWER](https://github.com/Microsoft/VCSamples)