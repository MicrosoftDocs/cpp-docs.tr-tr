---
title: "Belge görünüm mimarisinin bir özeti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ceadc55945a31e4787287beb6943897784aeaad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Bir Özeti
Belgeler ve görünümler tipik bir MFC uygulamasında eşleştirilmelidir. Veri belgesinde depolanır, ancak görünümü ayrıcalıklı veri erişimi. Belge ayrımı görünümünden depolama ve veri Bakımı kendi görüntüden ayırır.  
  
## <a name="gaining-access-to-document-data-from-the-view"></a>Veri görünümünden belge erişimini  
 Görünümü ile ya da kendi belgenin verilere erişen [GetDocument](../mfc/reference/cview-class.md#getdocument) işaretçi belgeye ya da C++ sınıf görünümü yaparak döndüren işlev `friend` belge sınıfının. Görünüm veri erişimini çizin veya aksi halde işlemek hazır olduğunda veri almak için sonra kullanır.  
  
 Örneğin, Görünüm'ün gelen [OnDraw](../mfc/reference/cview-class.md#ondraw) görünümü üye işlevini kullanır **GetDocument** bir belge işaretçi elde edilir. Bu işaretçi erişmek için kullandığı sonra bir `CString` belgedeki veri üyesi. Görünüm dizeye geçirir `TextOut` işlevi. Bu örnek kodu görmek için bkz: [bir görünümde çizim yapma](../mfc/drawing-in-a-view.md).  
  
## <a name="user-input-to-the-view"></a>Kullanıcı girişi görüntülemek için  
 Görünümün seçim veya veri düzenleme olarak kendi içinde bir fare tıklatma de yorumlayabilir. Benzer şekilde, tuş vuruşlarınızı veri girişi veya düzenleme olarak yorumlayabilir. Kullanıcı türleri metin yöneten bir görünümde bir dize varsayalım. Görünüm belge için bir işaretçi alır ve bazı veri yapısında depolar belgeye yeni veri iletmek için işaretçiyi kullanır.  
  
## <a name="updating-multiple-views-of-the-same-document"></a>Aynı belgenin birden çok görünüm güncelleştiriliyor  
 Bir uygulamada aynı belgenin birden çok görünümlerle — bir metin düzenleyicisinde Bölümlendirici pencere gibi — görünümü, yeni verileri ilk belgeye geçirir. Belgenin çağırır sonra [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) kendileri yeni verileri yansıtacak şekilde güncelleştirmek için belgenin tüm görünümleri söyler üye işlevi. Bu görünümler eşitler.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge/görünüm mimarisinin avantajları](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Belge/görünüm mimarisinin alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

