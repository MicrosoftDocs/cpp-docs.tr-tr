---
title: MFC'de durum çubuğu uygulaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COldStatusBar
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e593227daabb2d2c25d593cfb58ef23ba7855be7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436721"
---
# <a name="status-bar-implementation-in-mfc"></a>MFC'de Durum Çubuğu Uygulaması

A [CStatusBar](../mfc/reference/cstatusbar-class.md) nesnedir metin çıkış bölmeleri satırına sahip bir denetim çubuğu. Çıkış bölmeleri, ileti satırları ve durum göstergesi olarak sık kullanılan bloblardır. Seçili bir menü komutunu kısaca açıklayan menü yardım iletisini satırları ve SCROLL LOCK, NUM LOCK ve diğer anahtarlar durumunu gösteren göstergeleri verilebilir.

MFC sürüm 4.0 itibariyle durum çubukları sınıfı kullanılarak uygulanır [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), bir durum çubuğu ortak denetim kapsüller. Geriye dönük uyumluluk için eski durum çubuğu uygulaması sınıfında MFC korur `COldStatusBar`. Önceki sürümlerdeki MFC için belgelerde `COldStatusBar` altında `CStatusBar`.

[CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), bir üye işlevi yeni MFC 4.0 için durum çubuğu özelleştirme ve ek işlevsellik için Windows ortak denetim destek avantajlarından yararlanmanıza olanak tanır. `CStatusBar` üye işlevleri, çoğu Windows ortak denetimleri işlevlerini sağlar; Ancak, çağırdığınızda `GetStatusBarCtrl`, durum çubuğu özellikleri daha da, durum çubukları verebilirsiniz. Çağırdığınızda `GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` nesne. Bu başvuru, durum çubuğu denetimi yönetmek için kullanabilirsiniz.

Aşağıdaki şekilde birkaç göstergeleri gösteren bir durum çubuğu gösterir.

![Durum çubuğu](../mfc/media/vc37dy1.gif "vc37dy1") bir durum çubuğu

Araç çubuğu gibi durum çubuğu nesne kendi üst çerçeve penceresinde katıştırılır ve çerçeve penceresi oluşturulduğunda otomatik olarak oluşturulur. Üst çerçevenin kaldırıldığında durum çubuğu, tüm denetim çubukları gibi otomatik olarak de yok edilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Durum çubuğu bölmesinin metnini güncelleştirme](../mfc/updating-the-text-of-a-status-bar-pane.md)

- MFC sınıfları [CStatusBar](../mfc/reference/cstatusbar-class.md) ve [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [Denetim çubukları](../mfc/control-bars.md)

- [İletişim kutusu çubukları](../mfc/dialog-bars.md)

- [Araç çubukları (MFC araç çubuğu uygulaması)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Durum Çubukları](../mfc/status-bars.md)

