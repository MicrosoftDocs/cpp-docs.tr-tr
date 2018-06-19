---
title: Dizi, liste ve eşleme sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41dfe0b36548d87b5e0501c557e70f3cf11eea5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345299"
---
# <a name="array-list-and-map-classes"></a>Dizi, Liste ve Eşleme Sınıfları
Toplamalar veri işleme için bir grup koleksiyon sınıflarının sınıf kitaplığı sağlar — diziler, listeler ve eşler — çeşitli nesne ve önceden tanımlanmış türleri tutun. Koleksiyonları dinamik olarak boyutlandırılır. Bu sınıfların herhangi bir programda veya Windows için yazılmış olup olmadığını kullanılabilir. Ancak, bunlar uygulama çerçevesi, belge sınıflarının tanımlanması veri yapılarını uygulamak için en kullanışlıdır. Kullanıma özel koleksiyon sınıfları bunlardan türetilemeyeceğini veya bunları şablonu sınıflara göre oluşturabilirsiniz. Makaleyi Bu yaklaşımlar hakkında daha fazla bilgi için bkz: [koleksiyonları](../mfc/collections.md). Makale şablonu koleksiyon sınıfları listesi için bkz [diziler, listeler ve eşlemeler için şablon sınıfları](../mfc/template-classes-for-arrays-lists-and-maps.md).  
  
 Bitişik bellekte depolanır tek boyutlu veri yapılarını dizidir. Bir öğenin boyutunu tarafından öğenin dizini çarparak ve dizi temel adres için sonuç ekleyerek verilen herhangi bir öğe bellek adresini hesaplanabilir bu yana çok hızlı rastgele erişim destekledikleri. Ancak diziler diziye öğe eklemek varsa, tüm dizi bu yana geçen eklenecek öğe yer açmak amacıyla taşınacak eklenen öğeye sahip çok pahalı. Diziler büyür ve gerektiğinde daraltma.  
  
 Listeleri diziler için benzer, ancak çok farklı bir şekilde depolanır. Her bir öğe listesini karakteriyle bağlantılı listesini yapmadan önceki ve sonraki öğeleri için bir işaretçi de içerir. Eklemek veya Bunun yapılması yalnızca birkaç işaretçileri değiştirme içerdiğinden öğeleri silmek için çok hızlıdır. Tüm aramaları listenin uçlarından biri başlatmak gerektiğinden ancak listesini arama pahalı olabilir.  
  
 MAPS bir anahtar değeri için veri değeri ilgilidir. Örneği için bir harita anahtar dize ve veri listeye bir işaretçi olabilir. Belirli bir dizeyle ilişkili işaretçi size eşlemek isteyin. Harita aramaları hızlı olduklarından eşlemeleri karma tabloları anahtar aramaları için kullanın. Öğelerini eklemeyi ve silmeyi de hızlıdır. MAPS, genellikle diğer veri yapılarını yardımcı dizinlerini kullanılır. MFC kullanan özel türde bir harita adlı bir [ileti eşlemesi](../mfc/mapping-messages.md) Windows iletilerini ileti işleyicisi işlevi için bir işaretçi eşlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

