---
title: MFC ile RichEdit 1.0 denetimini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d2d45de1c6bd986c2bf509ce601f80fcd3721599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890317"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC ile RichEdit 1.0 Denetimini Kullanma
RichEdit denetimi kullanmak için önce çağırmalısınız [Afxınitrichedit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 denetimi (RICHED20. yüklemek için DLL) veya arama [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) eski RichEdit 1.0 denetimi (RICHED32. yüklemek için DLL).  
  
 Geçerli kullanabilir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) eski RichEdit 1.0 denetimi sınıfıyla ancak **CRichEditCtrl** yalnızca RichEdit 2.0 denetimi destekleyecek şekilde tasarlanmıştır. RichEdit 1.0 ve RichEdit 2.0 çok benzer olduğundan, çoğu yöntemleri çalışır; Ancak, bazı yöntemler yanlış iş veya hiç iş yok şekilde 1.0 ve 2.0 denetimleri arasındaki bazı farklar vardır unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu Düzenleyicisi sorunlarını giderme](../windows/troubleshooting-the-dialog-editor.md)   
 [İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

