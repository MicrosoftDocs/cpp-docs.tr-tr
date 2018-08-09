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
ms.openlocfilehash: a00642c1aefdce57c37723ef4daf23381cee3c13
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650754"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC ile RichEdit 1.0 Denetimini Kullanma
RichEdit denetimini kullanmak için öncelikle çağırmalısınız [Afxınitrichedit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 denetimi (RICHED20. yüklemek için DLL) veya çağrı [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) eski RichEdit 1.0 denetimini (RICHED32. yüklemek için DLL).  
  
 Geçerli kullanabilir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) eski RichEdit 1.0 denetimi sınıfıyla ancak `CRichEditCtrl` yalnızca 2.0 RichEdit denetimini desteklemek için tasarlanmıştır. RichEdit 1.0 ve 2.0 RichEdit çok benzer olduğundan, çoğu yöntemleri çalışır; Ancak, bazı yöntemler yanlış çalışmasına veya hiç çalışmıyor 1.0 ve 2.0 denetimlerini arasında bazı farklar vardır unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu düzenleyicisinde sorun giderme](../windows/troubleshooting-the-dialog-editor.md)   
 [İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)