---
title: CReBar ile CReBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CReBar
- CReBarCtrl
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: a1b5cda729e760246449bf197fdc9b32752b96e8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279217"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar ile CReBarCtrl

MFC rebars oluşturmak için iki sınıf sağlar: [CReBar](../mfc/reference/crebar-class.md) ve [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CReBar` Tüm ortak çubuk barınağı denetimi işlevlerini sağlar ve bu gerekli ortak denetim ayarları ve yapıları çoğunu sizin yerinize çözer.

`CReBarCtrl` Win32 çubuk barınağı şeritleri için bir sarmalayıcı sınıftır ve bu nedenle çubuk barınağı MFC mimarisine tümleştirmek düşünmüyorsanız uygulamak daha kolay olabilir. Kullanmayı planlıyorsanız `CReBarCtrl` ve MFC mimarisine çubuk barınağı tümleştirin, çubuk barınağı denetimi işlemeleri MFC iletişim kurmak için daha da dikkatli göz önüne almanız gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda, gereksiz ek çalışma gerekir `CReBar`.

Visual C++ çubuk barınağı ortak denetimi yararlanmak için iki yol sunar.

- Çubuk barınağı kullanarak oluşturduğunuz `CReBar`ve sonra çağrı [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) erişim elde etmek için `CReBarCtrl` üye işlevleri.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` bıraktığı bir satır içi üye işlevi olan **bu** çubuk barınağı nesne işaretçisi. Bu, çalışma zamanında işlev çağrısı zahmetine olduğu anlamına gelir.

- Çubuk barınağı kullanarak oluşturduğunuz [CReBarCtrl](../mfc/reference/crebarctrl-class.md)'s Oluşturucusu.

Her iki yöntem için çubuk barınağı denetimi üye işlevleri sürümlere erişmenizi sağlayacaktır. Çağırdığınızda `CReBar::GetReBarCtrl`, bir başvuru döndürür bir `CReBarCtrl` ayarlayın ya da üye işlevleri kullanabilmeniz için nesne. Bkz: [CReBar](../mfc/reference/crebar-class.md) oluşturma ve kullanarak bir çubuk barınağı oluşturma hakkında bilgi `CReBar`.

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
