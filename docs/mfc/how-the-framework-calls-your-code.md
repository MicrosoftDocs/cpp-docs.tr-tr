---
title: Framework kodunuzu çağırması | Microsoft Docs
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
ms.openlocfilehash: f746ce3c3d658ab1dccc098939410b52d91b1188
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348185"
---
# <a name="how-the-framework-calls-your-code"></a>Framework'ün Kodunuzu Çağırması
Kaynak kodunuz ve MFC çerçevesi kodda arasındaki ilişkiyi anlamak önemlidir. Uygulamanızı çalıştığında, denetim akışını çoğunu framework'ün kodda yer alıyor. Framework'te kullanıcı komutları seçer ve bir görünümündeki verileri düzenler gibi Windows iletilerini alır ileti döngüsü yönetir. Framework tek başına işleyebilir olayları kodunuz üzerinde hiç kullanmayın. Örneğin, çerçeve pencereleri kapatın ve kullanıcı komutlarına yanıt olarak uygulamadan çıkmak bilir. Bu görevleri işleme gibi framework fırsatlar bu olaylarına yanıt vermek için ileti işleyicileri ve C++ sanal işlevleri kullanır. Kodunuz denetiminde değildir, ancak:; çerçevedir.  
  
 Framework kodunuz için uygulamaya özgü olaylar çağırır. Örneğin, kullanıcı menü komutu seçtiğinde framework komut C++ nesnelerinin bir dizisi boyunca yönlendirir: Geçerli Görünüm ve çerçeve penceresi, görünüm, belgenin belge şablonu ve uygulama nesnesi ile ilişkili belge. Bu nesnelerden birini komutu işleyebilecek varsa, bunu, yapar uygun ileti işleyicisi işlevi çağırma. Verilen her komut için çağrılan kodu size ait olabilir veya framework'ün olabilir.  
  
 Bu düzenlemenin Windows için geleneksel programlama veya olay kaynaklı programlama ile karşılaşmış programcıları için biraz bilgi sahibi olur.  
  
 İlgili Konular bölümünde ne framework olarak başlatır ve uygulamayı çalıştırır ve ardından uygulama sonlanana gibi temizler okur. Ayrıca, burada yazdığınız kodları sığacak anlayacaksınız.  
  
 Daha fazla bilgi için bkz: [sınıfı CWinApp: uygulama sınıfı](../mfc/cwinapp-the-application-class.md) ve [belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'te Derleme](../mfc/building-on-the-framework.md)

