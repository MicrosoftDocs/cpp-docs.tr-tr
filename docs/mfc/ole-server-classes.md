---
title: OLE Sunucu Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 92dec514611dcce7d6c666fdd271843e69561637
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447593"
---
# <a name="ole-server-classes"></a>OLE Sunucu Sınıfları

Bu sınıflar sunucu uygulamaları tarafından kullanılır. Sunucu belgeleri `CDocument`yerine `COleServerDoc` türetilir. `COleServerDoc` `COleLinkingDoc`türetildiği için sunucu belgelerinin, bağlamayı destekleyen kapsayıcılar da olabileceğini unutmayın.

`COleServerItem` sınıfı, bir belgenin veya başka bir belgeye katıştırılabilen ya da bağlantılı bir belge kısmını temsil eder.

`COleIPFrameWnd` ve `COleResizeBar`, nesne kapsayıcıda iken yerinde düzenleme desteği `COleTemplateServer` ve diğer uygulamalardan gelen OLE nesnelerinin düzenlenebilmesi için belge/görünüm çiftleri oluşturulmasını destekler.

[Cotaserverdoc](../mfc/reference/coleserverdoc-class.md)<br/>
Sunucu-uygulama belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneler, `COleServerItem` nesnelerle etkileşimler aracılığıyla sunucu desteğinin toplu olarak sağlamasını sağlar. Görsel düzen özelliği, sınıf kitaplığının belge/görünüm mimarisi kullanılarak sağlanır.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
`COleClientItem` ve `COleServerItem`soyut temel sınıfı. `CDocItem` türetilen sınıfların nesneleri, belgelerin parçalarını temsil eder.

[COleServerItem](../mfc/reference/coleserveritem-class.md)<br/>
Öğeleri `COleServerDoc` için OLE arabirimini temsil etmek üzere kullanılır. Genellikle bir belgenin katıştırılmış bölümünü temsil eden bir `COleServerDoc` nesnesi vardır. Belgelerin bölümlerine bağlantıları destekleyen sunucularda, her biri belgenin bir kısmına olan bağlantıyı temsil eden birçok `COleServerItem` nesnesi olabilir.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Bir sunucu belgesi yerinde düzenlenirken bir görünüm için çerçeve penceresi sağlar.

[COleResizeBar](../mfc/reference/coleresizebar-class.md)<br/>
Yerinde yeniden boyutlandırma için standart Kullanıcı arabirimi sağlar. Bu sınıfın nesneleri `COleIPFrameWnd` nesneleriyle birlikte her zaman kullanılır.

[COleTemplateServer](../mfc/reference/coletemplateserver-class.md)<br/>
Framework 'ün belge/görünüm mimarisini kullanarak belge oluşturmak için kullanılır. `COleTemplateServer` nesnesi, işinin çoğunu ilişkili bir `CDocTemplate` nesnesine devreder.

[Colet özel durumu](../mfc/reference/coleexception-class.md)<br/>
OLE işlemedeki bir hatadan kaynaklanan bir özel durum. Bu sınıf, hem kapsayıcılar hem de sunucular tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
