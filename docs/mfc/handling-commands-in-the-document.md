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
ms.openlocfilehash: 8845ea7c44fd5a34774db0508302f5959987cdc9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441271"
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme

Belge sınıfınıza da menü öğeleri, araç çubuğu düğmeleri veya kısayol tuşları tarafından oluşturulan belirli komutları işleyebilir. Varsayılan olarak, `CDocument` kaydetme işler ve farklı kaydet Dosya menüsünde komutları kullanarak seri hale getirme. Verileri etkileyen diğer komutlar da belgenizin üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıfı `CScribDoc` belgede şu anda depolanan verilerin tümünü siler Tümünü Temizle Düzenle komutu için bir işleyici sağlar. Belgeler, ileti eşlemeleri olabilir, ancak görünümler, belgeleri standart Windows iletileri işleyemez — yalnızca **WM_COMMAND** iletileri ya da "komutları."

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)

