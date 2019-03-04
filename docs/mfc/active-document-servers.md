---
title: Etkin Belge Sunucuları
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
ms.openlocfilehash: 7050b810bb5e1f0c240222cd9b8c4922ced4238a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270780"
---
# <a name="active-document-servers"></a>Etkin Belge Sunucuları

Etkin belge sunucuları gibi diğer uygulama türleri Word, Excel veya PowerPoint konağı belgelerin etkin belgeler olarak bilinir. (Bu, yalnızca başka bir belge sayfasında görüntülenen) nesneleri OLE katıştırılmış etkin belgeler, tam arabirimi ve kendilerini oluşturan sunucu uygulamasının tam yerel işlevselliği sağlar. Kullanıcılar, belgeleri oluşturabilir (etkin belgeyi etkin olmaları durumunda), sık kullandığınız uygulamalar tam gücünden yararlanarak henüz kabul sonuç projesi tek bir varlık olarak.

Etkin belgeler ve her zaman yerinde etkin olan birden fazla sayfası olabilir. Etkin belgeler denetimi ile kendi menülerini birleştirme kullanıcı arabiriminin bir parçası **dosya** ve **yardımcı** kapsayıcının menülerini. Bunlar, kapsayıcının tüm düzenleme alanı kaplayan ve görünümleri ve (kenar boşlukları, altbilgiler ve benzeri) yazıcı sayfasının düzenini denetler.

MFC belge/görünüm arabirimleri, komut gönderme eşlemeleri, yazdırma, menü yönetim ve kayıt defteri yönetimini etkin belge sunucuları uygular. Belirli programlama gereklilikleri [etkin belgeler](../mfc/active-documents.md).

MFC destekleyen etkin belgeler ile [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) sınıfından türetilen [CCmdTarget](../mfc/reference/ccmdtarget-class.md), ve [Cdocobjectserverıtem](../mfc/reference/cdocobjectserveritem-class.md), türetilmiş [ Coleserverıtem](../mfc/reference/coleserveritem-class.md). MFC ile etkin belge kapsayıcıları destekleyen [Coledocobjectıtem](../mfc/reference/coledocobjectitem-class.md) sınıfından türetilen [Coleclientıtem](../mfc/reference/coleclientitem-class.md).

`CDocObjectServer` Etkin belge arabirimleri eşler, başlatır ve etkin bir belge etkinleştirir. MFC makroları etkin belgelerde komut yönlendirme işlemek için de sağlar. Etkin belgeler kullanmak için AfxDocOb.h StdAfx.h dosyanıza ekleyin.

Normal bir MFC sunucusu kendi kancaları `COleServerItem`-türetilmiş sınıf. Seçerseniz MFC Uygulama Sihirbazı bu sınıf sizin için oluşturur **Mini sunucu** veya **tam sunucu** application sunucunuza bileşik belge desteği sağlamak için onay kutusunu işaretleyin. Ayrıca seçerseniz **etkin belge sunucusu** onay kutusu, MFC Uygulama Sihirbazı oluşturur türetilen bir sınıf `CDocObjectServerItem` yerine.

`COleDocObjectItem` Sınıfı bir OLE kapsayıcısı etkin belge kapsayıcı olmasını sağlar. MFC Uygulama Sihirbazı'nı seçerek bir etkin belge kapsayıcısı oluşturmak için kullanabileceğiniz **etkin belge kapsayıcı** MFC Uygulama Sihirbazı bileşik belge desteği sayfanın onay kutusunu işaretleyin. Daha fazla bilgi için [bir etkin belge kapsayıcı uygulaması oluşturma](../mfc/creating-an-active-document-container-application.md).

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)
