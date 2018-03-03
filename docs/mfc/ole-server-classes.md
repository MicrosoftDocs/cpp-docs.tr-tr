---
title: "OLE sunucu sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d23c7cb23d9221f8f2183c666a99c70ef149db3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-server-classes"></a>OLE Sunucu Sınıfları
Bu sınıfların sunucu uygulamaları tarafından kullanılır. Sunucu belgeleri türetilir `COleServerDoc` yerine **CDocument**. Çünkü unutmayın `COleServerDoc` türetildiği `COleLinkingDoc`, sunucu belgeleri bağlama desteği kapsayıcıları de olabilir.  
  
 `COleServerItem` Bir belge veya başka bir belgede gömülü veya bağlı bir belge bölümü sınıfı temsil eder.  
  
 `COleIPFrameWnd`ve `COleResizeBar` nesne bir kapsayıcıda durumdayken yerinde düzenlemeyi desteklemek ve `COleTemplateServer` OLE nesneleri diğer uygulamalardan gelen düzenlenebilir belge/görünüm çiftleri oluşturmayı destekler.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Sunucu uygulaması belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc`nesneler sağlayın sunucu desteği ile etkileşim aracılığıyla toplu `COleServerItem` nesneleri. Görsel düzenleme yeteneğini sınıf kitaplığının belge/görünüm mimarisi kullanarak sağlanır.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Soyut taban sınıfı `COleClientItem` ve `COleServerItem`. Sınıfların nesnelerini türetilen `CDocItem` belge parçalarını temsil eder.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 OLE arabirimi temsil etmek için kullanılan `COleServerDoc` öğeleri. Genellikle bir olduğundan `COleServerDoc` bir belgenin katıştırılmış bölümünü temsil eden nesne. Destek belgeleri bölümlerine bağlantılar sunucuları olabilir birçok `COleServerItem` nesneleri, belgeyi bir kısmı için her biri gösteren bir bağlantı.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Bir sunucu belge yerinde düzenlendiğinde çerçeve penceresi için bir görünüm sağlar.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 Yerinde yeniden boyutlandırma için standart kullanıcı arabirimi sağlar. Bu sınıfın nesneleri ile birlikte kullanılan her zaman `COleIPFrameWnd` nesneleri.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 Framework'ün belge/görünüm mimarisi kullanarak belgeleri oluşturmak için kullanılır. A `COleTemplateServer` nesne temsilciler kendi iş ilişkili bir çoğunu `CDocTemplate` nesnesi.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE işlenirken bir hata kaynaklanan bir özel durum. Bu sınıf, kapsayıcılar ve sunucular tarafından kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

