---
description: 'Daha fazla bilgi edinin: OLE sunucu sınıfları'
title: OLE Sunucu Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: a2f60f148d6a24323ca6546e633c30103b315ee2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243997"
---
# <a name="ole-server-classes"></a>OLE Sunucu Sınıfları

Bu sınıflar sunucu uygulamaları tarafından kullanılır. Sunucu belgeleri kaynağından değil, öğesinden türetilir `COleServerDoc` `CDocument` . , `COleServerDoc` Öğesinden türetildiğinden `COleLinkingDoc` , sunucu belgelerinin bağlamayı destekleyen kapsayıcılar de olabileceğini unutmayın.

Sınıfı, bir belgenin `COleServerItem` veya başka bir belgeye katıştırılabilen veya ile bağlantılı olabilecek bir belge veya kısmını temsil eder.

`COleIPFrameWnd` ve `COleResizeBar` nesne bir kapsayıcıda iken yerinde düzenleme desteği ve `COleTemplateServer` diğer UYGULAMALARDAN gelen OLE nesnelerinin düzenlenebilmesi için belge/görünüm çiftleri oluşturulmasını destekler.

[Cotaserverdoc](reference/coleserverdoc-class.md)<br/>
Sunucu-uygulama belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneler, nesneleri olan etkileşimler aracılığıyla sunucu desteği toplu sağlar `COleServerItem` . Görsel düzen özelliği, sınıf kitaplığının belge/görünüm mimarisi kullanılarak sağlanır.

[CDocItem](reference/cdocitem-class.md)<br/>
Ve soyut taban sınıfı `COleClientItem` `COleServerItem` . Sınıfından türetilmiş sınıfların nesneleri `CDocItem` , belgelerin parçalarını temsil eder.

[COleServerItem](reference/coleserveritem-class.md)<br/>
OLE arabirimini öğelere göstermek için kullanılır `COleServerDoc` . Genellikle bir `COleServerDoc` belgenin katıştırılmış bölümünü temsil eden bir nesne vardır. Belgelerin bölümlerine bağlantıları destekleyen sunucularda, `COleServerItem` her biri belgenin bir kısmına olan bağlantıyı temsil eden birçok nesne olabilir.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Bir sunucu belgesi yerinde düzenlenirken bir görünüm için çerçeve penceresi sağlar.

[COleResizeBar](reference/coleresizebar-class.md)<br/>
Yerinde yeniden boyutlandırma için standart Kullanıcı arabirimi sağlar. Bu sınıfın nesneleri her zaman nesneleriyle birlikte kullanılır `COleIPFrameWnd` .

[COleTemplateServer](reference/coletemplateserver-class.md)<br/>
Framework 'ün belge/görünüm mimarisini kullanarak belge oluşturmak için kullanılır. Bir `COleTemplateServer` nesne, işinin çoğunu ilişkili bir nesne ile devreder `CDocTemplate` .

[Colet özel durumu](reference/coleexception-class.md)<br/>
OLE işlemedeki bir hatadan kaynaklanan bir özel durum. Bu sınıf, hem kapsayıcılar hem de sunucular tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
