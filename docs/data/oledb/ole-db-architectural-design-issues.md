---
title: "OLE DB Mimari Tasarım sorunları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b894ec1cbd227663d46e98e523ffe8c1c5d84475
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB Mimari Tasarım Sorunları
OLE DB uygulamanıza başlamadan önce aşağıdaki sorunları dikkate:  
  
 **Hangi programlama uygulamasını OLE DB uygulamanızı yazmak için kullanacak mısınız?**  
 Microsoft, bunu yapmanın birkaç kitaplıkları sunar: OLE DB Şablon kitaplığı, OLE DB öznitelikleri ve OLE DB SDK işlenmemiş OLE DB arabirimleri. Ayrıca, programınızı yazmanıza yardımcı olacak sihirbazları vardır. Bu uygulamalar açıklanan [OLE DB Şablonları, öznitelikler ve diğer uygulamalar](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).  
  
 **Kendi sağlayıcınızı gerekiyor mu?**  
 Çoğu geliştirici, kendi sağlayıcınızı yazmanız gerekmez. Microsoft, birkaç sağlayıcı sağlar. Bir veri bağlantısı (örneğin projenize ATL OLE DB Tüketici Sihirbazı'nı kullanarak bir tüketici eklediğinizde,), oluşturduğunuz her **veri bağlantısı özelliklerini** iletişim kutusu sisteminize kayıtlı tüm kullanılabilir sağlayıcılar listeler. Bu sağlayıcılardan biri kendi veri saklama ve veri erişim uygulamanız için uygun olup olmadığını yapmak için kolay bunlardan birini şeydir. Ancak, veri deponuza Bu kategorilerden birini sığmadığında kendi sağlayıcınızı oluşturmanız gerekir. Sağlayıcılar oluşturma hakkında daha fazla bilgi için bkz: [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **Hangi düzeyde desteği için tüketici gerekiyor mu?**  
 Bazı tüketiciler çok temel olabilir; Başkalarının çok karmaşık olabilir ancak. OLE DB nesneleri işlevselliğini özellikleri ile belirtilir. Bir sağlayıcı oluşturmak için bir tüketici veya veritabanı sağlayıcısını Sihirbazı'nı oluşturmak için ATL OLE DB Tüketici Sihirbazı'nı kullandığınızda, standart bir işlevler kümesi vermenizi uygun nesne özelliklerini ayarlar. Sihirbaz tarafından oluşturulan tüketici ya da sağlayıcı sınıfları bunları yapmak için gereken her şeyi desteklemez, ancak bu sınıfların arabirimleri başvurmak ihtiyacınız [OLE DB şablonları kitaplığı](../../data/oledb/ole-db-templates.md). Bu arabirimleri bunları kullanımını sizin için daha kolay hale getirmek için ek uygulama sağlama ham OLE DB arabirimleri sarılır.  
  
 Bir satır kümesindeki veriler güncelleştirmek istiyor ancak Tüketici Sihirbazı ile oluşturduğunuzda bu belirtmek, örneğin, işlevselliği olaydan sonra ayarlayarak belirleyebileceğiniz **DBPROP_IRowsetChange** ve  **DBPROP_UPDATABILITY** komut nesne üzerindeki özellikleri. Ardından, satır kümesi oluşturduğunuzda, var. `IRowsetChange` arabirimi.  
  
 **Başka bir veri erişim teknolojisi (ADO, ODBC ve DAO) kullanarak eski kod var mı?**  
 Tüm durumlarda kapsayan (OLE DB bileşenleriyle ADO bileşenleri kullanma ve OLE DB için ODBC kodu geçirme) gibi teknolojileri olası birleşimlerini verildiğinde, Visual C++ belge kapsamında değildir. Ancak, çeşitli senaryolarda kapsayan birçok makale aşağıdaki Microsoft Web sitelerinde kullanılabilir:  
  
-   [Microsoft Yardım ve Destek](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Microsoft Data Access teknik makaleleri genel bakış](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Visual Studio Çözüm Merkezi](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Microsoft.com Ara](http://search.microsoft.com/)  
  
 Bir arama gerçekleştirdiğinizde, senaryonuza en uygun bir anahtar sözcükleri birleşimi girin; Örneğin: bir OLE DB sağlayıcısı ile ADO nesneleri kullanıyorsanız, bir Boolean Arama deneyin ile **ADO ve "OLE DB"**. Eski DAO kodunu ODBC'ye geçirmek istediyseniz, "tüm sözcükleri" seçin ve dizeler gibi belirtin **geçirme DAO**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)