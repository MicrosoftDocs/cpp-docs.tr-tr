---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Message-Map çapraz başvuruyu kullanma'
title: 'Nasıl yapılır: İleti Eşleme Çapraz Başvurusunu Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
ms.openlocfilehash: 4bbc140db59a7df4abd42fdcf68b47273ec3e846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219661"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Nasıl yapılır: İleti Eşleme Çapraz Başvurusunu Kullanma

Etiketli girişlerde \<memberFxn> , türetilmiş bir [CWnd](../../mfc/reference/cwnd-class.md) sınıfı için kendi üye işlevinizi yazın. İşlevinizde dilediğiniz adı verin. Gibi diğer işlevler, `OnActivate` sınıfının üye işlevleridir `CWnd` . Çağrılırsa, iletiyi `DefWindowProc` Windows işlevine iletir. Windows bildirim iletilerini işlemek için, `CWnd` türetilmiş sınıfınıza karşılık gelen işlevi geçersiz kılın. İşleviniz, taban sınıfının ve Windows 'un iletiye yanıt vermesini sağlamak için temel sınıfınıza geçersiz kılınan işlevi çağırmalıdır.

Her durumda, işlev prototipini `CWnd` türetilmiş sınıf başlığına yerleştirin ve ileti eşleme girişini gösterildiği gibi kodlayın.

Aşağıdaki terimler kullanılır:

|Süre|Tanım|
|----------|----------------|
|kimlik|Kullanıcı tanımlı herhangi bir menü öğesi KIMLIĞI (WM_COMMAND iletileri) veya denetim KIMLIĞI (alt pencere bildirim iletileri).|
|"ileti" ve "wNotifyCode"|Windows. H 'de tanımlanan Windows ileti kimlikleri.|
|nMessageVariable|Windows işlevinden dönen değeri içeren bir değişkenin adı `RegisterWindowMessage` .|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)
