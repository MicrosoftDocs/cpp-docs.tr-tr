---
description: 'Daha fazla bilgi edinin: MDI alt pencerelerini yönetme'
title: MDI Alt Öğe Pencerelerini Yönetme
ms.date: 11/19/2018
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: 1207e6a8fa174c36b09352796521bcb860ee665f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112095"
---
# <a name="managing-mdi-child-windows"></a>MDI Alt Öğe Pencerelerini Yönetme

MDI ana çerçeve pencereleri (uygulama başına bir tane) MDıCLıENT penceresi adlı özel bir alt pencere içerir. MDıCLıENT penceresi, ana çerçeve penceresinin istemci alanını yönetir ve kendi alt pencereleri vardır: belge pencereleri, öğesinden türetilir `CMDIChildWnd` . Belge pencereleri, çerçeve pencerelerinin (MDI alt pencereleri) olduğu için kendi alt öğelerine de sahip olabilirler. Bu durumların tümünde, üst pencere alt pencerelerini yönetir ve bazı komutları bunlara iletir.

Bir MDI çerçevesi penceresinde, çerçeve penceresi MDıCLıENT penceresini yönetir ve denetim çubuklarıyla birlikte yeniden konumlandırın. MDıCLıENT penceresi, sırasıyla tüm MDI alt çerçeve pencerelerini yönetir. Aşağıdaki şekilde, bir MDI çerçevesi penceresi, MDıCLıENT penceresi ve onun alt belge çerçeve pencereleri arasındaki ilişki gösterilmektedir.

![MDI çerçeve penceresinde alt pencereler](../mfc/media/vc37gb1.gif "MDI çerçeve penceresinde alt pencereler") <br/>
MDI çerçeve pencereleri ve alt öğeleri

Bir MDI çerçevesi penceresi, varsa geçerli MDI alt penceresiyle birlikte da kullanılabilir. MDI çerçevesi penceresi, kendisini işlemesini denemeden önce MDI alt öğesine komut iletileri devreder.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](creating-document-frame-windows.md)

- [Çerçeve pencere stilleri](frame-window-styles-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencerelerini kullanma](using-frame-windows.md)
