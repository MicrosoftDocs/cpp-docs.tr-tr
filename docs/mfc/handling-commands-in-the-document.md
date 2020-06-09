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
ms.openlocfilehash: ed2ef635437408cacfd600d6cdba4b3731d575b4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625738"
---
# <a name="handling-commands-in-the-document"></a>Belgedeki Komutları İşleme

Belge sınıfınız menü öğeleri, araç çubuğu düğmeleri veya hızlandırıcı tuşları tarafından oluşturulan belirli komutları da işleyebilir. Varsayılan olarak, `CDocument` serileştirme kullanarak Dosya menüsündeki Kaydet ve farklı Kaydet komutlarını işler. Verileri etkileyen diğer komutlar da, belgenizin üye işlevleri tarafından işlenebilir. Örneğin, karalama programında sınıfı, `CScribDoc` Şu anda belgede depolanan tüm verileri silen Düzenle Tümünü Düzenle komutu için bir işleyici sağlar. Belgelerde ileti haritaları olabilir, ancak görünümlerin aksine belgeler standart Windows iletilerini işleyemez, yalnızca iletileri **WM_COMMAND** veya "komutları" kullanamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri kullanma](using-documents.md)
