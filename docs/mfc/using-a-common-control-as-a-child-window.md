---
description: 'Hakkında daha fazla bilgi edinin: ortak bir denetimi alt pencere olarak kullanma'
title: Bir Ortak Denetimi Alt Pencere Olarak Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 5a5fda2cbf8d0bf16ccb17f2766b31d24e5c0c67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263562"
---
# <a name="using-a-common-control-as-a-child-window"></a>Bir Ortak Denetimi Alt Pencere Olarak Kullanma

Herhangi bir Windows ortak denetimi başka bir pencerenin alt penceresi olarak kullanılabilir. Aşağıdaki yordam, ortak bir denetimin dinamik olarak nasıl oluşturulduğunu ve ardından onunla nasıl çalışabileceğinizi açıklamaktadır.

### <a name="to-use-a-common-control-as-a-child-window"></a>Ortak bir denetimi alt pencere olarak kullanmak için

1. İlgili sınıf veya işleyicide denetimi tanımlayın.

1. Windows denetimini oluşturmak için [CWnd:: Create](../mfc/reference/cwnd-class.md#create) metodunu denetimin geçersiz kılmasını kullanın.

1. Denetim oluşturulduktan sonra ( `OnCreate` denetimi alt sınıfı yaparsanız işleyici kadar erken), denetimi üye işlevlerini kullanarak değiştirebilirsiniz. Yöntemler hakkındaki ayrıntılar için [denetimlerde](../mfc/controls-mfc.md) ayrı denetimlerin açıklamalarını inceleyin.

1. Denetim ile işiniz bittiğinde, denetimi yok etmek için [CWnd::D estroyWindow](../mfc/reference/cwnd-class.md#destroywindow) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
