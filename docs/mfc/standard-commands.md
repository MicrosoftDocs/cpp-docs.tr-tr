---
description: 'Daha fazla bilgi edinin: standart komutlar'
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
ms.openlocfilehash: 09c0afecf5b34565c3ab14e276c7c43a20189a0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216749"
---
# <a name="standard-commands"></a>Standart Komutlar

Framework birçok standart komut iletisini tanımlar. Bu komutların kimlikleri genellikle şu biçimde olacaktır:

**ID_** *Source* _ *öğesi*

Burada *kaynak* genellikle bir menü adıdır ve *öğe* bir menü öğesidir. Örneğin, Dosya menüsündeki yeni komut için komut KIMLIĞI ID_FILE_NEW. Standart komut kimlikleri belgelerde kalın tür olarak gösterilir. Programcı tanımlı kimlikler, çevreleyen metinden farklı bir yazı tipinde gösterilir.

Aşağıda, desteklenen en önemli komutların bazıları listelenmiştir:

*Dosya menü komutları*<br/>
Yeni, açma, kapatma, kaydetme, farklı kaydet, sayfa kurulumu, yazdırma ayarları, yazdırma, baskı önizleme, çıkış ve en son kullanılan dosyalar.

*Menü komutlarını Düzenle*<br/>
Temizle, tümünü temizle, Kopyala, kes, bul, Yapıştır, Yinele, Değiştir, Tümünü Seç, geri al ve Yinele.

*Menü komutlarını görüntüle*<br/>
Araç çubuğu ve durum çubuğu.

*Pencere menüsü komutları*<br/>
Yeni, Düzenle, basamakla, döşeme yatay, döşeme dikey ve bölme.

*Yardım menüsü komutları*<br/>
Dizin, yardım ve hakkında.

*OLE komutları (düzenleme menüsü)*<br/>
Yeni nesne Ekle, bağlantıları Düzenle, Yapıştır bağlantısı, özel ve *TypeName* nesnesi (fiil komutları).

Framework, bu komutlar için farklı destek düzeyleri sağlar. Bazı komutlar yalnızca tanımlı komut kimlikleri olarak desteklenir, diğerleri ise kapsamlı uygulamalarla desteklenir. Örneğin, çerçeve yeni bir belge nesnesi oluşturarak, bir Aç iletişim kutusu görüntüleyerek ve dosyayı açıp okurken Dosya menüsünde Aç komutunu uygular. Bunun aksine, düzenleme menüsünde komutları uygulamanız gerekir, çünkü ID_EDIT_COPY gibi komutlar kopyaladığınız verilerin yapısına bağlıdır.

Desteklenen komutlar ve belirtilen uygulama düzeyi hakkında daha fazla bilgi için bkz. [Teknik notun 22](../mfc/tn022-standard-commands-implementation.md). Standart komutlar, AFXRES. H dosyasında tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi nesneleri ve komut kimlikleri](../mfc/user-interface-objects-and-command-ids.md)
