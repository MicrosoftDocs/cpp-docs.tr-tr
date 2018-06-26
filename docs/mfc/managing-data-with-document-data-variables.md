---
title: Belge verisi değişkenleri ile verileri yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca7c673f47510282e129eab2538008400eb2fb9
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929438"
---
# <a name="managing-data-with-document-data-variables"></a>Belge Verisi Değişkenleri ile Verileri Yönetme
Belgenizin veri belge sınıfı üye değişkenleri olarak uygular. Örneğin, karalama program türü veri üyesi bildirir `CObList` — işaretçileri depolar bağlantılı bir liste `CObject` nesneleri. Bu liste, bir serbest çizgi çizme noktalar dizileri depolamak için kullanılır.  
  
 Belgenizin üye verileri nasıl uygulayacağınıza uygulamanızı yapısına bağlıdır. MFC çıkışı yardımcı olmak için bir grup "koleksiyon sınıflarının" temin eder — diziler, listeler ve eşlemeler C++ şablonlar temelinde koleksiyonları dahil olmak üzere (sözlükler) — ortak veri türleri çeşitli gibi kapsülleyen sınıfları birlikte `CString`, `CRect`, `CPoint`, `CSize`, ve `CTime`. Bu sınıfları hakkında daha fazla bilgi için bkz: [sınıf kitaplığına genel bakış](../mfc/class-library-overview.md) içinde *MFC başvurusu*.  
  
 Belgenizin üye verileri tanımladığınızda, genellikle üye işlevleri ayarlamak ve veri öğelerini almak ve bunları yararlı diğer işlemleri gerçekleştirmek için belge sınıfı ekler.  
  
 Kendi görünümlerinizi belge nesnesi, görünümün işaretçi oluşturma zamanında görünümünde yüklü belgeye kullanarak erişir. Bir görünümün üye işlevleri üzerinde this işaretçisi çağırarak alabilir `CView` üye işlevi `GetDocument`. Bu işaretçinin kendi belge türüne yayınlanamıyor emin olun. Ardından işaretçiyi ortak belge üyeleri erişebilir.  
  
 Sık veri aktarımı doğrudan erişim gerektirir ya da belge sınıfının ortak olmayan üyeler kullanmak istiyorsanız, arkadaşınızın (C++ koşullarını) belge sınıfının sınıf görünümünüzü yapmak isteyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

