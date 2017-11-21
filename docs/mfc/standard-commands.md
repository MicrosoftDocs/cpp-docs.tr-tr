---
title: Standart komutlar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 93471fa28adf2c094b953b70daaf9c81d05047f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="standard-commands"></a>Standart Komutlar
Framework birçok standart komut iletileri tanımlar. Bu komutlar için kimlikleri genellikle form alın:  
  
 **ID_** *kaynak*_*öğesi*  
  
 Burada *kaynak* genellikle bir menü adıdır ve *öğesi* menü öğesi değil. Örneğin, yeni bir komut dosyası menüsünde komut kimliği `ID_FILE_NEW`. Standart komut kimlikleri belgelere kalın yazıyla gösterilir. Programcı tanımlı kimlikler çevresindeki metni farklı bir yazı tipi gösterilir.  
  
 Desteklenen en önemli komutları bazılarının bir listesi verilmiştir:  
  
 *Dosya menü komutları*  
 Yeni, açın, Farklı Kaydet, sayfa yapısı, yazıcı ayarları, yazdırma, Baskı Önizleme, çıkış ve en son kullanılan dosyaları kaydetme, kapatın.  
  
 *Menü komutlarını Düzenle*  
 Temizleyin, Temizle tüm, kopyalama, kesme, bulma, yapıştırma tekrarlayın, Değiştir, Tümünü Seç, geri alma ve yineleme.  
  
 *Görünüm menü komutları*  
 Araç çubuğu ve durum çubuğu.  
  
 *Pencere menü komutları*  
 Yeni, düzenleme, basamaklı, yatay döşeme, dikey döşeme ve bölme.  
  
 *Yardım menü komutları*  
 Dizin, Yardım, kullanma ve hakkında bilgi.  
  
 *OLE komutları (Düzen menüsü)*  
 Yeni bir nesne, düzenleme bağlantıları, Bağlantı Yapıştır, Özel Yapıştır eklemek ve *typename* nesne (fiil komutları).  
  
 Çerçevesi için bu komutları değişen düzeyde destek sağlar. Başkalarının kapsamlı uygulamaları ile destekleniyorsa bazı komutlar yalnızca tanımlanmış komut kimlikleri desteklenir. Örneğin, framework Aç komutu Dosya menüsünde yeni bir belge nesnesi oluşturma, açık bir iletişim kutusu, görüntüleme ve açma ve dosya okuyarak uygular. Buna karşılık, Düzen menüsündeki komutlar kendiniz komutları gibi bu yana uygulamanız gereken **ıd_edıt_copy** kopyaladığınız veri yapısına bağlıdır.  
  
 Desteklenen komutları hakkında daha fazla bilgi ve sağlanan uygulama düzeyi için bkz: [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md). Standart komutlar AFXRES dosyasında tanımlanır. H.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi nesneleri ve komut kimlikleri](../mfc/user-interface-objects-and-command-ids.md)

