---
title: Standart Komutlar
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
ms.openlocfilehash: fa98a250e6f9de3005cf4978fe66689363865879
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485702"
---
# <a name="standard-commands"></a>Standart Komutlar

Framework standart komut ileti sayısını tanımlar. Bu komutlar için kimlikleri genellikle biçiminde:

**ID_** *kaynak*_*öğesi*

Burada *kaynak* genellikle bir menü adıdır ve *öğesi* menü öğesidir. Örneğin, Dosya menüsündeki yeni komutu için komut kimliği ıd_fıle_new olur. Standart komut kimlikleri belgeleri kalın yazıyla gösterilir. Programcı tanımlı kimlikler çevreleyen metni farklı bir yazı tipi gösterilir.

Desteklenen en önemli komutların bir listesi verilmiştir:

*Dosya menü komutları*<br/>
Yeni, açın, Farklı Kaydet, sayfa yapısı, Yazdırma Kurulumu, yazdırma, Baskı Önizleme, çıkış ve en son kullanılan dosyaları kaydedin, kapatın.

*Menü komutlarını Düzenle*<br/>
Temizleyin, Clear tüm, kopyalama, kesme, bulma, yapıştırma, tekrarlayın, Değiştir, Tümünü Seç, Geri Al ve Yinele.

*Görünüm Menü Komutları*<br/>
Araç çubuğu ve durum çubuğu.

*Pencere Menü Komutları*<br/>
Yeni, düzenleme, basamaklı, Yatay Döşe, Dikey Döşe ve bölme.

*Yardım Menü Komutları*<br/>
Dizin, Yardım, kullanma ve ilgili.

*OLE komutları (Düzenle menüsü)*<br/>
Yeni nesne, Edit Links, Yapıştır, Özel Yapıştır eklemek ve *typename* nesnesi (komut Fiili).

Framework, bu komutları için farklı düzeylerde destek sağlar. Başkalarının kapsamlı uygulamaları ile desteklendiğinden, bazı komutlar tanımlı komut kimlikleri yalnızca desteklenir. Örneğin, framework Aç komutunu Dosya menüsünden Yeni bir belge nesnesi oluşturma, açık bir iletişim kutusu, görüntüleme ve açma ve dosya okunurken uygular. Buna karşılık, komutları Düzen menüsünden kendiniz uygulamanız gereken, verilerin niteliğine ıd_edıt_copy gibi komutlar bağlı olduğundan kopyalama.

Desteklenen komutlar hakkında daha fazla bilgi ve sağlanan uygulama düzeyi için bkz: [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md). Standart komutlar AFXRES dosyasında tanımlanır. H

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)

