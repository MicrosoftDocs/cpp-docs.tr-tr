---
title: "Belgedeki komutları işleme | Microsoft Docs"
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
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8d27698d573e1dee539f93ab88015285648fa77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme
Belge sınıfı ayrıca menü öğeleri, araç çubuğu düğmeleri veya kısayol tuşları tarafından oluşturulan belirli komutları işleyebilir. Varsayılan olarak, **CDocument** Kaydet Dosya menüsünden komutları kullanarak seri hale getirme ve kaydetme işler. Veri etkileyen diğer komutlar da belgenizi üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıf `CScribDoc` belgede şu anda depolanan verilerin tümünü siler Tümünü Temizle Düzenle komutu için bir işleyici sağlar. Belgeler, ileti eşlemeleri olamaz, ancak görünümleri farklı olarak, standart Windows iletileri belgeleri işleyemiyor — yalnızca **WM_COMMAND** iletileri ya da "komutları."  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

