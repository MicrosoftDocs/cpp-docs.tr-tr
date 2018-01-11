---
title: "Etkin belge sunucuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3dacb923b2e51ddc031165e637b08c9614ee1bf3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="active-document-servers"></a>Etkin Belge Sunucuları
Etkin belge sunucuları gibi diğer uygulama türleriyle Word, Excel veya PowerPoint konak belgelerin etkin belgeler çağrılır. (Yalnızca başka bir belge sayfasında görüntülenir) nesneleri OLE katıştırılmış etkin belgeler tam arabirimi ve kendilerini oluşturan sunucu uygulamasının tam yerel işlevselliği sağlar. Kullanıcılar, belgeleri oluşturabilir (etkin belgeyi etkin olup olmadığını), sık kullanılan uygulamalar gücünü kullanarak henüz kabul elde edilen proje tek bir varlık olarak.  
  
 Etkin belgeler birden fazla sayfa olabilir ve her zaman yerinde etkin olur. Etkin belgeler denetim ile bunların menülerini birleştirme kullanıcı arabiriminin parçası **dosya** ve **yardımcı** kapsayıcısının menüleri. Bunlar, kapsayıcının tüm düzenleme alanı kaplar ve görünümleri ve (kenar boşlukları, altbilgi ve benzeri) yazıcı sayfanın düzenini denetleyebilirsiniz.  
  
 MFC belge/görünüm arabirimleri, komutu eşlemeleri dağıtma, yazdırma, menü yönetimi ve kayıt defteri yönetimi etkin belge sunucuları uygular. Belirli programlama gereklilikler [etkin belgeler](../mfc/active-documents.md).  
  
 MFC ile etkin belgeler destekleyen [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) türetilmiş sınıf [CCmdTarget](../mfc/reference/ccmdtarget-class.md), ve [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md), türetilmiş [ COleServerItem](../mfc/reference/coleserveritem-class.md). MFC ile etkin belge kapsayıcıları destekler [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md) türetilmiş sınıf [COleClientItem](../mfc/reference/coleclientitem-class.md).  
  
 `CDocObjectServer`Etkin belge arabirimleri eşler ve başlatır ve etkin bir belge etkinleştirir. MFC makroları etkin belgelerde komut yönlendirme işlemek için de sağlar. Etkin belgeler, uygulamanızda kullanmak için AfxDocOb.h StdAfx.h dosyanıza ekleyin.  
  
 Normal bir MFC sunucusu kendi kancalarını `COleServerItem`-türetilmiş sınıf. Seçerseniz MFC Uygulama Sihirbazı'nı bu sınıf sizin için oluşturur **Mini sunucu** veya **tam sunucu** uygulama sunucunuzu birleşik belge desteği sağlamak için onay kutusunu. Aynı zamanda belirlerseniz **etkin belge sunucusu** onay kutusu, MFC Uygulama Sihirbazı'nı oluşturur türetilmiş bir sınıf `CDocObjectServerItem` yerine.  
  
 `COleDocObjectItem` Sınıfı, bir etkin belge kapsayıcısı olmak bir OLE kapsayıcı olanak tanır. MFC Uygulama Sihirbazı'nı seçerek bir etkin belge kapsayıcısı oluşturmak için kullanabileceğiniz **etkin belge kapsayıcısı** MFC Uygulama Sihirbazı'nı bileşik belge desteği sayfasının onay kutusu. Daha fazla bilgi için bkz: [bir etkin belge kapsayıcı uygulaması oluşturma](../mfc/creating-an-active-document-container-application.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsaması](../mfc/active-document-containment.md)

