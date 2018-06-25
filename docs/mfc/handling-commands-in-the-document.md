---
title: Belgedeki komutları işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a1e848827b46d40c1ec39f2af4788e6957932c5
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929118"
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme
Belge sınıfı ayrıca menü öğeleri, araç çubuğu düğmeleri veya kısayol tuşları tarafından oluşturulan belirli komutları işleyebilir. Varsayılan olarak, `CDocument` Kaydet Dosya menüsünden komutları kullanarak seri hale getirme ve kaydetme işler. Veri etkileyen diğer komutlar da belgenizi üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıf `CScribDoc` belgede şu anda depolanan verilerin tümünü siler Tümünü Temizle Düzenle komutu için bir işleyici sağlar. Belgeler, ileti eşlemeleri olamaz, ancak görünümleri farklı olarak, standart Windows iletileri belgeleri işleyemiyor — yalnızca **WM_COMMAND** iletileri ya da "komutları."  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

