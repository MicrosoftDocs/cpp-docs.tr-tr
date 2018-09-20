---
title: Pano | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48315b3608a5e66c2f94e1b06a038772dbb25bb4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380496"
---
# <a name="clipboard"></a>Pano

Bu makaleler ailesi Windows Pano desteği, MFC uygulamalarında uygulamak açıklanmaktadır. Windows panosu iki şekilde kullanılır:

- Kesme, kopyalama ve yapıştırma gibi standart düzenleme menü komutları uygulama.

- Uygulama Tekdüzen veri aktarımı ile sürükle ve bırakma (OLE).

Pano bir kaynak ve hedef arasında veri aktarımı için standart Windows yöntemdir. Ayrıca OLE işlemlerinde çok kullanışlı olabilir. OLE gelişinden ile Windows iki Pano mekanizma vardır. Standart Windows panosu API'si hala kullanılabilir, ancak OLE veri aktarım mekanizması ile takıma. OLE Tekdüzen veri aktarımı (UDT), kesme, kopyalama ve yapıştırma panoyla destekler ve sürükleyin ve bırakın.

Pano, tanıtıcı veya sınıf kendi içermez tüm Windows oturumu tarafından paylaşılan bir sistemi hizmetidir. Pano sınıfın üye işlevleri aracılığıyla yönetmek [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Her Pano mekanizmasının ne zaman kullanılacağı](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [Geleneksel Windows panosu API'si kullanma](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [Veri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)

- [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)

- [Windows panosu](https://msdn.microsoft.com/library/ms648709)

- [Sürükleme ve bırakma (OLE) uygulama](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
