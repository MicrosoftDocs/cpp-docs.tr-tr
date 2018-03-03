---
title: Pano | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 304f20f94880b0bd8cb671788c5c06b69d25d377
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard"></a>Pano
Bu makaleler ailesi Windows panosuna desteği MFC uygulamalarında uygulamak açıklanmaktadır. Windows panosu iki yolla kullanılır:  
  
-   Kesme, kopyalama ve yapıştırma gibi standart düzenleme menü komutlarını uygulama.  
  
-   Tekdüzen veri uygulama ile Sürükle aktarmak ve bırakma (OLE).  
  
 Pano bir kaynak ve hedef arasında veri aktarımı, standart Windows yöntemidir. Ayrıca OLE işlemlerinde çok kullanışlı olabilir. OLE geliştirilirken ile Windows Pano için iki mekanizma vardır. Standart Windows panosu API'si hala kullanılabilir, ancak OLE veri aktarım mekanizması ile takıma. OLE Tekdüzen veri aktarımı (UDT) kesme, kopyalama ve yapıştırma Pano ile destekler ve sürükleyin ve bırakın.  
  
 Pano bir tanıtıcı ya da kendi sınıf yok şekilde tüm Windows oturum tarafından paylaşılan bir sistemdir. Pano sınıfının üye fonksiyonları üzerinden yönetmek [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Her Pano mekanizmasının ne zaman kullanılacağı](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [Geleneksel Windows panosu API'si kullanma](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Veri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows panosu](https://msdn.microsoft.com/library/ms648709)  
  
-   [Sürükleme ve bırakma (OLE) uygulama](../mfc/drag-and-drop-ole.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
