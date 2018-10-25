---
title: Rebar denetimiyle birlikte bir iletişim çubuğu kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9d4155fec333061c65f148f29e849dc4717f0d2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073767"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

