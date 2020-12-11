---
description: 'Hakkında daha fazla bilgi edinin: komut yönlendirme çizimi'
title: Komut Yönlendirme Çizimi
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 51c5182eb1fa2a8b9666e265526e9220a9f3d4a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159966"
---
# <a name="command-routing-illustration"></a>Komut Yönlendirme Çizimi

Göstermek için bir MDI uygulamasının düzenleme menüsündeki bir tümünü temizle menü öğesinden bir komut iletisi düşünün. Bu komutun işleyici işlevinin, uygulamanın belge sınıfının bir üye işlevi olacağını varsayalım. Kullanıcı menü öğesini seçtikten sonra bu komutun işleyicisine nasıl ulaşıyorsa aşağıda verilmiştir:

1. Ana çerçeve penceresi önce komut iletisini alır.

1. Ana MDI çerçevesi penceresi, şu anda etkin olan MDI alt penceresine komutu işlemek için bir şans sağlar.

1. Bir MDI alt çerçeve penceresinin standart yönlendirmesi, kendi ileti eşlemesini denetlemeden önce komutta bir şans sağlar.

1. Görünüm, kendi ileti eşlemesini denetler ve hiçbir işleyici bulmuyor, sonra komutu ilişkili belgesine yönlendirir.

1. Belge, ileti eşlemesini denetler ve bir işleyici bulur. Bu belge üyesi işlevi çağrıldı ve yönlendirme durdu.

Belgenin bir işleyicisi yoksa, daha sonra komutu belge şablonuna yönlendirmenize olanak sağlar. Ardından komut, görünüme ve sonra çerçeve penceresine geri döner. Son olarak, çerçeve penceresi ileti haritasını denetleyebilir. Bu denetim de başarısız olursa, komut ana MDI çerçevesi penceresine ve ardından Uygulama nesnesine (işlenmemiş komutların en son hedefi) yönlendirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
