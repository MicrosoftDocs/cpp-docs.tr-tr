---
title: "İleti işleyicileri | Microsoft Docs"
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
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1b906a49d7da7ed8505252a1759d7ea00fcda1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-handlers"></a>İleti İşleyicileri
MFC'de, ayrılmış bir *işleyici* işlevi ayrı her ileti işler. İleti işleyici işlevleri, bir sınıfın üye işlevlerdir. Bu belge koşullarını kullanır *ileti işleyicisi üye işlevi*, *ileti işleyicisi işlevi*, *ileti işleyicisi*, ve *işleyicisi*birbirinin yerine. İleti işleyicileri bazı tür "komut işleyicileri." olarak da bilinir  
  
 İleti işleyicileri hesapları çalışmanızı büyük bir kısmının için framework uygulaması yazma yazma. Bu makale ailesi ileti işleme mekanizması nasıl çalıştığı açıklanmaktadır.  
  
 Bunu bir ileti işleyicisi yaptığı o iletisine yanıt olarak Bitti'yi istediğiniz yapar. Sınıfının Özellikler penceresini kullanarak işleyicileri oluşturun ve ardından kaynak kod düzenleyicisini kullanarak işleyicinin kodunu doldurun.  
  
 Tüm Microsoft Visual C++ MFC ve olanaklarının, işleyicileri yazmak için kullanabilirsiniz. Tüm sınıflar listesi için bkz: [sınıf kitaplığına genel bakış](../mfc/class-library-overview.md) içinde *MFC başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

