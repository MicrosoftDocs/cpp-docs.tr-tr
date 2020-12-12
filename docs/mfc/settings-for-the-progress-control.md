---
description: 'Hakkında daha fazla bilgi edinin: Ilerleme denetimi ayarları'
title: İlerleme Denetimi Ayarları
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 0cf3caa5e7b87062b1714f8e5e350840157ff7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217074"
---
# <a name="settings-for-the-progress-control"></a>İlerleme Denetimi Ayarları

İlerleme denetimi için temel ayarlar ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)), Aralık ve geçerli konumudur. Aralık işlemin tüm süresini temsil eder. Geçerli konum, uygulamanızın işlemi tamamlamaya yönelik yaptığı ilerlemeyi temsil eder. Aralık veya konumda yapılan tüm değişiklikler ilerleme denetiminin kendisini yeniden çizmesine neden olur.

Varsayılan olarak, Aralık 0-100 olarak ayarlanır ve ilk konum 0 olarak ayarlanır. İlerleme denetimi için geçerli Aralık ayarlarını almak için [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) üye işlevini kullanın. Aralığı değiştirmek için [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) member işlevini kullanın.

Konumu ayarlamak için [SetPos](../mfc/reference/cprogressctrl-class.md#setpos)kullanın. Geçerli konumu yeni bir değer belirtmeden almak için [GetPos](../mfc/reference/cprogressctrl-class.md#getpos)kullanın. Örneğin, yalnızca geçerli işlemin durumunu sorgulamak isteyebilirsiniz.

İlerleme denetiminin geçerli konumunu adım adım yapmak için [StepIt](../mfc/reference/cprogressctrl-class.md#stepit)kullanın. Her adımın miktarını ayarlamak için [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) kullanın

## <a name="see-also"></a>Ayrıca bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
