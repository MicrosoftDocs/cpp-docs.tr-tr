---
description: 'Hakkında daha fazla bilgi edinin: OLE DB sağlayıcı oluşturma'
title: OLE DB Sağlayıcısı Oluşturma
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: 69dc9311a79f2739636633b2d268343a92d2dac9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287807"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB Sağlayıcısı Oluşturma

OLE DB sağlayıcısı oluşturmanın önerilen yolu, bir ATL COM projesi ve sağlayıcı oluşturmak için sihirbazları kullanmak ve ardından OLE DB şablonlarını kullanarak dosyaları değiştirmektir. Sağlayıcınızı özelleştirirken, istenmeyen özellikleri açıklama ekleyebilir ve isteğe bağlı arabirimler ekleyebilirsiniz.

Temel adımlar aşağıdaki gibidir:

1. Sağlayıcıyı oluşturmak için temel proje dosyalarını ve **ATL OLEDB Sağlayıcısı sihirbazını** oluşturmak için **atl Proje Sihirbazı** 'nı kullanın (    >    >  **Yeni öğe Ekle**' de yüklü Visual C++**ATL** klasöründen ATL OLEDB Sağlayıcısı ' nı seçin).

   > [!NOTE]
   > **ATL OLEDB Sağlayıcısı** eklemeden önce projenin MFC desteği içermesi gerekir.

1. `Execute` [Ccustomrowset (customrs. h)](cmyproviderrowset-myproviderrs-h.md)içindeki yöntemdeki kodu değiştirin. Bir örnek için bkz. [dizeleri OLE DB sağlayıcıya okuma](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

1. [Customds. h](cmyprovidersource-myproviderds-h.md), [customsess. h](cmyprovidersession-myprovidersess-h.md)ve [customrs. h](cmyproviderrowset-myproviderrs-h.md)içindeki özellik eşlemelerini düzenleyin. Sihirbaz, bir sağlayıcının uygulayabildiği tüm özellikleri içeren özellik eşlemeleri oluşturur. Özellik eşlemeleri ' ne gidin ve sağlayıcınızın desteklemek zorunda olmadığı özellikleri kaldırın veya not edin.

1. [Ccustomrowset (CustomRS. h)](cmyproviderrowset-myproviderrs-h.md)içinde bulunan PROVIDER_COLUMN_MAP güncelleştirin. Bir örnek için bkz. [OLE DB sağlayıcıda dizeleri depolama](../../data/oledb/storing-strings-in-the-ole-db-provider.md).

1. Sağlayıcınızı test etmeye hazırsanız sağlayıcıyı bir sağlayıcı numaralandırmasında bulmaya çalışırken test edebilirsiniz. Bir Numaralandırmadaki sağlayıcı bulan test kodu örnekleri için bkz. [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) ve [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) örnekleri veya [basit bir tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md)örneği.

1. İstediğiniz ek arabirimleri ekleyin. Bir örnek için bkz. [basit Read-Only sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).

   > [!NOTE]
   > Varsayılan olarak, sihirbazlar OLE DB düzey 0 uyumlu kod oluşturur. Uygulamanızın 0 düzeyine uyumlu kalmasını sağlamak için, koddan sihirbaz tarafından oluşturulan arabirimlerin hiçbirini kaldırmayın.

## <a name="see-also"></a>Ayrıca bkz.

[CatDB örneği: veri kaynağı şema tarayıcısı](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[DBViewer örneği: veritabanı tarayıcısı](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
