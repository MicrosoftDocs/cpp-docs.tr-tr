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
ms.openlocfilehash: c20ff02b2d72f1dfa6afab5a0d547b46aa55b18c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343560"
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme
Belge sınıfı ayrıca menü öğeleri, araç çubuğu düğmeleri veya kısayol tuşları tarafından oluşturulan belirli komutları işleyebilir. Varsayılan olarak, **CDocument** Kaydet Dosya menüsünden komutları kullanarak seri hale getirme ve kaydetme işler. Veri etkileyen diğer komutlar da belgenizi üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıf `CScribDoc` belgede şu anda depolanan verilerin tümünü siler Tümünü Temizle Düzenle komutu için bir işleyici sağlar. Belgeler, ileti eşlemeleri olamaz, ancak görünümleri farklı olarak, standart Windows iletileri belgeleri işleyemiyor — yalnızca **WM_COMMAND** iletileri ya da "komutları."  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

