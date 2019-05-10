---
title: OLE DB Mimari Tasarım Sorunları
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
ms.openlocfilehash: ef2837ea80c61f074cf567ee1fe61fa2cfa0ae73
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525314"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB Mimari Tasarım Sorunları

> [!NOTE]
> ATL OLE DB Tüketicisi Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil. İşlevselliğini el ile eklemeye devam edebilirsiniz. Daha fazla bilgi için [olmadan bir tüketici kullanarak sihirbaz oluşturma](creating-a-consumer-without-using-a-wizard.md).

Aşağıdaki sorunlar, OLE DB uygulamayı başlatmadan önce göz önünde bulundurun:

## <a name="what-programming-implementation-will-you-use-to-write-your-ole-db-application"></a>Hangi programlama uygulamasını OLE DB uygulamanızı yazmak için kullanacak mısınız?

Microsoft, bu görevi gerçekleştirmek için birden çok kitaplık sunar: OLE DB Şablon kitaplığı, OLE DB öznitelikleri ve OLE DB SDK ham OLE DB arabirimler. Aynı zamanda, programınız yazmanıza Yardım sihirbazları vardır. Bu uygulamalar, şurada açıklanan [OLE DB Şablonları, öznitelikler ve diğer uygulamalar](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).

## <a name="do-you-need-to-write-your-own-provider"></a>Kendi sağlayıcınızı yazma gerekiyor mu?

Çoğu geliştirici, kendi sağlayıcı yazma gerekmez. Microsoft çeşitli sağlayıcılar sunar. Bir veri bağlantısı oluşturduğunuzda (örneğin, eklediğinizde, bir tüketici kullanarak projenize **ATL OLE DB Tüketicisi Sihirbazı**), **veri bağlantı özellikleri** iletişim kutusu, kullanılabilir tüm sağlayıcıları listeler Sisteminizde kayıtlı. Sağlayıcılardan birini kendi veri deposu ve veri erişim uygulamanız için uygun değilse, kolay bir şey yapmak için aşağıdakilerden birini kullanmaktır. Ancak, veri deponuz Bu kategorilerden birini sığmıyorsa, kendi sağlayıcınızı oluşturmanız gerekir. Sağlayıcılar oluşturma hakkında daha fazla bilgi için bkz: [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md).

## <a name="what-level-of-support-do-you-need-for-your-consumer"></a>Hangi düzeyde desteği için tüketici gerekiyor mu?

Bazı tüketiciler temel olabilir. diğer karmaşık olabilir, ancak. OLE DB nesnelerin işlevselliğini özellikleri tarafından belirtilir. Kullanırken **ATL OLE DB Tüketicisi Sihirbazı** bir tüketici oluşturma veya **veritabanı sağlayıcısı Sihirbazı** bir sağlayıcı oluşturmak için standart bir dizi size uygun nesne özelliklerini ayarlar İşlevler. Sihirbazın ürettiği tüketici veya sağlayıcısı sınıfları bunları yapmak için ihtiyacınız olan her şeyi desteklemez, ancak bu sınıfların arabirimlerini başvurmak gerekiyorsa, [OLE DB şablonları kitaplığı](../../data/oledb/ole-db-templates.md). Bu arabirimler, bunları sizin için daha kolay hale getirmek için fazladan uygulama sağlama ham OLE DB birimleri kaydır.

Bir satır kümesi veri güncelleştirmek istiyor ancak Sihirbazı ile tüketici oluşturduğunuzda bu belirtmek, örneğin, işlevselliği olaydan sonra ayarlayarak belirtebilirsiniz `DBPROP_IRowsetChange` ve `DBPROP_UPDATABILITY` command nesnesindeki özellikleri. Ardından, satır kümesi oluşturulduğunda sahip `IRowsetChange` arabirimi.

## <a name="do-you-have-older-code-using-another-data-access-technology-ado-odbc-or-dao"></a>Eski kod başka bir veri erişim teknolojisi (ADO, ODBC ve DAO) kullanılarak var mı?

Olası eşleştirme birleşimlerini (örneğin, OLE DB bileşenlerle ADO bileşenlerini kullanma ve OLE DB için ODBC kodu geçirme) teknolojileri göz önünde bulundurulduğunda, tüm durumları kapsayan Visual C++ belgelerinin kapsamıdır. Ancak, aşağıdaki Microsoft web sitelerinde çeşitli senaryoları kapsayan birçok makale mevcuttur:

- [Microsoft Yardım ve Destek](https://support.microsoft.com/)

- [Microsoft Data Access teknik makaleler genel bakış](https://msdn.microsoft.com/library/ms810811.aspx)

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
