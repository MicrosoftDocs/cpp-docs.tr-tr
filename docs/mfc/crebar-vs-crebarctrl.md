---
title: CReBar ile CReBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: 05decc095e43426044c4487b9aca05268642f915
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620454"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar ile CReBarCtrl

MFC, yeniden çubuklar oluşturmak için iki sınıf sağlar: [CReBar](reference/crebar-class.md) ve [CReBarCtrl](reference/crebarctrl-class.md) (Windows ortak denetim API 'sini sarmalayan). `CReBar`, Rebar ortak denetiminin tüm işlevlerini sağlar ve sizin için gerekli ortak denetim ayarlarının ve yapıların çoğunu işler.

`CReBarCtrl`, Win32 Rebar denetimi için bir sarmalayıcı sınıftır ve bu nedenle, yeniden çubuğu MFC mimarisine tümleştirmeyi düşünmüyorsanız uygulanması daha kolay olabilir. `CReBarCtrl`Yeniden çubuğu mfc mimarisine göre kullanmayı ve tümleştirmeyi planlıyorsanız, yeniden çubuk denetim işlemelerini MFC 'ye iletmede ek bir dikkat etmeniz gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda gereksiz olan ek çalışmadır `CReBar` .

Visual C++, Rebar ortak denetiminden faydalanmak için iki yol sağlar.

- Kullanarak yeniden çubuğu oluşturun `CReBar` ve ardından üye işlevlerine erişmek Için [CReBar:: GetReBarCtrl](reference/crebar-class.md#getrebarctrl) ' i çağırın `CReBarCtrl` .

    > [!NOTE]
    >  `CReBar::GetReBarCtrl`, Rebar nesnesinin **Bu** işaretçisini oluşturan bir satır içi üye işlevidir. Bu, çalışma zamanında işlev çağrısının ek yükü olmayacağı anlamına gelir.

- [CReBarCtrl](reference/crebarctrl-class.md)oluşturucuyu kullanarak yeniden çubuğu oluşturun.

Her iki yöntem de Rebar denetiminin üye işlevlerine erişmenizi sağlar. `CReBar::GetReBarCtrl`' İ çağırdığınızda, `CReBarCtrl` herhangi bir üye işlevi kümesini kullanabilmeniz için bir nesnesine bir başvuru döndürür. Kullanarak bir yeniden çubuk oluşturma ve oluşturma hakkında bilgi için bkz. [CReBar](reference/crebar-class.md) `CReBar` .

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](using-crebarctrl.md)<br/>
[Denetimler](controls-mfc.md)
