---
description: 'Daha fazla bilgi edinin: çerçeve pencerelerini yok etme'
title: Çerçeve Pencerelerini Yok Etme
ms.date: 11/04/2016
f1_keywords:
- PostNcDestroy
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
ms.openlocfilehash: 192b1b21881f4a9f94a4fb1d6c7b18b4a91ac579
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327853"
---
# <a name="destroying-frame-windows"></a>Çerçeve Pencerelerini Yok Etme

MFC çerçevesi, pencere yok etme ve çerçeve belgeleri ve görünümleriyle ilişkili pencereler için oluşturma işlemlerini yönetir. Ek pencereler oluşturursanız, bunları yok etmek sizin sorumluluğunuzdadır.

Çerçevede, Kullanıcı çerçeve penceresini kapattığında, pencerenin varsayılan [OnClose](reference/cwnd-class.md#onclose) Işleyicisi, [DestroyWindow](reference/cwnd-class.md#destroywindow)'u çağırır. Windows penceresi yok edildiğinde çağrılan son üye işlevi [OnNcDestroy](reference/cwnd-class.md#onncdestroy), bazı temizleme işlemleri yapar, Windows CleanUp işlemini gerçekleştirmek için [varsayılan](reference/cwnd-class.md#default) üye işlevini çağırır ve son olarak [PostNcDestroy](reference/cwnd-class.md#postncdestroy)sanal üye işlevini çağırır. ' In [CFrameWnd](reference/cframewnd-class.md) uygulamasının `PostNcDestroy` C++ pencere nesnesini silmesi. **`delete`** Bir çerçeve penceresinde C++ işlecini asla kullanmamalısınız. Bunun yerine `DestroyWindow` kullanın.

Ana pencere kapandığında uygulama kapanır. Kaydedilmemiş belgeler varsa, çerçeve, belgelerin kaydedilip kaydedilmemesini istemek için bir ileti kutusu görüntüler ve gerekirse uygun belgelerin kaydedilmesini sağlar.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](creating-document-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencerelerini kullanma](using-frame-windows.md)
