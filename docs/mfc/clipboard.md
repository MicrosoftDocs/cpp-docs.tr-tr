---
title: Pano
ms.date: 11/04/2016
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
ms.openlocfilehash: d405a7bbe15d2658380e19c1c908e57f2e40a574
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508936"
---
# <a name="clipboard"></a>Pano

Bu makale ailesinde MFC uygulamalarında Windows panosuna yönelik desteğin nasıl uygulanacağı açıklanmaktadır. Windows Panosu iki şekilde kullanılır:

- Kes, Kopyala ve Yapıştır gibi standart düzenleme menü komutlarını uygulama.

- Sürükleme ve bırakma (OLE) ile Tekdüzen veri aktarımını uygulama.

Pano, verileri bir kaynak ve hedef arasında aktarmaya yönelik standart Windows yöntemidir. OLE işlemlerinde de çok yararlı olabilir. OLE 'nin KAG 'i ile Windows 'da iki Pano mekanizması vardır. Standart Windows Pano API 'SI yine de kullanılabilir, ancak OLE veri aktarım mekanizmasıyla takıma sunuldu. OLE Tekdüzen veri aktarımı (UDT) Pano ile kesme, kopyalama ve yapıştırmayı destekler ve sürükleyip bırakın.

Pano, tüm Windows oturumu tarafından paylaşılan bir sistem hizmetidir, bu nedenle kendine ait bir tanıtıcıya veya sınıfına sahip değildir. Panoyu [CWnd](../mfc/reference/cwnd-class.md)sınıfının üye işlevleri aracılığıyla yönetirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Her Pano mekanizmasının ne zaman kullanılacağı](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [Geleneksel Windows Pano API 'sini kullanma](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE panosu mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [Verileri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)

- [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)

- [Windows Panosu](/windows/win32/dataxchg/clipboard)

- [Sürükleme ve bırakma uygulama (OLE)](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
