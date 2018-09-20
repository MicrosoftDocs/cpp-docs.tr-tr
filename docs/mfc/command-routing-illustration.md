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
ms.openlocfilehash: 46449a90223bdb5e7774d4be5710014ff2c6ccae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406080"
---
# <a name="command-routing-illustration"></a>Komut Yönlendirme Çizimi

Göstermek için Tümünü Temizle'yi menü öğesi MDI uygulamanın Düzen menüsündeki komutu iletiden göz önünde bulundurun. Bu komut işleyici işlevi uygulamanın belge sınıfının üye işlevinde özelleştirmede varsayalım. Kullanıcı menü öğesini seçtikten sonra bu komut, işleyici nasıl ulaştığında aşağıda verilmiştir:

1. Ana çerçeve penceresinin ilk komut iletiyi alır.

1. Ana MDI çerçevesi penceresi etkin MDI alt penceresi komutunu işlemek için bir şans verir.

1. Standart bir MDI alt çerçeve penceresi yönlendirme, görünüm şansı komut kendi ileti eşlemesi denetlemeden önce sağlar.

1. Görünüm kendi ileti eşlemesi ilk denetler ve hiçbir işleyicisi bulma sonraki komut, ilişkili belge için yönlendirir.

1. Belge, ileti eşlemesi denetler ve bir işleyici bulur. Bu belge üye işlevi çağrılan ve yönlendirmeyi durdurur.

Belgenin bir işleyici değilse, bu komutu, belge şablonuna sonraki rota. Ardından komutu, Görünüm ve ardından çerçeve penceresi döndürecektir. Son olarak, çerçeve penceresinin kendi ileti eşlemesi denetler. Bu onay de başarısız olursa komutu ana MDI çerçevesi penceresi dönün ve ardından uygulama nesnesi yönlendirilirdi — işlenmemiş komutları ultimate hedefi.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

