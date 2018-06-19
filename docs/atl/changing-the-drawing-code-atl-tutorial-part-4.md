---
title: Çizim kodunu değiştirme (ATL Eğitmeni, Bölüm 4) | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c077aca8c3276fac963eda8cdd2c413a9d6d5f5b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358918"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Çizim Kodunu değiştirme (ATL Eğitmeni, Bölüm 4)
Varsayılan olarak, bir kare ve metin denetimin çizim kodunu görüntüler **PolyCtl**. Bu adımda, daha ilginç bir şey görüntülemek için kodunu değiştirir. Aşağıdaki görevleri oynayan:  
  
-   Üst bilgi dosyasını değiştirme  
  
-   Değiştirme `OnDraw` işlevi  
  
-   Çokgen noktalarının hesaplamak için bir yöntem ekleme  
  
-   Dolgu rengi başlatılıyor  
  
## <a name="modifying-the-header-file"></a>Üst bilgi dosyasını değiştirme  
 Matematik işlevleri için destek eklemeye başlayın `sin` ve `cos`, hangi kullanılacak Çokgen noktalarının hesaplamak ve depolamak için bir dizi oluşturarak yerleştirir.  
  
#### <a name="to-modify-the-header-file"></a>Üst bilgi dosyasını değiştirmek için  
  
1.  Satırı ekleyin `#include <math.h>` PolyCtl.h dön. Dosyanın en üstüne aşağıdaki gibi görünmelidir:  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  Çokgen noktalarının hesaplanan sonra türünde bir dizi depolanacak `POINT`, bu nedenle dizi sonra tanımını ekleyin `m_nSides` PolyCtl.h içinde:  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## <a name="modifying-the-ondraw-method"></a>OnDraw yöntemi değiştirme  
 Değiştirmeniz gerekir artık `OnDraw` PolyCtl.h yöntemi. Ekleyecek kod yeni Kalem ve hangi, çokgen çizmek fırça oluşturur ve ardından çağırır `Ellipse` ve `Polygon` Fiili çizimi gerçekleştirmek için Win32 API işlevleri.  
  
#### <a name="to-modify-the-ondraw-function"></a>OnDraw işlevi değiştirmek için  
  
1.  Varolan `OnDraw` PolyCtl.h yönteminde aşağıdaki kod ile:  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Çokgen noktalarının hesaplamak için bir yöntem ekleme  
 Adlı bir yöntem ekleyin `CalcPoints`, çokgenin çevre noktalar koordinatlarını hesaplar. Bu hesaplamalar işlevdeki geçirilen RECT değişkeni dayalı olacak.  
  
#### <a name="to-add-the-calcpoints-method"></a>CalcPoints yöntemi eklemek için  
  
1.  Bildirimi ekleme `CalcPoints` için `IPolyCtl` ortak bölümüne `CPolyCtl` PolyCtl.h sınıfında:  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     Ortak bölümüne son parçası `CPolyCtl` sınıfı şu şekilde görünür:  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  Bu uygulaması, ekleme `CalcPoints` PolyCtl.cpp sonuna işlevi:  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## <a name="initializing-the-fill-color"></a>Dolgu rengi başlatılıyor  
 Initialize `m_clrFillColor` varsayılan renkle.  
  
#### <a name="to-initialize-the-fill-color"></a>Dolgu rengi başlatmak için  
  
1.  Kullanın yeşil kullanılan varsayılan rengi bu satıra ekleyerek `CPolyCtl` PolyCtl.h oluşturucuda:  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 Oluşturucu şimdi şöyle görünür:  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## <a name="building-and-testing-the-control"></a>Derleme ve denetim test etme  
 Denetim yeniden oluşturun. PolyCtl.htm dosya hala açık değilse, kapalı olduğundan emin olun ve ardından **yapı Çokgen** üzerinde **yapı** menüsü. Denetim PolyCtl.htm sayfasından yine görüntüleyebilir, ancak bu kez ActiveX denetimi Test kapsayıcısı kullanır.  
  
#### <a name="to-use-the-activex-control-test-container"></a>ActiveX denetimi Test kapsayıcısı kullanmak için  
  
1.  Derleme ve ActiveX denetimi Test kapsayıcısı başlatın. Daha fazla bilgi için bkz: [TSTCON örnek: ActiveX denetimi Test kapsayıcısı](../visual-cpp-samples.md).  
  
2.  Test kapsayıcısı içinde üzerinde **Düzenle** menüsünde tıklatın **yeni denetimi Ekle**.  
  
3.  Çağrılacak denetiminizi bulun `PolyCtl Class`, tıklatıp **Tamam**. Yeşil bir üçgen içindeki bir daire görürsünüz.  
  
 Bir sonraki yordamı izleyerek kenar sayısını değiştirmeyi deneyin. Bir çift arabirimdeki Test kapsayıcısı içinde özelliklerini değiştirmek için kullanmak **çağırma yöntemleri**.  
  
#### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>Test kapsayıcısı içinde denetimin özelliğinden değiştirmek için  
  
1.  Test kapsayıcısı içinde tıklatın **çağırma yöntemleri** üzerinde **denetim** menüsü.  
  
     **Yöntemi çağırma** iletişim kutusu görüntülenir.  
  
2.  Seçin **PropPut** sürümü **kenara** özelliğinden **yöntem adı** aşağı açılan liste kutusu.  
  
3.  Tür `5` içinde **parametre değeri** kutusunda, **değeri ayarlanmış**, tıklatıp **Invoke**.  
  
 Denetim değişmeyen unutmayın. Kenar sayısını dahili olarak ayarlayarak değiştirdiğiniz rağmen `m_nSides` değişkeni, bu çizilecek denetimi neden oldu değil. Başka bir uygulamaya geçin ve sonra geri Test kapsayıcısı için geçiş denetimi yeniden çizilmiş ve kenara doğru sayıda bulacaksınız.  
  
 Bu sorunu düzeltmek için bir çağrı ekleyin `FireViewChange` tanımlanan işlevi `IViewObjectExImpl`, kenar sayısını ayarladıktan sonra. Denetim kendi penceresinde çalışıyorsa, `FireViewChange` çağıracak `InvalidateRect` doğrudan yöntemi. Denetim penceresiz, çalışıyorsa, `InvalidateRect` kapsayıcının site arabirimde yöntemi çağrılır. Bu, kendisini çizilecek denetimi zorlar.  
  
#### <a name="to-add-a-call-to-fireviewchange"></a>FireViewChange çağrısı ekleyin  
  
1.  PolyCtl.cpp çağrısı ekleyerek güncelleştirme `FireViewChange` için `put_Sides` yöntemi. İşiniz bittiğinde, `put_Sides` yöntemi aşağıdaki gibi görünmelidir:  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 Ekledikten sonra `FireViewChange`, yeniden oluşturun ve ActiveX denetimi Test kapsayıcısı denetiminde yeniden deneyin. Ne zaman kenarların sayısını değiştirmek ve tıklatın bu kez `Invoke`, hemen değiştirmek denetim görmeniz gerekir.  
  
 Sonraki adımda, bir olay ekleyeceksiniz.  
  
 [3. adım dön](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [adıma 5](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)   
 [Test Kapsayıcısı ile Özellikleri ve Olayları Test Etme](../mfc/testing-properties-and-events-with-test-container.md)

