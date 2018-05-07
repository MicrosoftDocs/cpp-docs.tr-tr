---
title: Bir görünüm kullanıcı girişini yorumlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e3ade658046ad789a92bce044d12e5a6e76f7ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="interpreting-user-input-through-a-view"></a>Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama
Diğer üye işlevleri görünümün işlemek ve tüm kullanıcı girişi yorumlayabilir. Genellikle, işlenecek görünümü sınıfınızda ileti işleyicisi üye işlevleri tanımlayacaksınız:  
  
-   Windows [iletileri](../mfc/messages.md) fare ve klavye eylemleri tarafından oluşturulan.  
  
-   [Komutları](../mfc/user-interface-objects-and-command-ids.md) menüleri, araç çubuğu düğmeleri ve Hızlandırıcı tuşları.  
  
 Bu ileti işleyicisi üye işlevleri veri taşımak ve panodan dahil olmak üzere veri girişi, seçim veya düzenleme, aşağıdaki eylemleri yorumlama:  
  
-   Fare hareketleri ve tıklama sürüklediği ve çift tıklamalar  
  
-   Tuş vuruşları  
  
-   Menü komutları  
  
 Hangi Windows iletileri görünüm tanıtıcıları uygulamanızın gereksinimlerine göre değişir.  
  
 [İleti işleme ve eşleme konuları](../mfc/message-handling-and-mapping.md) menü öğeleri ve diğer kullanıcı arabirimi nesneleri komutları atama ve nasıl işleyici işlevlerine komutları bağlanacağını açıklar. [İleti işleme ve eşleme konuları](../mfc/message-handling-and-mapping.md) ayrıca nasıl MFC komutları yönlendirir açıklar ve standart Windows iletileri işleyicileri için bunları içeren nesneleri gönderir.  
  
 Örneğin, uygulamanızın görünümde çizim yapma doğrudan fare uygulamanız gerekebilir. Karalama örnek nasıl işleneceğini gösterir `WM_LBUTTONDOWN`, `WM_MOUSEMOVE`, ve `WM_LBUTTONUP` sırasıyla başlamak için iletileri devam ve bir çizgi kesimi çizim bitmelidir. Diğer taraftan, bazen bir fare tıklatma seçim olarak görünümünüzde yorumlama gerekebilir. Görünümün `OnLButtonDown` işleyici işlevi kullanıcı çizim veya seçerek olup olmadığını belirlemek. Seçilirken, işleyici tıklatın görünümünde bazı nesnesinin sınırları içinde olup olmadığını belirlemek ve varsa, nesneyi seçili olarak göstermek için ekranı alter.  
  
 Görünümünüzü kesme, kopyalama, yapıştırma veya Pano kullanarak seçili veri silmek için Düzen menüsünden olanlar gibi bazı menü komutlarını da işleyebilirsiniz. Bu tür bir işleyici bazı Pano ilgili üye işlevleri sınıfının çağırırdı `CWnd` seçili veri öğesi için veya Pano'dan aktarmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görünümleri Kullanma](../mfc/using-views.md)

