---
title: "Sağlayıcınızı test etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a1c97db59b88672f390fc88b78f8d5f843ca7099
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="testing-your-provider"></a>Sağlayıcınızı Test Etme
Sağlayıcı yayınlamadan önce gösterilen sırada aşağıdaki testleri gerçekleştirmeniz gerekir. Bu testler olası kullanıcılar için düzgün sağlayıcısı çalıştığından emin olun.  
  
1.  Sağlayıcıyı kullanarak test bir [tüketici](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB tüketici şablonlarıyla yazılmış uygulama. Sınama tüketicisi sağlayıcınızın (eklenen veya değiştirilen tüm kodu) tüm işlevsel alanlara kapsamalıdır.  
  
2.  Sağlayıcıyı ADO ile yazılmış bir tüketici uygulaması kullanarak sınayın. Çoğu geliştirici (özellikle Microsoft Visual Basic ve Microsoft C# geliştiricileri) ADO ya da ADO.NET tüketici uygulamaları için kullanın. Sınama tüketicisi sağlayıcınızın tüm işlevsel alanlara kapsamalıdır. ADO tüketici uygulaması örneği için bkz: [ADO kod örnekleri Visual Basic'de](https://msdn.microsoft.com/en-us/library/ms807514.aspx).  
  
3.  Sağlayıcınız için OLE DB sağlayıcıları düzey 0 standardını karşıladığından emin olmak için (ADO uygunluk testlerini dahil) OLE DB uygunluk testlerini çalıştırın. (Adresindeki "OLE DB düzey 0 uygunluk testleri için" 0 düzeyi açıklaması için arama [OLE DB Programcı Kılavuzu](http://go.microsoft.com/fwlink/?linkid=121548). Bu testler ve ilişkili belgeler veri erişim SDK'te Visual C++ yer alır. Bu testler sağlayıcınız iyi diğer tarafından toplandığında çalıştığından emin olmak için de yardımcı [hizmeti sağlayıcıları](../../data/oledb/ole-db-resource-pooling-and-services.md) ve değiştirme veya Özellikler ekleme, özellikle yararlı olur. Uygunluk testleri hakkında daha fazla bilgi için Visual Studio CD birinde bulunan veri erişimi SDK'sı için Benioku dosyasına bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)