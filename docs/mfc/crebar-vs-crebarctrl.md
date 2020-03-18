---
title: CReBar ile CReBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: 94f889be453a17a55357a260bd2a0c07037f6ded
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445276"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar ile CReBarCtrl

MFC, yeniden çubuklar oluşturmak için iki sınıf sağlar: [CReBar](../mfc/reference/crebar-class.md) ve [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (Windows ortak denetim API 'sini sarmalayan). `CReBar`, Rebar ortak denetiminin tüm işlevlerini sağlar ve sizin için gerekli ortak denetim ayarlarının ve yapıların çoğunu işler.

`CReBarCtrl`, Win32 Rebar denetimi için bir sarmalayıcı sınıftır ve bu nedenle, yeniden çubuğu MFC mimarisine tümleştirmeyi düşünmüyorsanız uygulanması daha kolay olabilir. `CReBarCtrl` kullanmayı planlarsanız ve yeniden çubuğu MFC mimarisine tümleştirirseniz, yeniden çubuk denetim işlemelerini MFC 'ye iletmede ek bir dikkat etmeniz gerekir. Bu iletişim zor değildir; Ancak, `CReBar`kullandığınızda gereksiz olan ek çalışmadır.

Visual C++ , Rebar ortak denetiminden faydalanmak için iki yol sağlar.

- `CReBar`kullanarak yeniden çubuğu oluşturun ve `CReBarCtrl` üye işlevlerine erişim sağlamak için [CReBar:: GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) ' i çağırın.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl`, Rebar nesnesinin **Bu** işaretçisini oluşturan bir satır içi üye işlevidir. Bu, çalışma zamanında işlev çağrısının ek yükü olmayacağı anlamına gelir.

- [CReBarCtrl](../mfc/reference/crebarctrl-class.md)oluşturucuyu kullanarak yeniden çubuğu oluşturun.

Her iki yöntem de Rebar denetiminin üye işlevlerine erişmenizi sağlar. `CReBar::GetReBarCtrl`çağırdığınızda, herhangi bir üye işlevi kümesini kullanabilmeniz için bir `CReBarCtrl` nesnesine bir başvuru döndürür. `CReBar`kullanarak bir yeniden çubuk oluşturma ve oluşturma hakkında bilgi için bkz. [CReBar](../mfc/reference/crebar-class.md) .

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
