---
title: Çıktı (cihaz bağlamı) sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.output
dev_langs:
- C++
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85571e2173d9dc4e900d63e982a91571fafc103e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="output-device-context-classes"></a>Çıktı (Cihaz Bağlamı) Sınıfları
Bu sınıfların cihaz bağlamlarında kullanılabilir Windows farklı türde kapsüller.  
  
 Aşağıdaki sınıfların çoğu Windows cihaz bağlamı için bir tanıtıcı kapsüller. Bir cihaz bağlamı bir görünüm veya yazıcı gibi bir aygıtı çizim öznitelikleri hakkında bilgi içeren bir Windows nesnesidir. Tüm çizim çağrılar bir aygıt-context nesnesi yapılır. Ek sınıfları türetilen `CDC` Windows meta dosyaları da dahil olmak üzere özelleştirilmiş cihaz bağlamı işlevleri kapsülleyen.  
  
 [CDC](../mfc/reference/cdc-class.md)  
 Cihaz bağlamları için temel sınıf. Tam ekran erişmek için doğrudan ve yazıcılar gibi nondisplay bağlamları erişmek için kullanılır.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md)  
 Kullanılan bir görüntü bağlamı `OnPaint` Windows üye işlevleri. Otomatik olarak çağırır `BeginPaint` yapım üzerinde ve `EndPaint` yok etme üzerinde.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md)  
 Windows istemci alanları için görüntüleme bağlamı. Örneğin, bir hemen olaylarına yanıt olarak fare çizmek için kullanılır.  
  
 [CWindowDC](../mfc/reference/cwindowdc-class.md)  
 Hem istemci hem de nonclient alanları da dahil olmak üzere tüm windows için görüntüleme bağlamı.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md)  
 Windows meta dosyaları için bir cihaz bağlamı. Bir Windows Meta dosyası bir görüntü oluşturmak için çalınabilir grafik cihaz arabirimi (GDI) komutları dizisini içerir. Üye işlevlerini yapılan çağrılar bir `CMetaFileDC` meta dosyasının içine kaydedilir.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Ayrı tutma (x, y) koordinat çiftleri.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Uzaklık, göreli konumları ya da eşleştirilmiş değerleri barındırır.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Dikdörtgen alanları koordinatlarını içerir.  
  
 [CRgn](../mfc/reference/crgn-class.md)  
 Bir pencere içindeki bir elips, çokgen veya düzensiz alanı düzenleme için GDI bölge yalıtır. Sınıfında kırpma üye işlevleri ile birlikte kullanılan `CDC`.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Yeniden boyutlandırma ve dikdörtgen nesneleri taşıma için kullanılan kullanıcı arabirimi işler ve görüntüler.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Bir renk seçmek için bir standart iletişim kutusu sağlar.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Standart iletişim kutusu, yazı tipi seçmek için sağlar.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Bir dosya yazdırma için bir standart iletişim kutusu sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

