---
title: Çerçeve Windows yok etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 742ea2fedff2e4f044e46242a4152c12855ab15e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396161"
---
# <a name="destroying-frame-windows"></a>Çerçeve Pencerelerini Yok Etme

Pencere yok etme ve bunun yanı sıra oluşturmak için bu pencerelerde framework belgeler ve görünümler ile ilişkili MFC çerçevesi yönetir. Ek windows oluşturursanız, bu yok etme için sorumlu olursunuz.

Kullanıcı, pencerenin varsayılan çerçeve penceresi kapandığında Framework'teki [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Windows penceresini yok edildiğinde adlı son bir üye işlevidir [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), bazı temizleme işlemleri yapar, çağıran [varsayılan](../mfc/reference/cwnd-class.md#default) üye Windows temizleme işlemini gerçekleştirmek için işlevi ve son olarak çağırır sanal üye işlevi [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) uygulaması `PostNcDestroy` C++ pencere nesnesi siler. C++ hiçbir zaman kullanmalısınız **Sil** bir çerçeve penceresinde işleci. Bunun yerine `DestroyWindow` kullanın.

Ana pencere kapandığında uygulamayı kapatır. Kaydedilmemiş belgeler var. değişiklik yapılırsa, framework belgeleri kaydedilen istemek için bir ileti kutusu görüntüler ve ilgili belgelere gerekirse kaydedilmesini sağlar.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

