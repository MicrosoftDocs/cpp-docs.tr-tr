---
title: Veri nesneleri ve veri kaynakları (OLE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 766148494c6b8693f8d9e65f27e157b58d8e8689
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="data-objects-and-data-sources-ole"></a>Veri Nesneleri ve Veri Kaynakları (OLE)
Veri aktarımı, Pano veya sürükle ve bırak, kullanarak ya da gerçekleştirdiğinizde verileri bir kaynak ve hedef sahiptir. Başka bir uygulamaya yapıştırma için kabul ettiği ve kopyalamak için verileri bir uygulama sağlar. Aynı veri aktarımı başarılı olması için farklı işlemler gerçekleştirmek her iki tarafı aktarım gerekir. Microsoft Foundation Class (MFC) kitaplığı, bu Aktarım her iki tarafındaki temsil eden iki sınıflar sağlar:  
  
-   Veri kaynakları (tarafından uygulanan `COleDataSource` nesneler) veri aktarımı kaynak tarafı temsil eder. Veriler panoya kopyalanacak olduğunda ya da veri için bir Sürükle ve bırak işlemi sağlandığında bunlar kaynak uygulama tarafından oluşturulur.  
  
-   Veri nesneleri (tarafından uygulanan `COleDataObject` nesneler) veri aktarımı hedef tarafı temsil eder. Hedef uygulama içine veya Pano'dan yapıştırma işlemi gerçekleştirmek için sorulduğunda bırakılan veri olduğunda oluşturulur.  
  
 Aşağıdaki makaleler veri nesneleri ve veri kaynaklarında uygulamalarınızı nasıl kullanılacağı açıklanmaktadır. Her ikisi de bağlı verileri kopyalama ve yapıştırma için çağrılabilir çünkü bu bilgiler kapsayıcı ve sunucu uygulamaları için geçerlidir.  
  
-   [Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Veri Nesneleri ve Veri Kaynakları: Düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Sürükleme ve Bırakma](../mfc/drag-and-drop-ole.md)  
  
 [Pano](../mfc/clipboard.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject sınıfı](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
