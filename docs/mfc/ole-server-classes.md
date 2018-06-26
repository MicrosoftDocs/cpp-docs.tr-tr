---
title: OLE sunucu sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9d0c75325c62a92f65c56f2c76350bf752228fd
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932227"
---
# <a name="ole-server-classes"></a>OLE Sunucu Sınıfları
Bu sınıfların sunucu uygulamaları tarafından kullanılır. Sunucu belgeleri türetilir `COleServerDoc` yerine `CDocument`. Çünkü unutmayın `COleServerDoc` türetildiği `COleLinkingDoc`, sunucu belgeleri bağlama desteği kapsayıcıları de olabilir.  
  
 `COleServerItem` Bir belge veya başka bir belgede gömülü veya bağlı bir belge bölümü sınıfı temsil eder.  
  
 `COleIPFrameWnd` ve `COleResizeBar` nesne bir kapsayıcıda durumdayken yerinde düzenlemeyi desteklemek ve `COleTemplateServer` OLE nesneleri diğer uygulamalardan gelen düzenlenebilir belge/görünüm çiftleri oluşturmayı destekler.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Sunucu uygulaması belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneler sağlayın sunucu desteği ile etkileşim aracılığıyla toplu `COleServerItem` nesneleri. Görsel düzenleme yeteneğini sınıf kitaplığının belge/görünüm mimarisi kullanarak sağlanır.  
  
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

