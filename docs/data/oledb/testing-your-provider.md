---
title: Sağlayıcınızı test etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7801d29371a2be069dcdf60807b0d8a99c99eedc
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689600"
---
# <a name="testing-your-provider"></a>Sağlayıcınızı Test Etme
Bir sağlayıcı yayınlamadan önce belirtilen sırayla aşağıdaki testleri gerçekleştirmeniz gerekir. Bu testler, olası kullanıcılar için düzgün şekilde sağlayıcısı işlevleri emin olun.  
  
1.  Kullanarak sağlayıcıyı test bir [tüketici](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB tüketici şablonlarıyla yazılmış uygulaması. Test tüketici sağlayıcınızın (eklenen veya değiştirilen tüm kodu) tüm işlevsel alanlar kapsamalıdır.  
  
2.  ADO ile yazılmış bir tüketici uygulaması kullanarak sağlayıcıyı test edin. Çoğu geliştirici (özellikle de Microsoft Visual Basic ve Microsoft C# geliştiricilerin) ADO ya da ADO.NET tüketici uygulamaları için kullanın. Test tüketici tüm işlevsel alanlar sağlayıcınızın kapsamalıdır. ADO tüketici uygulaması örneği için bkz: [ADO kod örnekleri Visual Basic'de](https://msdn.microsoft.com/library/ms807514.aspx).  
  
3.  Sağlayıcınız için OLE DB sağlayıcıları düzeyi 0 standart karşıladığından emin olmak için (ADO uygunluk testlerini dahil) OLE DB uygunluk testlerini çalıştırın. (Adresindeki "OLE DB düzeyi 0 uygunluk testleri için" 0 düzeyi açıklaması için arama [OLE DB Programcı Kılavuzu](/previous-versions/windows/desktop/ms713643\(v=vs.85\)). Bu testleri ve ilişkili belgeler Visual C++'da veri erişim SDK'sı dahil edilmiştir. Sağlayıcınız da diğerini toplandığında çalıştığından emin olmak için bu testleri de yardımcı [hizmeti sağlayıcıları](../../data/oledb/ole-db-resource-pooling-and-services.md) değiştirir veya özellik eklemek özellikle yararlıdır. Uygunluk testleri hakkında daha fazla bilgi için Visual Studio CDs birinde bulunan veri erişim SDK'sı için Benioku dosyasına bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)