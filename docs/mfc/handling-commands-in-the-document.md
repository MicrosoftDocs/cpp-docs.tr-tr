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
ms.openlocfilehash: f3cce539d52bd04e97a6b5f84cbd833b05afb5bb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280439"
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme

Belge sınıfınıza da menü öğeleri, araç çubuğu düğmeleri veya kısayol tuşları tarafından oluşturulan belirli komutları işleyebilir. Varsayılan olarak, `CDocument` kaydetme işler ve farklı kaydet Dosya menüsünde komutları kullanarak seri hale getirme. Verileri etkileyen diğer komutlar da belgenizin üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıfı `CScribDoc` belgede şu anda depolanan verilerin tümünü siler Tümünü Temizle Düzenle komutu için bir işleyici sağlar. Belgeler, ileti eşlemeleri olabilir, ancak görünümler, belgeleri standart Windows iletileri işleyemez — yalnızca **WM_COMMAND** iletileri ya da "komutları."

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)
