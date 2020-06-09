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
ms.openlocfilehash: 5f4a17bedaa50913dce1f6388dfb6b8d9ecd38da
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617282"
---
# <a name="clipboard"></a>Pano

Bu makale ailesinde MFC uygulamalarında Windows panosuna yönelik desteğin nasıl uygulanacağı açıklanmaktadır. Windows Panosu iki şekilde kullanılır:

- Kes, Kopyala ve Yapıştır gibi standart düzenleme menü komutlarını uygulama.

- OLE sürükle ve bırak ile Tekdüzen veri aktarımı uygulama.

Pano, verileri bir kaynak ve hedef arasında aktarmaya yönelik standart Windows yöntemidir. OLE işlemlerinde de çok yararlı olabilir. OLE 'nin KAG 'i ile Windows 'da iki Pano mekanizması vardır. Standart Windows Pano API 'SI yine de kullanılabilir, ancak OLE veri aktarım mekanizmasıyla takıma sunuldu. OLE Tekdüzen veri aktarımı (UDT) Pano ile kesme, kopyalama ve yapıştırmayı destekler ve sürükleyip bırakın.

Pano, tüm Windows oturumu tarafından paylaşılan bir sistem hizmetidir, bu nedenle kendine ait bir tanıtıcıya veya sınıfına sahip değildir. Panoyu [CWnd](reference/cwnd-class.md)sınıfının üye işlevleri aracılığıyla yönetirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Her Pano mekanizmasının ne zaman kullanılacağı](clipboard-when-to-use-each-clipboard-mechanism.md)

- [Geleneksel Windows Pano API 'sini kullanma](clipboard-using-the-windows-clipboard.md)

- [OLE panosu mekanizmasını kullanma](clipboard-using-the-ole-clipboard-mechanism.md)

- [Verileri kopyalama ve yapıştırma](clipboard-copying-and-pasting-data.md)

- [Diğer biçimleri ekleme](clipboard-adding-other-formats.md)

- [Windows Panosu](/windows/win32/dataxchg/clipboard)

- [OLE sürükle ve bırak](drag-and-drop-ole.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)
