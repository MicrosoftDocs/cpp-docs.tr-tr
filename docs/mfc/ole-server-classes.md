---
title: OLE Sunucu Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 610a69204e5cb66f2129351ab2a04bb0915a1b4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451694"
---
# <a name="ole-server-classes"></a>OLE Sunucu Sınıfları

Bu sınıflar, sunucu uygulamaları tarafından kullanılır. Sunucu belgeleri türetilir `COleServerDoc` yerine `CDocument`. Dikkat edin çünkü `COleServerDoc` türetilir `COleLinkingDoc`, sunucu belgeleri bağlamayı destekleyen kapsayıcılar da olabilir.

`COleServerItem` Bir belge veya başka bir belgeye gömülü veya bağlantılı bir belge bölümü sınıfı temsil eder.

`COleIPFrameWnd` ve `COleResizeBar` nesne bir kapsayıcıda olsa da, yerinde düzenleme desteği ve `COleTemplateServer` diğer uygulamalardan OLE nesneleri düzenlenebilir belge/görünüm çiftleri oluşturmayı destekler.

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
Sunucu uygulaması belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneleri sağlar sunucu desteği ile etkileşim aracılığıyla toplu `COleServerItem` nesneleri. Görsel düzenleme özelliği, Sınıf Kitaplığı'nızın belge/görünüm mimarisi kullanılarak sağlanır.

[Cdocıtem](../mfc/reference/cdocitem-class.md)<br/>
Soyut taban sınıfı `COleClientItem` ve `COleServerItem`. Sınıfından türetilen sınıfların nesnelerini `CDocItem` belge parçalarını temsil eder.

[Coleserverıtem](../mfc/reference/coleserveritem-class.md)<br/>
OLE arabirimi temsil etmek için kullanılan `COleServerDoc` öğeleri. Olur ve genellikle `COleServerDoc` belgeye katıştırılmış bölümünü temsil eden nesne. Belge parçalarını bağlantılarını destekleyen sunucularda olabilir birçok `COleServerItem` her biri temsil eden bir bağlantı bir kısmını serileştirmeniz nesneleri.

[Coleıpframewnd](../mfc/reference/coleipframewnd-class.md)<br/>
Sunucu belgesinin yerinde düzenlenirken çerçeve penceresi için bir görünüm sağlar.

[COleResizeBar](../mfc/reference/coleresizebar-class.md)<br/>
Yerinde yeniden boyutlandırma için standart kullanıcı arabirimi sağlar. Bu sınıfın nesneleri ile birlikte kullanılan her zaman `COleIPFrameWnd` nesneleri.

[Coletemplateserver'ı](../mfc/reference/coletemplateserver-class.md)<br/>
Framework'ün belge/görünüm mimarisi kullanarak belgeleri oluşturmak için kullanılır. A `COleTemplateServer` nesne için ilişkili bir çalışmasının çoğunu Temsilciler `CDocTemplate` nesne.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE işlenirken bir hata kaynaklanan bir özel durum. Bu sınıf, kapsayıcılar ve sunucular tarafından kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

