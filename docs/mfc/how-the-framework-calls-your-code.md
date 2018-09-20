---
title: Framework'ün kodunuzu çağırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68db9107a8d2d113e9118c9cf125acb2798edcd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373876"
---
# <a name="how-the-framework-calls-your-code"></a>Framework'ün Kodunuzu Çağırması

Kaynak kodunuzu ve MFC çerçevesi kodda arasındaki ilişkiyi anlamak önemlidir. Uygulamanız çalışırken, denetim akışı çoğunu framework'ün kodda yer alıyor. Kullanıcı komutları seçer ve bir görünümdeki veriler düzenler, Windows iletileri alır ileti döngüsü framework yönetir. Framework, tek başına işleyebileceği olayları kodunuz üzerinde hiç güvenmeyin. Örneğin, çerçeve pencereleri kapatın ve yanıt kullanıcı komutları için uygulamadan çıkın bilir. Bu görevleri işler gibi framework fırsatlar de bu olaylara yanıt vermek için ileti işleyicileri ve C++ sanal işlevleri kullanır. Kodunuz denetiminde değildir, ancak:; çerçevedir.

Framework, uygulamaya özgü olaylar için kodunuzu çağırır. Örneğin, kullanıcı bir menü komutu seçtiğinde framework komut C++ nesnelerinin bir dizisi boyunca yönlendirir: Geçerli Görünüm ve çerçeve penceresi, görünüm, belgenin belge şablonu ve uygulama nesnesi ile ilişkili belge. Bu nesnelerden birini komutu işleyebilir, bunu mu uygun ileti işleyicisi işlevini çağırarak. Verilen komutlardan herhangi birine, çağrılan kodu size ait olabileceğini veya framework'ün olabilir.

Bu düzenleme Windows için geleneksel programlama veya olay kaynaklı programlama ile karşılaşmış programcıları için biraz bilgi sahibi olur.

İlgili konulardaki ne framework olarak başlatır ve uygulamayı çalıştırır ve ardından uygulama sonlanana olarak temizler okur. Ayrıca, yazdığınız kodun nereye sığacak anlayacaksınız.

Daha fazla bilgi için [sınıfı CWinApp: uygulama sınıfı](../mfc/cwinapp-the-application-class.md) ve [belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'te Derleme](../mfc/building-on-the-framework.md)

