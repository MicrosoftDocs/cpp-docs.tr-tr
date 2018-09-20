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
ms.openlocfilehash: 351aea09376d6cba7f091828225fd337fa3f68e1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423188"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)

[1. bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) Klasik'ten Office Fluent Şerit ekleme gösterdi bu kılavuzun uygulama karalama. Bu bölüm, Şerit paneli ve kullanıcıların, menüler ve komutlar yerine kullanabileceği denetimler ekleme işlemi gösterilmektedir.

## <a name="prerequisites"></a>Önkoşullar

[Visual C++ Örnekleri](../visual-cpp-samples.md)

##  <a name="top"></a> Bölümleri

Kılavuzun bu bölümü aşağıdaki bölümleri içerir:

- [Şerit için yeni bir panel ekleme](#addnewpanel)

- [Şerit için bir Yardım Masası ekleme](#addhelppanel)

- [Şerit için bir kalem Panel ekleme](#addpenpanel)

- [Şerit rengi düğmesi ekleme](#addcolorbutton)

- [Belge sınıfına renk üye ekleme](#addcolormember)

- [Kalemler başlatma ve tercihlerini kaydediliyor](#initpensave)

##  <a name="addnewpanel"></a> Şerit için yeni bir panel ekleme

Bu adımları nasıl ekleneceğini göstermektedir bir **görünümü** araç çubuğu ve durum çubuğunun görünürlüğünü denetleme iki onay kutuları içeren paneli ve ayrıca bir **penceresi** dikey yönlendirilmiş bir bölme içeren paneli denetimleri oluşturma ve düzenleme Windows Çok Belgeli Arabirim (MDI) düğmesi.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Görüntüleme paneli ve pencere paneli Şerit çubuğuna eklemek için

1. Adlı bir panel oluşturma `View`, araç çubuğu ve durum çubuğu geçiş iki onay kutularını sahiptir.

   1. Gelen **araç kutusu**, sürükleyin bir **paneli** için **giriş** kategorisi. İki sürükleyin **onay kutularını** paneline.

   2. Bölmenin özelliklerini değiştirmek için tıklayın. Değişiklik **açıklamalı alt yazı** için `View`.

   3. Özelliklerini değiştirmek için onay kutusuna tıklayın. Değişiklik **kimliği** için `ID_VIEW_TOOLBAR` ve **açıklamalı alt yazı** için `Toolbar`.

   4. Özelliklerini değiştirmek için ikinci onay kutusuna tıklayın. Değişiklik **kimliği** için `ID_VIEW_STATUS_BAR` ve **açıklamalı alt yazı** için `Status Bar`.

2. Adlı bir panel oluşturma `Window` , Bölünmüş düğme vardır. Kullanıcı bölünmüş düğmeye tıkladığında bir kısayol menüsünü karalama uygulamada zaten tanımlanmış olan üç komutları görüntüler.

   1. Gelen **araç kutusu**, sürükleyin bir **paneli** için **giriş** kategorisi. Ardından bir **düğmesi** paneline.

   2. Bölmenin özelliklerini değiştirmek için tıklayın. Değişiklik **açıklamalı alt yazı** için `Window`.

   3. Düğmesine tıklayın. Değişiklik **açıklamalı alt yazı** için `Windows`, **anahtarları** için `w`, **büyük görüntü dizini** için `1`, ve **ayırma modu** için `False`. Ardından üç nokta simgesine tıklayın (**...** ) yanındaki **menü öğeleri** açmak için **öğe düzenleyici** iletişim kutusu.

   4. Tıklayın **Ekle** üç düğme eklemek için üç kez.

   5. İlk düğmeyi tıklayın ve ardından değiştirmek **açıklamalı alt yazı** için `New Window`, ve **kimliği** için `ID_WINDOW_NEW`.

   6. İkinci düğmeye tıklayın ve ardından değiştirmek **açıklamalı alt yazı** için `Cascade`, ve **kimliği** için `ID_WINDOW_CASCADE`.

   7. Üçüncü düğmeye tıklayın ve ardından değiştirmek **açıklamalı alt yazı** için `Tile`, ve **kimliği** için `ID_WINDOW_TILE_HORZ`.

3. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. **Görünümü** ve **penceresi** panelleri görüntülenmesi gerekir. Düğmeleri düzgün şekilde çalıştıklarını doğrulamak için tıklayın.

[[Bölümleri](#top)]

##  <a name="addhelppanel"></a> Şerit için bir Yardım Masası ekleme

Artık, adlandırılmış Şerit düğmeleri karalama uygulama tanımlı iki menü öğesi atayabilirsiniz **Yardım konuları** ve **hakkında karalama**. Düğmeleri adlı yeni bir panel eklenen **yardımcı**.

### <a name="to-add-a-help-panel"></a>Yardım Masası eklemek için

1. Gelen **araç kutusu**, sürükleyin bir **paneli** için **giriş** kategorisi. İki sürükleyin **düğmeleri** paneline.

2. Bölmenin özelliklerini değiştirmek için tıklayın. Değişiklik **açıklamalı alt yazı** için `Help`.

3. İlk düğmeyi tıklayın. Değişiklik **açıklamalı alt yazı** için `Help Topics`, ve **kimliği** için `ID_HELP_FINDER`.

4. İkinci düğmeye tıklayın. Değişiklik **açıklamalı alt yazı** için `About Scribble...`, ve **kimliği** için `ID_APP_ABOUT`.

5. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. A **yardımcı** iki Şerit düğmeleri içeren bir panel görüntülenmesi gerekir.

   > [!IMPORTANT]
   > Tıkladığınızda **Yardım konuları** düğme, karalama uygulamasını açar adlı bir sıkıştırılmış (.chm) HTML Yardım dosyasını *your_project_name*. chm. Sonuç olarak, projenizin karalama adlı değil, proje adınız Yardım dosyasını adlandırmalısınız.

[[Bölümleri](#top)]

##  <a name="addpenpanel"></a> Şerit için bir kalem Panel ekleme

Bir paneli kalınlığı ve kalem rengini denetlemek düğmeleri görüntülemek için şimdi ekleyin. Bu panelde kalın ve ince kalemler arasında değişen bir onay kutusu içerir. İşlevselliğini değeriyle benzer **Kalın çizgi** karalama uygulamasını menü öğesi.

Özgün karalama uygulamasını kalem genişliği kullanıcı tıkladığında görüntülenen iletişim kutusundan seçmesine izin verir **kalem genişliği** menüsünde. Şerit çubuğuna yeni denetimler için yeterli alan olduğundan, Şerit üzerinde iki birleşik giriş kutuları kullanarak iletişim kutusunda değiştirebilirsiniz. Tek bir birleşik giriş kutusu genişliği ince Kalem, ayarlar ve bir birleşik giriş kutusu kalın kalem genişliği ayarlar.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Şerit kalem paneli ve birleşik giriş kutuları eklemek için

1. Gelen **araç kutusu**, sürükleyin bir **paneli** için **giriş** kategorisi. Ardından bir **onay kutusunu** ve iki **birleşik giriş kutuları** paneline.

2. Bölmenin özelliklerini değiştirmek için tıklayın. Değişiklik **açıklamalı alt yazı** için `Pen`.

3. Onay kutusuna tıklayın. Değişiklik **açıklamalı alt yazı** için `Use Thick`, ve **kimliği** için `ID_PEN_THICK_OR_THIN`.

4. İlk birleşik giriş kutusuna tıklayın. Değişiklik **açıklamalı alt yazı** için `Thin Pen`, **kimliği** için `ID_PEN_THIN_WIDTH`, **metin** için `2`, **türü** için `Drop List`, ve **veri** için `1;2;3;4;5;6;7;8;9;`.

5. İkinci birleşik giriş kutusuna tıklayın. Değişiklik **açıklamalı alt yazı** için `Thick Pen`, **kimliği** için `ID_PEN_THICK_WIDTH`, **metin** için `5`, **türü** için `Drop List`, ve **veri** için `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`.

6. Yeni bir birleşik giriş kutuları için mevcut tüm menü öğelerini karşılık gelmez. Bu nedenle, her kalem seçeneği için bir menü öğesi oluşturmanız gerekir.

   1. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.

   2. Tıklayın **kalem** p açmak için**tr** menüsü. Ardından **türü burada** ve türü `Thi&n Pen`.

   3. Açmak için yazdığınız metnin sağ **özellikleri** penceresi ve değişiklik kimliği özelliğini `ID_PEN_THIN_WIDTH`.

   4. Ayrıca, her bir kalem menü öğesi için bir olay işleyicisi oluşturmanız gerekir. Sağ **düzeltmeyi & n kalem** oluşturduğunuz ve ardından menü öğesi **olay işleyici Ekle**. **Olay işleyici Sihirbazı** görüntülenir.

   5. İçinde **sınıf listesi** Sihirbazı, seçim kutusunda **CScribbleDoc** ve ardından **ekleme ve düzenleme**. Bu adlı bir olay işleyicisi oluşturur `CScribbleDoc::OnPenThinWidth`.

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

   2. Tıklayın **kalem** kalem menüsünü açmak için. Ardından **türü burada** ve türü `Thic&k Pen`.

   3. Görüntülenecek yazdığınız metnin sağ **özellikleri** penceresi. Kimliği özelliğini değiştirmek `ID_PEN_THICK_WIDTH`.

   4. Sağ **kalın kalem** oluşturduğunuz ve ardından menü öğesi **olay işleyici Ekle**. **Olay işleyici Sihirbazı** görüntülenir.

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

8. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Yeni düğmeler ve birleşik giriş kutusu görüntülenmelidir. Farklı kalem genişliği karalama kullanmayı deneyin.

[[Bölümleri](#top)]

##  <a name="addcolorbutton"></a> Kalem paneline bir renk düğmesi ekleme

Ardından, ekleme bir [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) kullanıcının sağlayan nesne karalama renk.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Kalem paneline bir renk düğmesi eklemek için

1. Renk düğmesi eklemeden önce bir menü öğesi için oluşturun. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın. Tıklayın **kalem** kalem menüsünü açmak için menü öğesi. Ardından **türü burada** ve türü `&Color`. Görüntülenecek yazdığınız metnin sağ **özellikleri** penceresi. Kimliği değiştirme `ID_PEN_COLOR`.

2. Şimdi renk düğmesi ekleyin. Gelen **araç kutusu**, sürükleyin bir **rengi düğmesi** için **kalem** paneli.

3. Renk düğmesine tıklayın. Değişiklik **açıklamalı alt yazı** için `Color`, **kimliği** için `ID_PEN_COLOR`, **SimpleLook** için `True`, **büyük görüntü dizini** için `1`, ve **ayırma modu** için `False`.

4. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Yeni renk düğmesinin görüntülenmesi **kalem** paneli. Ancak, bir olay işleyicisi henüz olmadığı için kullanılamaz. Sonraki adımlarda, bir renk düğmesi olay işleyicisi eklemek gösterilmektedir.

[[Bölümleri](#top)]

##  <a name="addcolormember"></a> Belge sınıfına renk üye ekleme

Özgün karalama uygulamasını renkli kalemler sahip olmadığından, bunlar için bir uygulama yazması gerekir. Belge kalem rengini depolamak için yeni bir üye belge sınıfına ekleyin, `CscribbleDoc.`

### <a name="to-add-a-color-member-to-the-document-class"></a>Belge sınıfına bir renk üye eklemek için

1. İçinde scribdoc.h, içinde `CScribbleDoc` sınıfı, Bul `// Attributes` bölümü. Aşağıdaki kod satırlarını sonra tanımını ekleyin `m_nThickWidth` veri üyesi.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

2. Her belgenin bir listesini içeren bir kullanıcı zaten çizilmiştir çok tuş vuruşu. Her vuruş tarafından tanımlanan bir `CStroke` nesne. `CStroke` Sınıfı kalem rengi hakkında bilgi içermez. Bu nedenle, sınıf değiştirmeniz gerekir. İçinde scribdoc.h, içinde `CStroke` sınıfı, sonra tanımını aşağıdaki kod satırlarını ekleme `m_nPenWidth` veri üyesi.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

3. Scribdoc.h içinde yeni bir ekleme `CStroke` Oluşturucusu genişliği ve rengine parametreleri belirtin. Kod sonra aşağıdaki satırı ekleyin `CStroke(UINT nPenWidth);` deyimi.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

4. Scribdoc.cpp içinde yeni uygulama Ekle `CStroke` Oluşturucusu. Uygulamasını sonra aşağıdaki kodu ekleyin `CStroke::CStroke(UINT nPenWidth)` Oluşturucusu.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

5. İkinci satırı değiştirin `CStroke::DrawStroke` yöntemini aşağıdaki şekilde.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

6. Belge sınıfı için varsayılan kalem rengini ayarlayın. Scribdoc.cpp aşağıdaki satırları ekleyin `CScribbleDoc::InitDocument`, sonra `m_nThickWidth = 5;` deyimi.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

7. İlk satırı scribdoc.cpp içinde değiştirmek `CScribbleDoc::NewStroke` aşağıdaki yöntemi.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

8. Son satırının değiştirme `CScribbleDoc::ReplacePen` aşağıdaki yöntemi.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

9. Eklediğiniz `m_penColor` üyesi bir önceki adımda. Artık üyesini ayarlar rengi düğmesi için bir olay işleyicisi oluşturun.

   1. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.

   2. Sağ **renk** menü öğesi ve tıklatın **olay işleyici Ekle**. **Olay işleyici Sihirbazı** görünür.

   3. İçinde **sınıf listesi** Sihirbazı, seçim kutusunda **CScribbleDoc** ve ardından **ekleme ve düzenleme** düğmesi. Bu oluşturur `CScribbleDoc::OnPenColor` olay işleyicisi taslağı.

10. Yer tutucusu için değiştirin `CScribbleDoc::OnPenColor` aşağıdaki kod ile olay işleyicisi.

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

11. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Renk düğmesine basın ve kalem rengini değiştirmek mümkün olması gerekir.

[[Bölümleri](#top)]

##  <a name="initpensave"></a> Kalemler başlatma ve tercihlerini kaydediliyor

Ardından, rengini ve genişliğini kalemler başlatın. Son olarak, kaydedin ve bir dosyadan çizim bir renk yükleyin.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Şerit çubuğundaki denetimleri başlatılamadı

1. Şerit çubuğunda kalemler başlatın.

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

2. Bir dosyaya çizim bir renk kaydedin. Scribdoc.cpp, aşağıdaki deyime ekleme `CStroke::Serialize` yöntemi, sonra `ar << (WORD)m_nPenWidth;` deyimi.

   ```cpp
   ar << (COLORREF)m_penColor;
    ```

3. Son olarak, bir dosyadan çizim bir renk yükleyin. Aşağıdaki kod satırını ekleyin `CStroke::Serialize` yöntemi, sonra `m_nPenWidth = w;` deyimi.

   ```cpp
   ar >> m_penColor;
   ```

4. Şimdi renk karalama ve çiziminize bir dosyaya kaydedin.

[[Bölümleri](#top)]

## <a name="conclusion"></a>Sonuç

MFC karalama uygulamasını güncelleştirdik. Bu izlenecek yol, mevcut uygulamalarınızı değiştirdiğinizde bir kılavuz olarak kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (1. Bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
