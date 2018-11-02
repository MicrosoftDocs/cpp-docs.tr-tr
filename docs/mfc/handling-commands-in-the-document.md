---
title: Belgedeki Komutları İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: d2f0a7271452ace9b9e06ff995af61881db4403c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548960"
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme

Belge sınıfınıza da menü öğeleri, araç çubuğu düğmeleri veya kısayol tuşları tarafından oluşturulan belirli komutları işleyebilir. Varsayılan olarak, `CDocument` kaydetme işler ve farklı kaydet Dosya menüsünde komutları kullanarak seri hale getirme. Verileri etkileyen diğer komutlar da belgenizin üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıfı `CScribDoc` belgede şu anda depolanan verilerin tümünü siler Tümünü Temizle Düzenle komutu için bir işleyici sağlar. Belgeler, ileti eşlemeleri olabilir, ancak görünümler, belgeleri standart Windows iletileri işleyemez — yalnızca **WM_COMMAND** iletileri ya da "komutları."

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)

