---
description: 'Hakkında daha fazla bilgi edinin: sağlayıcınızı test etme'
title: Sağlayıcınızı Test Etme
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: de9ba1b6cb66df8041cc6a94f357d52fc2194553
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272662"
---
# <a name="testing-your-provider"></a>Sağlayıcınızı Test Etme

Bir sağlayıcıyı bırakmadan önce, belirtilen sırayla aşağıdaki testleri yapmanız gerekir. Bu sınamalar, sağlayıcının birçok olası Kullanıcı için düzgün şekilde işlediğini gösterir.

1. OLE DB tüketici şablonlarıyla yazılmış bir [Tüketici](../../data/oledb/creating-an-ole-db-consumer.md) uygulaması kullanarak sağlayıcıyı test edin. Test tüketicisi, sağlayıcınızın tüm işlevsel bölgelerini kapsamalıdır (eklediğiniz veya değiştirdiğiniz tüm kodlar).

1. Sağlayıcıyı ADO ile yazılmış bir tüketici uygulamasını kullanarak test edin. Çoğu geliştirici (özellikle Microsoft Visual Basic ve Microsoft C# geliştiricileri), tüketici uygulamaları için ADO veya ADO.NET kullanır. Test tüketicisi, sağlayıcınızın tüm işlevsel bölgelerini kapsamalıdır. ADO tüketici uygulamasına bir örnek için bkz. [Microsoft Visual Basic 'Da ADO kodu örnekleri](/previous-versions/ms807514(v=msdn.10)).

1. Sağlayıcının OLE DB sağlayıcıları için düzey 0 standardını karşıladığını göstermek için OLE DB uygunluk testlerini (ADO uygunluk testleri dahil) çalıştırın. (Düzey 0 ' ın bir açıklaması için, [OLE DB Programcı Kılavuzu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)'Nda **OLE DB düzey 0 uyumluluk testlerini** arayın. Bu testler ve ilişkili belgeler, veri erişimi SDK 'sında Visual C++ eklenmiştir. Bu sınamalar, sağlayıcınızın diğer [hizmet sağlayıcıları](../../data/oledb/ole-db-resource-pooling-and-services.md) tarafından toplanarak iyi şekilde çalıştığını ve özellikle de Özellikler eklediğinizde ya da eklerseniz yararlı olduğunu göstermeye yardımcı olur. Uygunluk testleri hakkında daha fazla bilgi için, Visual Studio CD 'Lerinden birinde bulunan veri erişimi SDK 'Sı için Benioku dosyasına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
