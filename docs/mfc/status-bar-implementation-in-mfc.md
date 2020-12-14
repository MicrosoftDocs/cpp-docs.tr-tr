---
description: "Daha fazla bilgi edinin: MFC 'de durum çubuğu uygulama"
title: MFC'de Durum Çubuğu Uygulaması
ms.date: 11/19/2018
f1_keywords:
- COldStatusBar
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
ms.openlocfilehash: d42f8b4bf6ae72cf8eb4a12d1f5eafb8603c5e1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216762"
---
# <a name="status-bar-implementation-in-mfc"></a>MFC'de Durum Çubuğu Uygulaması

Bir [CStatusBar](../mfc/reference/cstatusbar-class.md) nesnesi, bir metin çıkış bölmesi satırı içeren bir denetim çubuğudur. Çıkış bölmeleri genellikle ileti satırları ve durum göstergeleri olarak kullanılır. Örnek olarak, seçilen menü komutu ve SCROLL LOCK, NUM LOCK ve diğer anahtarların durumunu gösteren göstergeler kısaca açıklayan menü yardım-ileti satırları bulunur.

MFC sürüm 4,0 itibariyle durum çubukları, bir durum çubuğu ortak denetimini kapsülleyen [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)sınıfı kullanılarak uygulanır. Ters uyumluluk için MFC, sınıfında eski durum çubuğu uygulamasını korur `COldStatusBar` . MFC 'nin önceki sürümlerine yönelik belgeler altında açıklanmaktadır `COldStatusBar` `CStatusBar` .

MFC 4,0 ' ye yeni bir üye işlevi olan [CStatusBar:: GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), durum çubuğu özelleştirmesi ve ek Işlevler için Windows ortak denetim desteğinden yararlanmanızı sağlar. `CStatusBar` üye işlevleri, Windows ortak denetimleri işlevlerinin çoğunu sağlar; Ancak, öğesini çağırdığınızda durum `GetStatusBarCtrl` çubuklarınızın durum çubuğunun özelliklerine daha da fazlasına sahip olabilirsiniz. `GetStatusBarCtrl`Öğesini çağırdığınızda, bir nesnesine bir başvuru döndürür `CStatusBarCtrl` . Bu başvuruyu durum çubuğu denetimini işlemek için kullanabilirsiniz.

Aşağıdaki şekilde, çeşitli göstergeler görüntüleyen bir durum çubuğu gösterilmektedir.

![Durum çubuğu](../mfc/media/vc37dy1.gif "Durum çubuğu") <br/>
Bir durum çubuğu

Araç çubuğu gibi, durum çubuğu nesnesi üst çerçeve penceresine katıştırılır ve çerçeve penceresi oluşturulduğunda otomatik olarak oluşturulur. Tüm denetim çubukları gibi durum çubuğu, üst çerçeve yok edildiğinde otomatik olarak yok edilir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Durum çubuğu bölmesinin metnini güncelleştirme](../mfc/updating-the-text-of-a-status-bar-pane.md)

- MFC sınıfları [CStatusBar](../mfc/reference/cstatusbar-class.md) ve [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [Denetim çubukları](../mfc/control-bars.md)

- [İletişim kutusu çubukları](../mfc/dialog-bars.md)

- [Araç çubukları (MFC araç çubuğu uygulama)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>Ayrıca bkz.

[Durum çubukları](../mfc/status-bars.md)
