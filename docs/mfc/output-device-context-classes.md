---
title: Çıktı (cihaz bağlamı) sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.output
dev_langs:
- C++
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40b1406e8c788554d549ee1bdaa1adc21070d994
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373561"
---
# <a name="output-device-context-classes"></a>Çıktı (Cihaz Bağlamı) Sınıfları

Bu sınıfların cihaz bağlamlarında kullanılabilir Windows farklı türde kapsüller.

Aşağıdaki sınıflar çoğu Windows cihaz bağlamı için bir tanıtıcı kapsüller. Bir cihaz bağlamı bir cihazın bir görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi içeren bir Windows nesnesidir. Tüm çizim çağrıları, bir cihaz bağlamındaki nesne ile yapılır. Türetilen sınıflar ek `CDC` Windows Meta dosyası da dahil olmak üzere, özel bir cihaz bağlamı işlevselliğini kapsüller.

[CDC](../mfc/reference/cdc-class.md)<br/>
Cihaz bağlamları için temel sınıf. Tüm görüntü erişmek için doğrudan ve yazıcılar gibi nondisplay bağlamlarda erişmek için kullanılır.

[CPaintDC](../mfc/reference/cpaintdc-class.md)<br/>
Kullanılan bir görüntü bağlamı `OnPaint` windows üye işlevleri. Otomatik olarak çağıran `BeginPaint` yapı üzerinde ve `EndPaint` etme.

[CClientDC](../mfc/reference/cclientdc-class.md)<br/>
Windows istemci alanları görüntüleme bağlamı. Örneğin, fare olaylara anında bir yanıt çizmek için kullanılır.

[CWindowDC](../mfc/reference/cwindowdc-class.md)<br/>
Hem istemci hem de istemci olmayan alanları dahil olmak üzere tüm windows görüntüleme bağlamı.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md)<br/>
Windows Meta dosyası için bir cihaz bağlamı. Bir Windows Meta dosyası bir görüntü oluşturmak için yeniden grafik cihaz arabirimi (GDI) komutları dizisini içerir. Üye işlevleri için yapılan çağrıları bir `CMetaFileDC` meta dosyasının içine kaydedilir.

## <a name="related-classes"></a>İlgili sınıflar

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Koordinat (x, y) çiftleri tutar.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Uzaklık, göreli konumlarını veya eşleştirilmiş değerleri tutar.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Dikdörtgen alanları koordinatlarını içerir.

[CRgn](../mfc/reference/crgn-class.md)<br/>
Elips, çokgen veya düzensiz bir alan bir pencere içinde düzenlemek için bir GDI bölgesi kapsüller. Kırpma üye işlevler sınıfında ile birlikte kullanılan `CDC`.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Görüntüler ve yeniden boyutlandırma ve dikdörtgen nesneleri taşımak için kullanıcı arabirimi işler.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
Bir renk seçmek için bir standart iletişim kutusu sağlar.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
Standart iletişim kutusu, yazı tipi seçmek için sağlar.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Dosya yazdırma için standart bir iletişim kutusu sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

