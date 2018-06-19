---
title: Durum çubuğu bölmesinin metnini güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbb2f14f274be3c7282a897c271049fe46434f3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384484"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Durum Çubuğu Bölmesinin Metnini Güncelleştirme
Bu makalede, bir MFC durum çubuğu bölmesinde görüntülenen metni değiştirme açıklanmaktadır. Durum çubuğu — bir pencere nesnesi sınıfının [CStatusBar](../mfc/reference/cstatusbar-class.md) — içeren birkaç "bölmeleri." Her bölme bilgilerini görüntülemek için kullanabileceğiniz durum çubuğu dikdörtgen bir alandır. Örneğin, birçok uygulama en sağdaki bölmelerinde CAPS LOCK, NUM LOCK ve diğer anahtarlar durumunu görüntüleyin. Uygulamalar ayrıca sıklıkla bilgilendirici metinde soldaki bölmesi (0), "iletisi bölme." olarak da adlandırılır görüntüleme Örneğin, varsayılan MFC durum çubuğu ileti bölmesinde seçili menü öğesi veya araç çubuğu düğmesi açıklayan bir dize göstermek için kullanır. Şekil [durum çubukları](../mfc/status-bar-implementation-in-mfc.md) MFC Uygulama Sihirbazı tarafından oluşturulan uygulamadan durum çubuğunu gösterir.  
  
 Varsayılan olarak, MFC etkinleştirmemeniz bir `CStatusBar` bölmesinde oluşturduğunda bölmesi. Bir bölme etkinleştirmek için kullanmanız gerekir `ON_UPDATE_COMMAND_UI` makrosu durumu ile ilgili her bölme için çubuk ve bölmeleri güncelleştirin. Bölmeleri göndermemek çünkü **WM_COMMAND** iletileri (bunlar, araç çubuğu düğmeleri gibi değil), el ile kod yazmanız gerekir.  
  
 Örneğin, bir bölme olduğunu varsayalım `ID_INDICATOR_PAGE` komut tanımlayıcısını ve, bir belgedeki geçerli sayfa numarası içerir. Aşağıdaki yordam, yeni bir bölme durum çubuğunda oluşturmayı açıklar.  
  
### <a name="to-make-a-new-pane"></a>Yeni bir bölme yapma  
  
1.  Bölmesinde ait komut kimliği tanımlayın  
  
     Üzerinde **Görünüm** menüsünde tıklatın **kaynak görünümü**. Proje kaynağı sağ tıklatın ve **kaynak semboller**. Kaynak sembolleri iletişim kutusu tıklatın `New`. Komut Kimliği adını yazın: Örneğin, `ID_INDICATOR_PAGE`. Kimliği için bir değer belirtin veya kaynak sembolleri iletişim kutusu tarafından önerilen değeri kabul edin. Örneğin, `ID_INDICATOR_PAGE`, varsayılan değeri kabul edin. Kaynak sembolleri iletişim kutusunu kapatın.  
  
2.  Bölmesinde görüntülemek için bir varsayılan dizesi tanımlayın.  
  
     Açık kaynak görünümü ile çift **dize tablosu** penceresinde uygulamanız için kaynak türlerini listeler. İle **dize tablosu** Düzenleyicisi'ni açın, seçin **yeni bir dize** gelen **Ekle** menüsü. Dize özellikleri penceresinde bölmesinde ait komut kimliği seçin (örneğin, `ID_INDICATOR_PAGE`) ve "Sayfa" gibi bir varsayılan dize değerini yazın. Dize Düzenleyicisi'ni kapatın. (Derleyici Hatası önlemek için bir varsayılan dizesi gerekir.)  
  
3.  Bölmesine eklemek **göstergeleri** dizi.  
  
     Dosya MAINFRM. CPP, bulun **göstergeleri** dizi. Bu dizinin tüm soldan sağa doğru sırayla durum çubuğunun göstergeleri için komut kimliklerini listeler. Dizideki uygun noktada bölmesinde ait komut kimliği, için aşağıda gösterildiği gibi girin `ID_INDICATOR_PAGE`:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 Metin bir bölmesinde görüntülemek için önerilen yöntem çağırmaktır **SetText** sınıfının üye işlevini `CCmdUI` bölmesi için bir güncelleştirme işleyici işlevinde. Örneğin, bir tamsayı değişken ayarlamak isteyebilirsiniz `m_nPage` geçerli sayfa numarası ve kullanım içeren **SetText** Bölmesi'nin metin bu sayıyı dize sürümüne ayarlamak için.  
  
> [!NOTE]
>  **SetText** yaklaşım önerilir. Çağırarak biraz daha düşük düzeyde bu görevi gerçekleştirmek mümkündür `CStatusBar` üye işlevi `SetPaneText`. Buna rağmen yine bir güncelleştirme işleyici gerekir. Bu tür için bir işleyici bölmesi, MFC otomatik olarak bölmesinde içeriği silmeyi devre dışı bırakır.  
  
 Aşağıdaki yordam Bölmesi'nde metni görüntülemek için bir güncelleştirme işleyici işlevi kullanmayı gösterir.  
  
#### <a name="to-make-a-pane-display-text"></a>Metin görüntüleme bölmesinde yapma  
  
1.  Komutu için bir komut güncelleştirme işleyici ekleyin.  
  
     Bir prototip işleyici için aşağıda gösterildiği gibi el ile eklemeniz `ID_INDICATOR_PAGE` (içinde MAINFRM. H):  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  Uygun. CPP dosya, için aşağıda gösterildiği gibi işleyicinin tanımı ekleme `ID_INDICATOR_PAGE` (içinde MAINFRM. CPP):  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     Bu işleyici ilk üç satırını metninizi görüntüler kodu var.  
  
3.  Uygun bir mesaj eşlemesinde eklemek `ON_UPDATE_COMMAND_UI` için aşağıda gösterildiği gibi makrosu `ID_INDICATOR_PAGE` (içinde MAINFRM. CPP):  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 Değerini tanımladıktan sonra `m_nPage` üye değişkeni (sınıfının `CMainFrame`), bu teknik bölmesinde boşta işleme sırasında uygulama başka göstergelerle güncelleştirir aynı şekilde görünmesi sayfa numarası neden olur. Varsa `m_nPage` değişiklikleri, değişikliklerin sonraki boşta döngü sırasında gösterme.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [(Araç çubuğu düğmeleri ve menü öğeleri program koşullar değiştikçe nasıl güncelleştirileceği) kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de durum çubuğu uygulaması](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar Sınıfı](../mfc/reference/cstatusbar-class.md)
