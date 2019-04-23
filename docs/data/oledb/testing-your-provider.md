---
title: Sağlayıcınızı Test Etme
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: d7a3adad546834e2bdc80a695f4c3bf2259dc0ba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038323"
---
# <a name="testing-your-provider"></a>Sağlayıcınızı Test Etme

Bir sağlayıcı yayınlamadan önce gösterilen sırada aşağıdaki testleri yapmanız gerekir. Bu testler, olası kullanıcılar için düzgün şekilde sağlayıcısı işlevleri göstermektedir.

1. Kullanarak sağlayıcıyı test bir [tüketici](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB tüketici şablonlarıyla yazılmış uygulaması. Test tüketici sağlayıcınızın (eklendiğinde veya değiştirildiğinde tüm kodlar) tüm işlevsel alanlar kapsamalıdır.

1. ADO ile yazılmış bir tüketici uygulaması kullanarak sağlayıcıyı test edin. Çoğu geliştirici (özellikle de Microsoft Visual Basic ve Microsoft C# geliştiricilerin) ADO ya da ADO.NET tüketici uygulamaları için kullanın. Test tüketici tüm işlevsel alanlar sağlayıcınızın kapsamalıdır. ADO tüketici uygulaması örneği için bkz: [ADO kod örnekleri Visual Basic'de](https://msdn.microsoft.com/library/ms807514.aspx).

1. Sağlayıcınız için OLE DB Sağlayıcısı 0 standart düzeyi karşıladığını gösterilecek (ADO uygunluk testlerini dahil) OLE DB uygunluk testlerini çalıştırın. (0 düzeyi açıklaması için arama **OLE DB düzeyi 0 uygunluk testlerini** adresindeki [OLE DB Programcı Kılavuzu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Bu testleri ve ilişkili belgeler Visual C++'da veri erişim SDK'sı dahil edilmiştir. Bu testleri sağlayıcınız da diğerini toplandığında çalıştığını göstermek için de yardımcı [hizmeti sağlayıcıları](../../data/oledb/ole-db-resource-pooling-and-services.md) değiştirir veya özellik eklemek özellikle yararlıdır. Uygunluk testleri hakkında daha fazla bilgi için Visual Studio CDs birinde bulunan veri erişim SDK'sı için Benioku dosyasına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)