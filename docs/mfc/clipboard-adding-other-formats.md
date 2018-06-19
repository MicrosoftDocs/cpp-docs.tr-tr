---
title: 'Pano: Diğer biçimleri ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c28fd1d628d0aed79028e43d9cce383f3acbb4ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342153"
---
# <a name="clipboard-adding-other-formats"></a>Pano: Diğer Biçimleri Ekleme
Bu konuda, özellikle OLE desteği için desteklenen biçimler listesini genişletmek açıklanmaktadır. Konu [Pano: veri kopyalama ve yapıştırmayı](../mfc/clipboard-copying-and-pasting-data.md) kopyalama ve yapıştırma panodan desteklemek için gereken en düşük uygulamayı açıklar. Bu tüm uygulamanız ise, Pano'ya yerleştirilen yalnızca biçimler: `CF_METAFILEPICT`, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**ve büyük olasılıkla `CF_LINKSOURCE`. Uygulamaların çoğu bu üç Pano üzerinde daha fazla biçiminden gerekir.  
  
##  <a name="_core_registering_custom_formats"></a> Özel kaydetme biçimleri  
 Kendi özel biçimler oluşturmak için özel bir pano biçimi kaydederken kullandığınız aynı yordamı izleyin: biçimine adını geçirmek **RegisterClipboardFormat** işlev ve dönüş değerini biçim ID olarak kullan.  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> Biçimleri Pano'ya yerleştirme  
 Bu panoya yerleştirilen daha fazla biçimleri eklemek için geçersiz kılmanız gerekir `OnGetClipboardData` herhangi birinden türetilmiş sınıf işlevinde `COleClientItem` veya `COleServerItem` (kopyalanacak verileri yerel olup olmamasına bağlı olarak). Bu işlevde, aşağıdaki yordamı kullanmanız gerekir.  
  
#### <a name="to-place-formats-on-the-clipboard"></a>Pano'ya biçimleri yerleştirmek için  
  
1.  Oluşturma bir `COleDataSource` nesnesi.  
  
2.  Bu veri kaynağı, yerel veri biçimleri çağırarak desteklenen biçimler listesine ekler. bir işlev geçirmek `COleDataSource::CacheGlobalData`.  
  
3.  Standart biçimlerini çağırarak eklemek `COleDataSource::CacheGlobalData` desteklemek istediğiniz her standart biçimi.  
  
 Bu teknik MFC OLE örnek programı kullanılır [HIERSVR](../visual-cpp-samples.md) (inceleyin `OnGetClipboardData` üye işlevini **CServerItem** sınıfı). Yalnızca bu örnekteki diğer standart biçimlerini HIERSVR desteklediği için bu üç adımı uygulanmadı farktır.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE sürükleme ve bırakma](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pano: OLE Pano Mekanizmasını Kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

