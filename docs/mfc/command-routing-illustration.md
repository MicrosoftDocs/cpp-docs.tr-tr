---
title: Komut Yönlendirme Çizimi
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 56d131151f2284f12a3b46a9acd3cfbd3c8b0f47
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304645"
---
# <a name="command-routing-illustration"></a>Komut Yönlendirme Çizimi

Göstermek için Tümünü Temizle'yi menü öğesi MDI uygulamanın Düzen menüsündeki komutu iletiden göz önünde bulundurun. Bu komut işleyici işlevi uygulamanın belge sınıfının üye işlevinde özelleştirmede varsayalım. Kullanıcı menü öğesini seçtikten sonra bu komut, işleyici nasıl ulaştığında aşağıda verilmiştir:

1. Ana çerçeve penceresinin ilk komut iletiyi alır.

1. Ana MDI çerçevesi penceresi etkin MDI alt penceresi komutunu işlemek için bir şans verir.

1. Standart bir MDI alt çerçeve penceresi yönlendirme, görünüm şansı komut kendi ileti eşlemesi denetlemeden önce sağlar.

1. Görünüm kendi ileti eşlemesi ilk denetler ve hiçbir işleyicisi bulma sonraki komut, ilişkili belge için yönlendirir.

1. Belge, ileti eşlemesi denetler ve bir işleyici bulur. Bu belge üye işlevi çağrılan ve yönlendirmeyi durdurur.

Belgenin bir işleyici değilse, bu komutu, belge şablonuna sonraki rota. Ardından komutu, Görünüm ve ardından çerçeve penceresi döndürecektir. Son olarak, çerçeve penceresinin kendi ileti eşlemesi denetler. Bu onay de başarısız olursa komutu ana MDI çerçevesi penceresi dönün ve ardından uygulama nesnesi yönlendirilirdi — işlenmemiş komutları ultimate hedefi.

## <a name="see-also"></a>Ayrıca bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)
