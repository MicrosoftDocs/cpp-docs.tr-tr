---
title: Rebar Denetimiyle Birlikte Bir İletişim Çubuğu Kullanma
ms.date: 11/04/2016
f1_keywords:
- WM_EX_TRANSPARENT
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
ms.openlocfilehash: 33ca3d0a7bf2e60511ea0048ad91b1f0930a2894
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287181"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir İletişim Çubuğu Kullanma

Belirtildiği gibi [Rebar denetimleri ve bantları](../mfc/rebar-controls-and-bands.md), her bant yalnızca bir alt pencere (veya Denetim) içerebilir. Bant başına birden fazla alt penceresi istiyorsanız bu bir kısıtlama olabilir. Uygun bir geçici çözüm, birden çok denetimleri ile bir iletişim çubuğu kaynağı oluşturma ve ardından çubuk barınağı denetimi (iletişim çubuğu içeren) bir çubuk barınağı bant eklemektir.

Normalde, saydam görünmesine iletişim çubuğu bant istediyseniz, iletişim çubuğu nesnesi için genişletilmiş WS_EX_TRANSPARENT ayarlayın. Ancak, düzgün bir iletişim çubuğu arka plan boyama bazı sorunlar WS_EX_TRANSPARENT sahip olduğundan, istenilen etkiyi elde etmek için küçük bir ek iş yapması gerekir.

Aşağıdaki yordam ayrıntıları WS_EX_TRANSPARENT kullanmadan saydamlık sağlamak için gerekli adımları genişletilmiş stili.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Bir rebar bant saydam iletişim çubuğu uygulamak için

1. Kullanarak [Sınıf Ekle iletişim kutusu](../mfc/reference/adding-an-mfc-class.md), yeni bir sınıf ekleyin (örneğin, `CMyDlgBar`), iletişim çubuğu nesnenizin uygular.

1. WM_ERASEBKGND ileti işleyicisi ekleyin.

1. Yeni işleyicisinde varolan kodu aşağıdaki örnekle eşleşecek şekilde değiştirin:

   [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. WM_MOVE ileti işleyicisi ekleyin.

1. Yeni işleyicisinde varolan kodu aşağıdaki örnekle eşleşecek şekilde değiştirin:

   [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Yeni işleyicileri, ana pencereyi WM_ERASEBKGND iletiyi iletme ve iletişim çubuğu nesne taşındı her zaman yeniden çizmeyi zorlama iletişim çubuğu saydamlığını benzetimini yapın.

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
