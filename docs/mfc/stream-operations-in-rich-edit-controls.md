---
title: Akış işlemleri zengin düzenleme denetimlerinde | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66afb05031b302877dfd34f64e6076f882a256d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379931"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Akış İşlemleri
İçine veya dışına bir zengin düzenleme denetimine veri aktarmak için akışlarını kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir akış tarafından tanımlanan bir [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) yapısı, arabellek ve bir uygulama tanımlı geri çağırma işlevi belirtir.  
  
 Verileri bir zengin düzenleme denetimi okumak için (diğer bir deyişle, verileri akış) kullanmak [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) üye işlevi. Denetim art arda verilerin bir kısmını arabelleğe her zaman aktarır uygulama tanımlı geri çağırma işlevi çağırır.  
  
 Bir zengin içeriğini düzenleme denetimi kaydetmek için (diğer bir deyişle, veri çıkış akışı) kullanabileceğiniz [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) üye işlevi. Denetim art arda arabelleğe yazar ve sonra uygulama tanımlı geri çağırma işlevini çağırır. Her çağrı için arabellek içeriğini geri çağırma işlevini kaydeder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

