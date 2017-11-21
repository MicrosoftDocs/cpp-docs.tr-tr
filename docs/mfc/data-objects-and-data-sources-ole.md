---
title: "Veri nesneleri ve veri kaynakları (OLE) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb39b5089b7cd4849e5afd3eaac239c0c2ab3adf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-objects-and-data-sources-ole"></a>Veri Nesneleri ve Veri Kaynakları (OLE)
Veri aktarımı, Pano veya sürükle ve bırak, kullanarak ya da gerçekleştirdiğinizde verileri bir kaynak ve hedef sahiptir. Başka bir uygulamaya yapıştırma için kabul ettiği ve kopyalamak için verileri bir uygulama sağlar. Aynı veri aktarımı başarılı olması için farklı işlemler gerçekleştirmek her iki tarafı aktarım gerekir. Microsoft Foundation Class (MFC) kitaplığı, bu Aktarım her iki tarafındaki temsil eden iki sınıflar sağlar:  
  
-   Veri kaynakları (tarafından uygulanan `COleDataSource` nesneler) veri aktarımı kaynak tarafı temsil eder. Veriler panoya kopyalanacak olduğunda ya da veri için bir Sürükle ve bırak işlemi sağlandığında bunlar kaynak uygulama tarafından oluşturulur.  
  
-   Veri nesneleri (tarafından uygulanan `COleDataObject` nesneler) veri aktarımı hedef tarafı temsil eder. Hedef uygulama içine veya Pano'dan yapıştırma işlemi gerçekleştirmek için sorulduğunda bırakılan veri olduğunda oluşturulur.  
  
 Aşağıdaki makaleler veri nesneleri ve veri kaynaklarında uygulamalarınızı nasıl kullanılacağı açıklanmaktadır. Her ikisi de bağlı verileri kopyalama ve yapıştırma için çağrılabilir çünkü bu bilgiler kapsayıcı ve sunucu uygulamaları için geçerlidir.  
  
-   [Veri nesneleri ve veri kaynakları: oluşturma ve yok etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Veri nesneleri ve veri kaynakları: düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Sürükleme ve bırakma](../mfc/drag-and-drop-ole.md)  
  
 [Pano](../mfc/clipboard.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject sınıfı](../mfc/reference/coledataobject-class.md)   
 [COleDataSource sınıfı](../mfc/reference/coledatasource-class.md)
