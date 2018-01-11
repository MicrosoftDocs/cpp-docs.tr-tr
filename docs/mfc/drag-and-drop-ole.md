---
title: "Sürükleme ve bırakma (OLE) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a852e597c06a08c3e9eb83731dc7da7df077435
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-ole"></a>Sürükleme ve Bırakma (OLE)
Veri kopyalama ve yapıştırma için öncelikle bir kısayol, OLE sürükle ve bırak özelliğidir. Veya veri kopyalamak için Pano'yu kullandığınızda, çeşitli adımları gereklidir. Verileri seçin, tıklatın **Kes** veya **kopya** gelen **Düzenle** menüsünde, hedef dosya, pencere veya uygulama, Git yerleştirin imleç istenen konumu ve tıklatın **Yapıştır** gelen **Düzenle** menüsü.  
  
 OLE sürükleme ve bırakma dosya adları yalnızca işleyebilir ve özellikle dosya adları uygulamaları geçirmek için tasarlanmıştır Dosya Yöneticisi sürükleme ve bırakma mekanizması farklıdır. OLE sürükleme ve bırakma çok daha genel. Panoda ayrıca yerleştirilemedi herhangi bir veri sürükleyip imkan tanır.  
  
 OLE sürükleme ve bırakma kullandığınızda işleminden iki adımı kaldırın. Veri kaynağı penceresinden ("bırakma kaynağı") seçin, istenen hedef ("bırakma hedefi") sürükleyin ve fare düğmesini bırakarak bırakın. İşlem menüleri gereksinimini ortadan kaldırır ve kopyala/yapıştır sırası hızlıdır. Bırakma kaynağı ve bırakma hedefi açık ve en az kısmen görünür ekranında olması gerektiğini tek gereksinimdir.  
  
 OLE sürükle ve bırak kullanarak, verileri bir konumdan diğerine farklı belgeler arasında veya uygulamalar arasında belge içinde aktarılabilir. Bir kapsayıcı veya bir sunucu uygulaması uygulanabilir ve herhangi bir uygulama bir bırakma kaynağı, bir bırakma hedefi veya her ikisi de olabilir. Bir uygulama uygulanan hem bırakma kaynağı hem de bırakma hedefi destek varsa, sürükle ve bırak etkinleştirildiğinde alt pencereleri arasında ya da bir pencere içinde. Bu özellik, uygulamanızın kullanmak üzere çok daha kolay yapabilirsiniz.  
  
 OLE sürükle ve bırak özelliklerini kullanmak istiyorsanız, bkz: [sürükle ve bırak: özelleştirme](../mfc/drag-and-drop-customizing.md). OLE dışı uygulamaları kaynakları bırakın yapmak için bu makalede açıklanan teknikleri kullanabilirsiniz. Makaleyi [sürükle ve bırak: bir bırakma hedefi uygulama](../mfc/drag-and-drop-implementing-a-drop-target.md) OLE ve OLE olmayan uygulamaları için destek bırakma hedefi uygulama açıklar. Ayrıca MFC OLE örnekleri incelemek yararlı olacak [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md).  
  
 Değil okumadıysanız [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) makaleleri ailesi, bunu şimdi yapmak isteyebilirsiniz. Bu makaleler, veri aktarımı ve uygulamalarınızda uygulama temelleri açıklanır.  
  
 Sürükleme ve bırakma hakkında daha fazla bilgi için bkz:  
  
-   [Sürükle ve Bırak: Bir Bırakma Kaynağı Uygulama](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Sürükle ve Bırak: Bir Bırakma Hedefi Uygulama](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Sürükle ve Bırak: Özelleştirme](../mfc/drag-and-drop-customizing.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)   
 [Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)

