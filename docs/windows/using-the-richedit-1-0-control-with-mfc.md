---
title: MFC ile RichEdit 1.0 Denetimini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
ms.openlocfilehash: 080ad995b9c7a041337d9b296d6ef8906e7f20ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468321"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC ile RichEdit 1.0 Denetimini Kullanma

RichEdit denetimini kullanmak için öncelikle çağırmalısınız [Afxınitrichedit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 denetimi (RICHED20. yüklemek için DLL) veya çağrı [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) eski RichEdit 1.0 denetimini (RICHED32. yüklemek için DLL).

Geçerli kullanabilir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) eski RichEdit 1.0 denetimi sınıfıyla ancak `CRichEditCtrl` yalnızca 2.0 RichEdit denetimini desteklemek için tasarlanmıştır. RichEdit 1.0 ve 2.0 RichEdit çok benzer olduğundan, çoğu yöntemleri çalışır; Ancak, bazı yöntemler yanlış çalışmasına veya hiç çalışmıyor 1.0 ve 2.0 denetimlerini arasında bazı farklar vardır unutmayın.

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisinde Sorun Giderme](../windows/troubleshooting-the-dialog-editor.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)