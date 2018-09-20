---
title: Bir görünüm aracılığıyla kullanıcı girişini yorumlama | Microsoft Docs
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
ms.openlocfilehash: 974324e296478f0ec36024d4427496d21255fbf7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421413"
---
# <a name="interpreting-user-input-through-a-view"></a>Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama

Görünümün diğer üye işlevlerini işlemek ve tüm kullanıcı girişini yorumlama. Genellikle, işlenecek görünümü sınıfınızda ileti işleyicisi üye işlevleri tanımlayın:

- Windows [iletileri](../mfc/messages.md) fare ve klavye eylemleri tarafından oluşturulur.

- [Komutları](../mfc/user-interface-objects-and-command-ids.md) menüler, düğmeler ve kısayol tuşları.

Bu ileti işleyicisi üye işlevleri için ve panodan veri taşıma dahil olmak üzere veri girişi, seçimi veya düzenleme, aşağıdaki eylemleri yorumlama:

- Fare hareketlerini ve tıklama, sürüklediğinde ve çift tıklamaları birbirinden ayırma

- Tuş vuruşları

- Menü komutları

Windows iletileri, görünüm tanıtıcıları, uygulamanızın ihtiyaçlarına bağlıdır.

[İleti işleme ve eşleme konuları](../mfc/message-handling-and-mapping.md) menü öğeleri ve diğer kullanıcı arabirimi nesneleri komutları atama ve nasıl komutları işleyici işlevlerine nasıl bağlanacağını açıklar. [İleti işleme ve eşleme konuları](../mfc/message-handling-and-mapping.md) Ayrıca, komutların MFC tarafından nasıl yönlendirdiği açıklar ve standart Windows iletileri işleyicileri için bunları içeren nesneleri gönderir.

Örneğin, uygulamanızın doğrudan fare bir görünümde çizim yapma uygulamanız gerekebilir. Genişletilen Scribble örneğinin sırasıyla başlamak, devam etmek ve son satır parçasının çizim WM_LBUTTONDOWN ve WM_MOUSEMOVE WM_LBUTTONUP iletilerin nasıl işleneceğini gösterir. Öte yandan, bazen bir fare tıklaması görünümünüzdeki seçim olarak yorumlamak gerekebilir. Görünümünüzün `OnLButtonDown` işleyici işlevi kullanıcının çizim veya seçerek reddedildiğini belirlemek. Seçilirken, işleyici tıklayarak görünümünde bazı nesnenin sınırları içinde olup olmadığını belirlemek ve bu durumda, seçili olarak nesne göstermek alter.

Görünümünüzü kesme, kopyalama, yapıştırma veya Pano kullanarak seçili veri silme için Düzen menüsünden olanlar gibi bazı menü komutları da işleyebilirsiniz. Böyle bir işleyici bazı Pano ile ilgili üye işlevleri sınıfın çağıracak `CWnd` seçili veri öğesi ya da Panodaki aktarmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[Görünümleri Kullanma](../mfc/using-views.md)

