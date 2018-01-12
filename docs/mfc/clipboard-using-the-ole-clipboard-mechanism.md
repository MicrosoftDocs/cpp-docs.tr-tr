---
title: "Pano: OLE Pano mekanizmasını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4996c6559ad20141fb84ed37e87fd1551e89a77b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>Pano: OLE Pano Mekanizmasını Kullanma
OLE Pano üzerinden veri aktarmak için standart biçimleri ve bazı OLE özgü biçimleri kullanır.  
  
 Kesme veya bir uygulamadan veri kopyalama, verileri daha sonra yapıştırma işlemlerinde kullanılacak Panosu'nda depolanır. Çeşitli biçimlerde verilerdir. Bir kullanıcı Pano'dan veri yapıştırmak seçtiğinde, uygulamanın hangi kullanmak için aşağıdaki biçimlerden birini seçebilirsiniz. Özellikle belirli bir bir biçim için Özel Yapıştır kullanarak kullanıcıdan sürece bilgilerin çoğu sağlar biçimi seçmek için uygulamayı yeniden yazılması gerekir. Devam etmeden önce okumak isteyebilirsiniz [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) Konular. Bunların nasıl iş veri aktarır ve uygulamalarınızda uygulama temelleri açıklanır.  
  
 Windows panosu üzerinden veri aktarmak için kullanılan standart biçimlerini sayısını tanımlar. Bunlar, meta dosyaları, metin, bit eşlemler ve diğerleri içerir. OLE Özel OLE biçimleri, de sayısını tanımlar. Bu standart biçimleri tarafından verilen'den daha fazla ayrıntı gerektiren uygulamalar için kendi özel Pano biçimleri kaydetmek için bir fikirdir. Win32 API işlevini [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Bunu yapmak için.  
  
 Örneğin, Microsoft Excel elektronik tablolar için özel bir biçim kaydeder. Bu biçim çok daha fazla bilgi, örneğin taşır, bit eşlem yapar. Bu verileri elektronik tablo biçiminde destekleyen bir uygulamaya yapıştırılırken formüller ve elektronik değerleri korunur ve gerekirse güncelleştirilebilir. Böylece bir OLE öğesi olarak yapıştırılabilmesi için Microsoft Excel veri biçimleri Pano'ya da koyar. Tüm OLE belge kapsayıcısı bu bilgileri katıştırılmış bir öğe olarak yapıştırabilirsiniz. Katıştırılmış bu öğe Microsoft Excel kullanarak değiştirilebilir. Pano, elektronik tablo seçili aralıkta görüntüsü basit bir bit eşlem de içerir. Bu ayrıca OLE belge kapsayıcıları veya Paint gibi bit eşlem düzenleyicileri yapıştırılabilmesi için. Bir bitmap söz konusu olduğunda, ancak verileri elektronik olarak işlemek için yolu yoktur.  
  
 Panodan en çok bilgi almak için uygulamalar Pano verilerini yapıştırma önce bu özel biçimler için denetlemelisiniz.  
  
 Örneğin, kesme komutu etkinleştirmek için bir işleyici aşağıdakine benzer yazabilirsiniz:  
  
 [!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Veri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows panosunu kullanma](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pano](../mfc/clipboard.md)

