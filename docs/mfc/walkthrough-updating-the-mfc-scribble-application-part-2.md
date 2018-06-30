---
title: 'İzlenecek yol: MFC karalama uygulamasını (Bölüm 2) güncelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bccc10e1aa2d984486c3cadfd45a14a6625ec959
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122411"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)

[Bölüm 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) klasik bir Office Fluent Şerit ekleme gösterdi bu kılavuzun uygulama karalama. Bu bölümü Şerit paneller ve kullanıcıların menüleri ve komutları yerine kullanabileceğiniz denetimleri nasıl ekleneceğini gösterir.

## <a name="prerequisites"></a>Önkoşullar

[Visual C++ Örnekleri](../visual-cpp-samples.md)

##  <a name="top"></a> Bölümler

Kılavuzun bu bölümü aşağıdaki bölümleri içerir:

- [Şerit'e yeni paneller ekleme](#addnewpanel)

- [Yardım Masası için Şerit ekleme](#addhelppanel)

- [Şerit'e bir kalem Panel ekleme](#addpenpanel)

- [Şerit'e bir renk düğmesi ekleme](#addcolorbutton)

- [Belge sınıfına renk üye ekleme](#addcolormember)

- [Kalemler başlatma ve tercihleri kaydetme](#initpensave)

##  <a name="addnewpanel"></a> Şerit'e yeni paneller ekleme

Bu adımlar nasıl ekleneceğini gösterir bir **Görünüm** araç çubuğu ve durum çubuğunun görünürlüğünü kontrol iki onay kutuları içeren paneli ve ayrıca bir **penceresi** dikey yönelimli bölme içeren paneli oluşturma ve düzenleme birden çok belge arabirimi (MDI) Windows denetimleri düğmesi.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Bir görünüm paneliyle ve pencere Şerit çubuğuna eklemek için

1. Adlı bir bölme oluşturmak `View`, araç çubuğu ve durum çubuğunu Değiştir iki onay kutularını sahiptir.

   1. Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. İki sürükleyin **onay kutularını** paneline.

   2. Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `View`.

   3. Özelliklerini değiştirmek için onay kutusuna tıklayın. Değişiklik **kimliği** için `ID_VIEW_TOOLBAR` ve **resim yazısı** için `Toolbar`.

   4. Özelliklerini değiştirmek için ikinci onay kutusuna tıklayın. Değişiklik **kimliği** için `ID_VIEW_STATUS_BAR` ve **resim yazısı** için `Status Bar`.

2. Adlı bir bölme oluşturmak `Window` Bölünmüş düğme vardır. Bir kullanıcı bölme düğmesine tıkladığında, bir kısayol menüsü karalama uygulamada önceden tanımlanmış üç komutları görüntüler.

   1. Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. Ardından sürükleyin bir **düğmesini** paneline.

   2. Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `Window`.

   3. Düğmesini tıklatın. Değişiklik **resim yazısı** için `Windows`, **anahtarları** için `w`, **büyük görüntü dizini** için `1`, ve **ayırma modu** için `False`. Üç nokta düğmesine (**...** ) yanındaki **menü öğeleri** açmak için **öğeleri Düzenleyicisi** iletişim kutusu.

   4. Tıklatın **Ekle** üç düğme eklemek için üç kez.

   5. İlk düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `New Window`, ve **kimliği** için `ID_WINDOW_NEW`.

   6. İkinci düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `Cascade`, ve **kimliği** için `ID_WINDOW_CASCADE`.

   7. Üçüncü düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `Tile`, ve **kimliği** için `ID_WINDOW_TILE_HORZ`.

3. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. **Görünüm** ve **penceresi** paneller görüntülenmesi. Düğmeleri düzgün şekilde çalıştıklarının onaylamak için tıklatın.

[[Bölümleri](#top)]

##  <a name="addhelppanel"></a> Yardım Masası için Şerit ekleme

Şimdi, karalama uygulamasını adlandırıldığı Şerit düğmeleri için tanımlanan iki menü öğeleri atayabilirsiniz **Yardım konuları** ve **hakkında karalama**. Düğmeleri adlı yeni bir paneline eklenen **yardımcı**.

### <a name="to-add-a-help-panel"></a>Yardım Masası eklemek için

1. Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. İki sürükleyin **düğmeleri** paneline.

2. Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `Help`.

3. İlk düğmesini tıklatın. Değişiklik **resim yazısı** için `Help Topics`, ve **kimliği** için `ID_HELP_FINDER`.

4. İkinci düğmesini tıklatın. Değişiklik **resim yazısı** için `About Scribble...`, ve **kimliği** için `ID_APP_ABOUT`.

5. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. A **yardımcı** iki Şerit düğmeleri içeren paneli görüntülenmesi.

   > [!IMPORTANT]
   > Tıkladığınızda **Yardım konuları** düğmesi, karalama uygulamasını açar adlı bir sıkıştırılmış (.chm) HTML Yardım dosyası *your_project_name*. chm. Projenizi karalama adlandırılmamışsa sonuç olarak, size yardım dosyasını proje adınızı yeniden adlandırmanız gerekir.

[[Bölümleri](#top)]

##  <a name="addpenpanel"></a> Şerit'e bir kalem Panel ekleme

Şimdi, kalınlığı ve kalemin rengini kontrol düğmeleri görüntülemek için bir panel ekleyin. Bu panoyu kalın ve ince kalemler arasında geçiş yapar bir onay kutusu içerir. İşlevselliği, benzer **Kalın çizgi** karalama uygulamasını menü öğesi.

Özgün karalama uygulamasını kullanıcının kullanıcı tıkladığında, görünen bir iletişim kutusundan kalem genişliği seçmesine olanak tanır **kalem genişliği** menüsünde. Şerit çubuğu yeni denetimler için yeterli yeri olduğundan, Şeritteki iki birleşik giriş kutuları kullanarak iletişim kutusunda değiştirebilirsiniz. Tek bir birleşik giriş kutusu ince kalem genişliği ayarlar ve diğer birleşik giriş kutusu kalın kalem genişliğini ayarlar.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Şerit kalem paneli ve birleşik giriş kutuları eklemek için

1. Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. Ardından sürükleyin bir **onay kutusunu** ve iki **birleşik giriş kutuları** paneline.

2. Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `Pen`.

3. Onay kutusuna tıklayın. Değişiklik **resim yazısı** için `Use Thick`, ve **kimliği** için `ID_PEN_THICK_OR_THIN`.

4. İlk açılan kutu'ı tıklatın. Değişiklik **resim yazısı** için `Thin Pen`, **kimliği** için `ID_PEN_THIN_WIDTH`, **metin** için `2`, **türü** için `Drop List`, ve **veri** için `1;2;3;4;5;6;7;8;9;`.

5. İkinci birleşik giriş kutusu'ı tıklatın. Değişiklik **resim yazısı** için `Thick Pen`, **kimliği** için `ID_PEN_THICK_WIDTH`, **metin** için `5`, **türü** için `Drop List`, ve **veri** için `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`.

6. Yeni birleşik giriş kutuları varolan tüm menü öğelerini karşılık gelmemelidir. Bu nedenle, her kalem seçeneği için bir menü öğesi oluşturmanız gerekir.

   1. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.

   2. Tıklatın **kalem** p açmak için**tr** menüsü. Ardından **burada türü** ve türü `Thi&n Pen`.

   3. Açmak için yazdığınız metni sağ **özellikleri** penceresi ve değişiklik kimliği özelliğini `ID_PEN_THIN_WIDTH`.

   4. Ayrıca her kalem menü öğesi için bir olay işleyicisi oluşturmanız gerekir. Sağ **düzeltmeyi & n kalem** yeni oluşturduğunuz ve ardından menü öğesi **olay işleyicisi ekleme**. **Olay işleyici Sihirbazı** görüntülenir.

   5. İçinde **sınıf listesi** Sihirbazı, select kutusunda **CScribbleDoc** ve ardından **ekleme ve düzenleme**. Bu adlı bir olay işleyicisi oluşturur `CScribbleDoc::OnPenThinWidth`.

   6. Aşağıdaki kodu ekleyin `CScribbleDoc::OnPenThinWidth`.

    ```cpp
    // Get a pointer to the ribbon bar
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
    ASSERT_VALID(pRibbon);

    // Get a pointer to the Thin Width combo box
    CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
    CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

    //Get the selected value
    int nCurSel = pThinComboBox->GetCurSel();
    if (nCurSel>= 0)
    {
        m_nThinWidth = atoi(pThinComboBox->GetItem(nCurSel));
    }
    
    // Create a new pen using the selected width
    ReplacePen();
    ```

7. Ardından, bir menü öğesi ve olay işleyicileri için kalın kalem oluşturun.

   1. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.

   2. Tıklatın **kalem** kalem menüsünü açın. Ardından **burada türü** ve türü `Thic&k Pen`.

   3. Görüntülenecek yazdığınız metni sağ **özellikleri** penceresi. ID özelliği değiştirmek `ID_PEN_THICK_WIDTH`.

   4. Sağ **kalın kalem** yeni oluşturduğunuz ve ardından menü öğesi **olay işleyicisi ekleme**. **Olay işleyici Sihirbazı** görüntülenir.

   5. İçinde **sınıf listesi** kutusu seçme Sihirbazı'nın **CScribbleDoc** ve ardından **ekleme ve düzenleme**. Bu adlı bir olay işleyicisi oluşturur `CScribbleDoc::OnPenThickWidth`.

   6. Aşağıdaki kodu ekleyin `CScribbleDoc::OnPenThickWidth`.

      ```cpp
      // Get a pointer to the ribbon bar
      CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
      ASSERT_VALID(pRibbon);

      CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
          CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
      // Get the selected value
      int nCurSel = pThickComboBox->GetCurSel();
      if (nCurSel>= 0)
      {
          m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));
      }
      
      // Create a new pen using the selected width
      ReplacePen();
      ```

8. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Yeni düğmeler ve birleşik giriş kutuları görüntülenmesi gerekir. Farklı kalem genişliği karalama kullanmayı deneyin.

[[Bölümleri](#top)]

##  <a name="addcolorbutton"></a> Kalem paneline renk düğme ekleme

Ardından, eklemek bir [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) kullanıcı sağlayan nesne karalama renkte.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Bir renk düğmesi kalem paneline eklemek için

1. Renk düğmesi eklemeden önce menü öğesi için oluşturun. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın. Tıklatın **kalem** kalem menüsünü açmak için menü öğesi. Ardından **burada türü** ve türü `&Color`. Görüntülenecek yazdığınız metni sağ **özellikleri** penceresi. Değişiklik kimliği `ID_PEN_COLOR`.

2. Renk düğmesi. Şimdi ekleyin. Gelen **araç**, sürükleyin bir **renk düğmesi** için **kalem** paneli.

3. Renk düğmesini tıklatın. Değişiklik **resim yazısı** için `Color`, **kimliği** için `ID_PEN_COLOR`, **SimpleLook** için `True`, **büyük görüntü dizini** için `1`, ve **ayırma modu** için `False`.

4. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Yeni renk düğmesi görüntülenmesi gerekip **kalem** paneli. Ancak, bir olay işleyicisi henüz olmadığı için kullanılamaz. Sonraki adımlar için renk düğmesi olay işleyicisi ekleme gösterir.

[[Bölümleri](#top)]

##  <a name="addcolormember"></a> Belge sınıfına renk üye ekleme

Özgün karalama uygulamasını renkli kalemler sahip olmadığından, onlar için bir uygulama yazmanız gerekir. Belge kalem rengini depolamak için yeni bir üye belge sınıfına ekleyin, `CscribbleDoc.`

### <a name="to-add-a-color-member-to-the-document-class"></a>Belge sınıfına renk üye eklemek için

1. Scribdoc.h içinde içinde `CScribbleDoc` sınıfı, Bul `// Attributes` bölümü. Aşağıdaki kod satırlarını sonra tanımını ekleyin `m_nThickWidth` veri üyesi.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

2. Her belge bir listesini içeren kullanıcı zaten çizilmiş çok tuş vuruşu. Her vuruş tarafından tanımlanan bir `CStroke` nesnesi. `CStroke` Sınıfı kalem rengi hakkında bilgi içermez. Bu nedenle, sınıf değiştirmeniz gerekir. Scribdoc.h içinde içinde `CStroke` sınıfında, aşağıdaki kod satırlarını sonra tanımını ekleyin `m_nPenWidth` veri üyesi.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

3. Scribdoc.h içinde yeni bir ekleme `CStroke` Oluşturucusu bir genişlik ve renk parametreleri belirtin. Koddan sonra aşağıdaki satırı ekleyin `CStroke(UINT nPenWidth);` deyimi.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

4. Yeni uygulama scribdoc.cpp içinde eklemek `CStroke` Oluşturucusu. Uygulamasının sonra aşağıdaki kodu ekleyin `CStroke::CStroke(UINT nPenWidth)` Oluşturucusu.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

5. İkinci satırı değiştirmek `CStroke::DrawStroke` yöntemini aşağıdaki şekilde.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

6. Belge sınıfı varsayılan kalem rengini ayarlayın. Scribdoc.cpp içinde aşağıdaki satırları ekleyin `CScribbleDoc::InitDocument`, sonra `m_nThickWidth = 5;` deyimi.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

7. İlk satırı scribdoc.cpp içinde değiştirmek `CScribbleDoc::NewStroke` şu yöntemi.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

8. Son satırının değiştirmek `CScribbleDoc::ReplacePen` şu yöntemi.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

9. Eklediğiniz `m_penColor` bir önceki adımda üye. Şimdi, üye ayarlar renk düğmesi olay işleyicisi oluşturun.

   1. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.

   2. Sağ **renk** menü öğesi ve tıklatın **olay işleyicisi ekleme**. **Olay işleyici Sihirbazı** görüntülenir.

   3. İçinde **sınıf listesi** Sihirbazı, select kutusunda **CScribbleDoc** ve ardından **ekleme ve düzenleme** düğmesi. Bu oluşturur `CScribbleDoc::OnPenColor` olay işleyicisi saplama.

10. Saplama için değiştirme `CScribbleDoc::OnPenColor` aşağıdaki kod ile olay işleyicisi.

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

11. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Renk düğmesine basın ve Kalem rengi değiştirin yapabiliyor olmanız gerekir.

[[Bölümleri](#top)]

##  <a name="initpensave"></a> Kalemler başlatma ve tercihleri kaydetme

Ardından, rengini ve genişliğini kalemler başlatır. Son olarak, kaydedin ve bir dosyadan çizim renk yükleyin.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Şerit çubuğundaki denetimlerinin başlatmak için

1. Şerit çubuğunda kalemler başlatır.

   Scribdoc.cpp için aşağıdaki kodu ekleyin `CScribbleDoc::InitDocument` yöntemi, sonra `m_sizeDoc = CSize(200,200)` deyimi.

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

2. Bir dosyaya çizim renk kaydedin. Scribdoc.cpp, şu deyimi eklemek `CStroke::Serialize` yöntemi, sonra `ar << (WORD)m_nPenWidth;` deyimi.

   ```cpp
   ar << (COLORREF)m_penColor;
    ```

3. Son olarak, bir dosyadan çizim renk yükleyin. Kod, aşağıdaki satırı ekleyin `CStroke::Serialize` yöntemi, sonra `m_nPenWidth = w;` deyimi.

   ```cpp
   ar >> m_penColor;
   ```

4. Şimdi renkte karalama ve, çizim bir dosyaya kaydedin.

[[Bölümleri](#top)]

## <a name="conclusion"></a>Sonuç

MFC karalama uygulamasını güncelleştirdiniz. Mevcut uygulamalarınızı değişiklik yaptığınızda bu kılavuzda bir kılavuz olarak kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)  
[İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (1. Bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)  
