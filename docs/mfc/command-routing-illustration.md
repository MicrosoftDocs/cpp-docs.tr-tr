---
title: Komut yönlendirme çizimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a12a5cd19177761dfbf484c64f528d8def194ca5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="command-routing-illustration"></a>Komut Yönlendirme Çizimi
Göstermek için Tümünü Temizle'yi menü öğesi MDI uygulamanın Düzenle menüsünde komutu iletiden göz önünde bulundurun. Uygulamanın belge sınıfının üye işlevini olması için bu komut işleyici işlevi olur varsayalım. Menü öğesi kullanıcı seçtikten sonra bu komut, işleyici nasıl ulaştığında aşağıda verilmiştir:  
  
1.  Ana çerçeve penceresi ilk komut iletisi alır.  
  
2.  Ana MDI çerçeve penceresi şu anda etkin MDI alt pencere komutu işlemek için bir fırsat sunar.  
  
3.  MDI alt çerçeve penceresi standart yönlendirme kendi görünüm şansı komutunun kendi ileti eşlemesi denetlemeden önce sağlar.  
  
4.  Görünüm kendi ileti eşlemesi ilk denetler ve hiçbir işleyici bulma sonraki komutu, ilişkili belgeyi yönlendirir.  
  
5.  Belge kendi ileti eşlemesi denetler ve bir işleyici bulur. Bu belge üye işlev çağrılır ve yönlendirme durdurur.  
  
 Belge bir işleyiciye sahip değil, bu komut, belge şablonu sonraki rota. Ardından komutu Görünüm ve ardından çerçeve penceresi döndürecektir. Son olarak, çerçeve penceresi kendi ileti eşlemesi denetler. Bu onay de başarısız olursa komutu geri ana MDI çerçeve penceresi ve ardından uygulama nesnesi yönlendirilecektir — işlenmemiş komutların ultimate hedef.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

