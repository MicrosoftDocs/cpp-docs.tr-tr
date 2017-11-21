---
title: "Bağlayıcı araçları hatası LNK1112 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1112
dev_langs: C++
helpviewer_keywords: LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8353c8e6baf8072ee45acaa3f4635bc333c03add
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1112"></a>Bağlayıcı Araçları Hatası LNK1112
Modül makine türü 'type1' hedef makine türü 'type2' çakışıyor  
  
 Girdi olarak belirtilen nesneyi dosyalar için farklı bir bilgisayara türleri derlendi.  
  
 Bağlantı çalışırsanız, örneğin, bir nesne ile derlenmiş dosyası **/CLR** ve bir nesne dosyası ile derlenmiş **/CLR: Saf** (makine türü CEE), bağlayıcı hatası LNK1112 oluşturacaktır.  
  
 Benzer şekilde, bir modülü ile oluşturursanız [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleyici ve x86 sahip başka bir modül derleyici ve bunları bağlamak için try bağlayıcı LNK1112 oluşturur.  
  
 Bu hatanın olası bir neden, 64 bitlik bir uygulama geliştirme ancak Visual C++ 64 bit derleyicileri birini yüklemediyseniz ' dir. Bu durumda, 64-bit yapılandırmaları kullanılabilir olmaz. Bu sorunu düzeltmek için Visual Studio için yükleyiciyi çalıştırın ve eksik C++ bileşenlerini yükleyin.  
  
 Değiştirirseniz bu hata ayrıca oluşabilir **etkin çözüm yapılandırması** içinde **Configuration Manager** ve Ara proje dosyalarını silmeden önce projeyi derlemek deneyin. Bu hatayı gidermek için seçin **çözümü yeniden derle** gelen **yapı** menüsü. Öğesini de seçebilirsiniz **temiz çözüm** gelen **yapı** menüsüne ve ardından yapı çözümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı araçları hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)