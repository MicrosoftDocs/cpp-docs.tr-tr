---
title: Rebar Denetimiyle Birlikte Bir İletişim Çubuğu Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
ms.openlocfilehash: e4e786d3670ec74b734739e29aa7e3e33b5af384
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302373"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir İletişim Çubuğu Kullanma

[Rebar denetimlerinde ve bantlarında](../mfc/rebar-controls-and-bands.md)belirtildiği gibi, her bant yalnızca bir alt pencere (veya denetim) içerebilir. Bant başına birden fazla alt pencere olmasını istiyorsanız bu bir sınırlama olabilir. Kullanışlı bir geçici çözüm, birden fazla denetim içeren bir iletişim çubuğu kaynağı oluşturmak ve ardından yeniden çubuk şeridi (iletişim çubuğunu içeren) yeniden çubuk denetimine eklemektir.

Normal olarak, iletişim çubuğu bandın saydam görünmesini istiyorsanız, iletişim çubuğu nesnesi için WS_EX_TRANSPARENT genişletilmiş stilini ayarlarsınız. Ancak, WS_EX_TRANSPARENT bir iletişim çubuğunun arka planını doğru şekilde boyamaya yönelik bazı sorunlar olduğundan, istenen etkiyi elde etmek için biraz daha fazla iş yapmanız gerekir.

Aşağıdaki yordamda WS_EX_TRANSPARENT genişletilmiş stilini kullanmadan saydamlık elde etmek için gereken adımlar ayrıntılı olarak verilmiştir.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Bir yeniden çubuk bandında saydam bir iletişim çubuğu uygulamak için

1. [Sınıf Ekle iletişim kutusunu](../mfc/reference/adding-an-mfc-class.md)kullanarak iletişim çubuğu nesnesini uygulayan yeni bir sınıf (örneğin, `CMyDlgBar`) ekleyin.

1. WM_ERASEBKGND ileti için bir işleyici ekleyin.

1. Yeni İşleyicide, mevcut kodu aşağıdaki örnekle eşleşecek şekilde değiştirin:

   [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. WM_MOVE ileti için bir işleyici ekleyin.

1. Yeni İşleyicide, mevcut kodu aşağıdaki örnekle eşleşecek şekilde değiştirin:

   [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Yeni işleyiciler, WM_ERASEBKGND iletisini ana pencereye ileterek iletişim çubuğu saydamlığının benzetimini yapar ve iletişim çubuğu nesnesi taşındığında her seferinde yeniden çizmeyi zorluyor.

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
