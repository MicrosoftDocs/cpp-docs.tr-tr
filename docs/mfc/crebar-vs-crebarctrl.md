---
title: CReBar ile CReBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6133e298cd0bc5b497fbbba47982a755afeefb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442857"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar ile CReBarCtrl

MFC rebars oluşturmak için iki sınıflar sağlar: [CReBar](../mfc/reference/crebar-class.md) ve [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CReBar` Tüm ortak çubuk barınağı denetimi işlevlerini sağlar ve bu gerekli ortak denetim ayarları ve yapıları çoğunu sizin yerinize çözer.

`CReBarCtrl` Win32 çubuk barınağı şeritleri için bir sarmalayıcı sınıftır ve bu nedenle çubuk barınağı MFC mimarisine tümleştirmek düşünmüyorsanız uygulamak daha kolay olabilir. Kullanmayı planlıyorsanız `CReBarCtrl` ve MFC mimarisine çubuk barınağı tümleştirin, çubuk barınağı denetimi işlemeleri MFC iletişim kurmak için daha da dikkatli göz önüne almanız gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda, gereksiz ek çalışma gerekir `CReBar`.

Visual C++ çubuk barınağı ortak denetimi yararlanmak için iki yol sunar.

- Çubuk barınağı kullanarak oluşturduğunuz `CReBar`ve sonra çağrı [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) erişim elde etmek için `CReBarCtrl` üye işlevleri.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` bıraktığı bir satır içi üye işlevi olan **bu** çubuk barınağı nesne işaretçisi. Bu, çalışma zamanında işlev çağrısı zahmetine olduğu anlamına gelir.

- Çubuk barınağı kullanarak oluşturduğunuz [CReBarCtrl](../mfc/reference/crebarctrl-class.md)'s Oluşturucusu.

Her iki yöntem için çubuk barınağı denetimi üye işlevleri sürümlere erişmenizi sağlayacaktır. Çağırdığınızda `CReBar::GetReBarCtrl`, bir başvuru döndürür bir `CReBarCtrl` ayarlayın ya da üye işlevleri kullanabilmeniz için nesne. Bkz: [CReBar](../mfc/reference/crebar-class.md) oluşturma ve kullanarak bir çubuk barınağı oluşturma hakkında bilgi `CReBar`.

## <a name="see-also"></a>Ayrıca Bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

