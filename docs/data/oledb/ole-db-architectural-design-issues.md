---
title: OLE DB Mimari Tasarım sorunları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b0a5c568a774d0aed05d702454664e653989401
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676842"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB Mimari Tasarım Sorunları
OLE DB uygulamanızı başlatmadan önce aşağıdaki sorunları dikkate almanız gerekir:  
  
 **Hangi programlama uygulamasını OLE DB uygulamanızı yazmak için kullanacak mısınız?**  
 Microsoft, bunu gerçekleştirmek için birden çok kitaplık sunar: OLE DB Şablon kitaplığı, OLE DB öznitelikleri ve OLE DB SDK ham OLE DB arabirimler. Ayrıca, programınız yazmanıza Yardım sihirbazları vardır. Bu uygulamalar, şurada açıklanan [OLE DB Şablonları, öznitelikler ve diğer uygulamalar](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).  
  
 **Kendi sağlayıcınızı yazma gerekiyor mu?**  
 Çoğu geliştirici, kendi sağlayıcı yazma gerekmez. Microsoft çeşitli sağlayıcılar sunar. Bir veri bağlantısı (örneğin, projenize ATL OLE DB Tüketicisi Sihirbazı'nı kullanarak bir tüketici eklediğinizde,), oluşturduğunuz her **veri bağlantı özellikleri** iletişim kutusu, sisteminize kayıtlı tüm yok sağlayıcıları listeler. Bu sağlayıcılardan birini kendi veri deposu ve veri erişim uygulamanız için uygun değilse, kolay bir şey yapmak için aşağıdakilerden birini kullanılır. Ancak, veri deponuz Bu kategorilerden birini uygun değilse, kendi sağlayıcınızı oluşturmak zorunda. Sağlayıcılar oluşturma hakkında daha fazla bilgi için bkz: [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **Hangi düzeyde desteği için tüketici gerekiyor mu?**  
 Bazı tüketiciler çok basit olabilir. olsa da başkalarının çok karmaşık olabilir. OLE DB nesnelerin işlevselliğini özellikleri tarafından belirtilir. ATL OLE DB Tüketicisi Sihirbazı bir sağlayıcı oluşturmak için bir tüketici veya veritabanı sağlayıcısı Sihirbazı oluşturmak için kullandığınız zaman, standart bir dizi işlev vermek uygun nesne özelliklerini ayarlar. Sihirbazın ürettiği tüketici veya sağlayıcısı sınıfları bunları yapmak için ihtiyacınız olan her şeyi desteklemez, ancak bu sınıfların arabirimlerini başvurmak gerekiyorsa, [OLE DB şablonları kitaplığı](../../data/oledb/ole-db-templates.md). Bu arabirimler, bunları sizin için daha kolay hale getirmek için fazladan uygulama sağlama ham OLE DB birimleri kaydır.  
  
 Bir satır kümesi veri güncelleştirmek istiyor ancak Sihirbazı ile tüketici oluşturduğunuzda bu belirtmek, örneğin, işlevselliği olaydan sonra ayarlayarak belirtebilirsiniz `DBPROP_IRowsetChange` ve `DBPROP_UPDATABILITY` command nesnesindeki özellikleri. Ardından, satır kümesi oluşturulduğunda sahip `IRowsetChange` arabirimi.  
  
 **Eski kod başka bir veri erişim teknolojisi (ADO, ODBC ve DAO) kullanılarak var mı?**  
 Olası eşleştirme birleşimlerini (örneğin, OLE DB bileşenlerle ADO bileşenlerini kullanma ve OLE DB için ODBC kodu geçirme) teknolojileri göz önünde bulundurulduğunda, tüm durumları kapsayan Visual C++ belgelerinin kapsamıdır. Ancak, aşağıdaki Microsoft Web sitelerinde çeşitli senaryoları kapsayan birçok makale mevcuttur:  
  
-   [Microsoft Yardım ve Destek](https://support.microsoft.com/)  
  
-   [Microsoft Data Access teknik makaleler genel bakış](https://msdn.microsoft.com/en-us/library/ms810811.aspx)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)