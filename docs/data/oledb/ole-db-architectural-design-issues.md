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
ms.openlocfilehash: e20fce19824cf093625347bca42f55cbad302b61
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040615"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB Mimari Tasarım Sorunları

OLE DB uygulamanızı başlatmadan önce aşağıdaki sorunları dikkate almanız gerekir:  
  
## <a name="what-programming-implementation-will-you-use-to-write-your-ole-db-application"></a>Hangi programlama uygulamasını OLE DB uygulamanızı yazmak için kullanacak mısınız?

Microsoft, bunu gerçekleştirmek için birden çok kitaplık sunar: OLE DB Şablon kitaplığı, OLE DB öznitelikleri ve OLE DB SDK ham OLE DB arabirimler. Ayrıca, programınız yazmanıza Yardım sihirbazları vardır. Bu uygulamalar, şurada açıklanan [OLE DB Şablonları, öznitelikler ve diğer uygulamalar](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).

## <a name="do-you-need-to-write-your-own-provider"></a>Kendi sağlayıcınızı yazma gerekiyor mu?

Çoğu geliştirici, kendi sağlayıcı yazma gerekmez. Microsoft çeşitli sağlayıcılar sunar. Bir veri bağlantısı (örneğin, projenize ATL OLE DB Tüketicisi Sihirbazı'nı kullanarak bir tüketici eklediğinizde,), oluşturduğunuz her **veri bağlantı özellikleri** iletişim kutusu, sisteminize kayıtlı tüm yok sağlayıcıları listeler. Bu sağlayıcılardan birini kendi veri deposu ve veri erişim uygulamanız için uygun değilse, kolay bir şey yapmak için aşağıdakilerden birini kullanılır. Ancak, veri deponuz Bu kategorilerden birini uygun değilse, kendi sağlayıcınızı oluşturmak zorunda. Sağlayıcılar oluşturma hakkında daha fazla bilgi için bkz: [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md).

## <a name="what-level-of-support-do-you-need-for-your-consumer"></a>Hangi düzeyde desteği için tüketici gerekiyor mu?

Bazı tüketiciler çok basit olabilir. olsa da başkalarının çok karmaşık olabilir. OLE DB nesnelerin işlevselliğini özellikleri tarafından belirtilir. ATL OLE DB Tüketicisi Sihirbazı bir sağlayıcı oluşturmak için bir tüketici veya veritabanı sağlayıcısı Sihirbazı oluşturmak için kullandığınız zaman, standart bir dizi işlev vermek uygun nesne özelliklerini ayarlar. Sihirbazın ürettiği tüketici veya sağlayıcısı sınıfları bunları yapmak için ihtiyacınız olan her şeyi desteklemez, ancak bu sınıfların arabirimlerini başvurmak gerekiyorsa, [OLE DB şablonları kitaplığı](../../data/oledb/ole-db-templates.md). Bu arabirimler, bunları sizin için daha kolay hale getirmek için fazladan uygulama sağlama ham OLE DB birimleri kaydır.

Bir satır kümesi veri güncelleştirmek istiyor ancak Sihirbazı ile tüketici oluşturduğunuzda bu belirtmek, örneğin, işlevselliği olaydan sonra ayarlayarak belirtebilirsiniz `DBPROP_IRowsetChange` ve `DBPROP_UPDATABILITY` command nesnesindeki özellikleri. Ardından, satır kümesi oluşturulduğunda sahip `IRowsetChange` arabirimi.

## <a name="do-you-have-older-code-using-another-data-access-technology-ado-odbc-or-dao"></a>Eski kod başka bir veri erişim teknolojisi (ADO, ODBC ve DAO) kullanılarak var mı?

Olası eşleştirme birleşimlerini (örneğin, OLE DB bileşenlerle ADO bileşenlerini kullanma ve OLE DB için ODBC kodu geçirme) teknolojileri göz önünde bulundurulduğunda, tüm durumları kapsayan Visual C++ belgelerinin kapsamıdır. Ancak, aşağıdaki Microsoft Web sitelerinde çeşitli senaryoları kapsayan birçok makale mevcuttur:

- [Microsoft Yardım ve Destek](https://support.microsoft.com/)

- [Microsoft Data Access teknik makaleler genel bakış](https://msdn.microsoft.com/en-us/library/ms810811.aspx)

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
