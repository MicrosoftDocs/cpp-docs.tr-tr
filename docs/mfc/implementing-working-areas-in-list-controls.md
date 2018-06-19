---
title: Liste denetimlerinde çalışma alanlarını uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44b92fbda7f00c761059a44b5bf9483e2dfac814
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347366"
---
# <a name="implementing-working-areas-in-list-controls"></a>Liste Denetimlerinde Çalışma Alanlarını Uygulama
Varsayılan olarak, bir liste denetimini tüm öğeleri bir standart kılavuz şekilde düzenler. Ancak, çalışma liste öğeleri dikdörtgen gruplar halinde düzenler alanlarını, başka bir yöntem desteklenir. Çalışma alanları uygulayan bir liste denetimi görüntüsü için liste görünümü denetimlerinde kullanarak Windows SDK'sı bakın.  
  
> [!NOTE]
>  Çalışma alanları, yalnızca liste denetimi simgesini veya küçük simge modunda olduğunda görünür. Ancak, görünümü rapor veya listeyi moduna geçtiyseniz geçerli çalışma alanları saklanır.  
  
 Çalışma alanları (sol, üst ve/veya öğeleri sağındaki üzerinde) boş bir sınır görüntülemek veya normalde olmayacaktır olması bir görüntülenecek yatay kaydırma çubuğu neden için kullanılabilir. Başka bir yaygın kullanım için öğeleri taşınmış bırakılan veya birden çok çalışma alanları oluşturmaktır. Bu yöntemle farklı anlamları tek bir görünümde alanları oluşturabilirsiniz. Kullanıcı farklı bir alanında koyarak öğeleri ardından kategorilere. Bunun bir örneğini okuma/yazma dosyaları için bir alan ve salt okunur dosyalar için başka bir alana sahip bir dosya sistemi görünümünü olacaktır. Dosya öğesi salt okunur alanına taşındıysa, onu otomatik olarak salt okunur. Bir dosya salt okunur alanından okuma/yazma alanına taşıma, okuma/yazma dosya hale getirir.  
  
 `CListCtrl` oluşturma ve yönetme, liste denetiminde çalışma alanları için birden fazla üye işlevleri sağlar. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) ve [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) almak ve bir dizi ayarlamak `CRect` nesneler (veya `RECT` yapıları), şu anda uygulanan çalışma alanları listesi denetlemek için depolama. Ayrıca, [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) çalışma alanları liste denetimi için geçerli sayısını alır (varsayılan olarak, sıfır).  
  
## <a name="items-and-working-areas"></a>Öğeleri ve çalışma alanları  
 Bir çalışma alanı oluşturulduğunda, çalışma alanının içinde bulunan öğeler üyelerini haline gelir. Benzer şekilde, bir öğe çalışma alanına taşınırsa, taşınmış olan çalışma alanının bir üyesi haline gelir. Otomatik olarak bir öğe içinde herhangi bir çalışma alanına bulunmayacak, ilk (dizin 0) çalışma alanının bir üyesi haline gelir. Bir öğe oluşturun ve belirli bir çalışma alanı içinde yerleştirilen sağlamak istiyorsanız, öğesi oluşturun ve ardından taşımak istediğiniz çalışma alanına çağrısıyla gerekir [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition). Aşağıdaki ikinci örneği, bu tekniği gösterir.  
  
 Aşağıdaki örnek dört çalışma alanları uygulayan (`rcWorkAreas`), her çalışma alanında bir liste denetimini 10 piksel genişliğinde kenarlık ile eşit boyutta (`m_WorkAreaListCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]  
  
 Çağrı [ApproximateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect) bir bölgede tüm öğeleri görüntülemek için gereken toplam alanının kestirmek girişiminde bulunuldu. Bu tahmin sonra dört bölgelere ayrılmış ve 5 piksel genişliğinde kenarlık ile doldurulan.  
  
 Sonraki örnekte, her grup için varolan liste öğelerini atar (`rcWorkAreas`) ve denetim Görünümü yeniler (`m_WorkAreaListCtrl`) etkisi tamamlamak için.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

