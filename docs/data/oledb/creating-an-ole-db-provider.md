---
title: OLE DB Sağlayıcısı Oluşturma
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: b6e59dba375e78878d13a6014ce75edf2a21758b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611204"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB Sağlayıcısı Oluşturma

Bir OLE DB sağlayıcısı oluşturmak için önerilen yöntem, ATL COM projesini ve sağlayıcı oluşturup ardından OLE DB Şablonları kullanarak dosyaları değiştirmek için sihirbazları kullanmaktır. Sağlayıcınız özelleştirme gibi istenmeyen özellikleri açıklaması ve isteğe bağlı arabirimler.

Temel adımlar aşağıdaki gibidir:

1. Kullanım **ATL projesi Sihirbazı** temel proje dosyaları oluşturmak için ve **ATL OLEDB Sağlayıcısı Sihirbazı** sağlayıcısı oluşturmak için (seçin **ATL OLEDB Sağlayıcısı** gelen**Yüklü** > **Visual C++** > **ATL** klasöründe **Yeni Öğe Ekle**).

   > [!NOTE]
   > Proje eklemeden önce MFC desteği içermelidir bir **ATL OLEDB Sağlayıcısı**.

1. Kodda değişiklik `Execute` yönteminde [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md). Bir örnek için bkz. [okuma dizeleri içine bir OLE DB sağlayıcısı](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

1. Özellik eşlemeleri içinde düzenleme [CustomDS.h](cmyprovidersource-myproviderds-h.md), [CustomSess.h](cmyprovidersession-myprovidersess-h.md), ve [CustomRS.h](cmyproviderrowset-myproviderrs-h.md). Sihirbaz bir sağlayıcının uygulayabileceği tüm özellikleri içeren özellik eşlemeleri oluşturur. Özellik eşlemeleri üzerinden giderek kaldırabilir veya yorum sağlayıcınız destek gerekmez özellikleri.

1. Bulunabilir PROVIDER_COLUMN_MAP güncelleştirme [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md). Bir örnek için bkz. [depolama dizeleri, OLE DB sağlayıcısı](../../data/oledb/storing-strings-in-the-ole-db-provider.md).

1. Sağlayıcınızı test etmeye hazır olduğunuzda, sağlayıcı bir sağlayıcı numaralandırmada bulunamadı deneyerek test edebilirsiniz. Bir sabit listesinde bir sağlayıcı bulur test kod örnekleri için bkz. [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) ve [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) örnekleri veya örnekte [bir Basit Tüketici Uygulama](../../data/oledb/implementing-a-simple-consumer.md).

1. İstediğiniz desteklenecek ek arabirimleri ekleyin. Bir örnek için bkz. [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).

   > [!NOTE]
   > Varsayılan olarak, sihirbaz OLE DB düzeyi 0 uyumlu bir kod oluşturur. Uygulama düzeyi 0 uyumlu kalmasını sağlamak için herhangi bir sihirbazın ürettiği arabirimleri koddan kaldırmayın.

## <a name="see-also"></a>Ayrıca Bkz.

[CatDB örnek: Veri kaynak şema tarayıcı](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[DBVIEWER örneği: Veritabanı tarayıcı](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
