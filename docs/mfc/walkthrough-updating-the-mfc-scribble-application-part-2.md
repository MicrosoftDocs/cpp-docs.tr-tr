---
description: 'Daha fazla bilgi edinin: Izlenecek yol: MFC karalama uygulamasını güncelleştirme (2. bölüm)'
title: 'İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: 2520ac8fc1c66a2fc388738d22f4851547b6d03b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142967"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)

Bu izlenecek yolda bulunan [1. Bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) , Klasik karalama uygulamasına nasıl ofis akıcı bir şerit ekleneceğini gösterdi. Bu bölüm, kullanıcıların menüler ve komutlar yerine kullanabileceği şerit panellerinin ve denetimlerin nasıl ekleneceğini gösterir.

## <a name="prerequisites"></a>Önkoşullar

[Visual C++ Örnekleri](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a> Başlıklı

İzlenecek yolun bu bölümü aşağıdaki bölümlere sahiptir:

- [Şerite yeni paneller ekleme](#addnewpanel)

- [Şerite yardım paneli ekleme](#addhelppanel)

- [Şerite kalem paneli ekleme](#addpenpanel)

- [Şerite bir renk düğmesi ekleme](#addcolorbutton)

- [Belge sınıfına bir renk üyesi ekleme](#addcolormember)

- [Kalemleri başlatma ve tercihleri kaydetme](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a> Şerite yeni paneller ekleme

Bu adımlar, araç çubuğunun ve durum çubuğunun görünürlüğünü denetleyen iki onay kutusu içeren bir **Görünüm** panelinin nasıl ekleneceğini ve ayrıca birden çok belge ARABIRIMI (MDI) pencerelerinin oluşturulmasını ve düzenlemesini denetleyen dikey yönelimli bir bölünmüş düğme Içeren bir **pencere** bölmesi gösterir.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Şerit çubuğuna bir görünüm paneli ve pencere paneli eklemek için

1. `View`Durum çubuğunu ve araç çubuğunu açıp iki onay kutusu olan adlı bir panel oluşturun.

   1. **Araç kutusundan** bir **paneli** **giriş** kategorisine sürükleyin. Sonra iki **onay kutusunu** panele sürükleyin.

   1. Özelliklerini değiştirmek için panele tıklayın. **Açıklamalı alt yazı** değiştirin `View` .

   1. Özelliklerini değiştirmek için ilk onay kutusuna tıklayın. **Kimliği** `ID_VIEW_TOOLBAR` ve **başlık** olarak değiştirin `Toolbar` .

   1. Özelliklerini değiştirmek için ikinci onay kutusuna tıklayın. **Kimliği** `ID_VIEW_STATUS_BAR` ve **başlık** olarak değiştirin `Status Bar` .

1. Bölünmüş düğmeye sahip adlı bir panel oluşturun `Window` . Kullanıcı Böl düğmesine tıkladığında, bir kısayol menüsü, karalama uygulamasında zaten tanımlanmış üç komutu görüntüler.

   1. **Araç kutusundan** bir **paneli** **giriş** kategorisine sürükleyin. Ardından bir **düğmeyi** panele sürükleyin.

   1. Özelliklerini değiştirmek için panele tıklayın. **Açıklamalı alt yazı** değiştirin `Window` .

   1. Düğmesine tıklayın. **Açıklamalı** alt yazı `Windows` , **anahtarlar** , `w` **büyük görüntü dizini** `1` ve **bölme moduna** değiştirin `False` . Ardından **menü öğeleri** ' nin yanındaki üç nokta (**...**) simgesine tıklayarak **öğeler düzenleyici** iletişim kutusunu açın.

   1. Üç düğme eklemek için üç kez **Ekle** ' ye tıklayın.

   1. İlk düğmesine tıklayın ve ardından açıklamalı alt **yazısını** `New Window` ve **kimliğini** olarak değiştirin `ID_WINDOW_NEW` .

   1. İkinci düğmeye tıklayın ve ardından açıklamalı alt **yazısını** `Cascade` ve **kimliğini** değiştirin `ID_WINDOW_CASCADE` .

   1. Üçüncü düğmesine tıklayın ve ardından açıklamalı alt **yazısını** `Tile` ve **kimliğini** olarak değiştirin `ID_WINDOW_TILE_HORZ` .

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. **Görünüm** ve **pencere** panelleri görüntülenmelidir. Doğru şekilde çalıştıklarından emin olmak için düğmelere tıklayın.

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a> Şerite yardım paneli ekleme

Şimdi, karalama uygulamasında tanımlanmış iki menü öğesini, **Yardım konuları** ve **karalama hakkında** şerit düğmelerine atayabilirsiniz. Düğmeler **Yardım** adlı yeni bir panele eklenir.

### <a name="to-add-a-help-panel"></a>Yardım paneli eklemek için

1. **Araç kutusundan** bir **paneli** **giriş** kategorisine sürükleyin. Sonra iki **düğmeyi** panele sürükleyin.

1. Özelliklerini değiştirmek için panele tıklayın. **Açıklamalı alt yazı** değiştirin `Help` .

1. İlk düğmesine tıklayın. **Açıklamalı** alt yazısını `Help Topics` ve **kimliğini** değiştirin `ID_HELP_FINDER` .

1. İkinci düğmeye tıklayın. **Açıklamalı** alt yazısını `About Scribble...` ve **kimliğini** değiştirin `ID_APP_ABOUT` .

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. İki Şerit düğmesi içeren bir **Yardım** paneli görüntülenmelidir.

   > [!IMPORTANT]
   > **Yardım konuları** düğmesine tıkladığınızda, karalama uygulaması *your_project_name*. chm adlı bir sıkıştırılmış HTML (. chm) Yardım dosyası açar. Sonuç olarak, projeniz karalama olarak adlandırılmışsa, yardım dosyasını proje adınızla yeniden adlandırmanız gerekir.

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a> Şerite kalem paneli ekleme

Şimdi, kalemin kalınlığını ve rengini denetleyen düğmeleri görüntüleyen bir panel ekleyin. Bu panel, kalın ve ince kalemler arasında geçiş yapan bir onay kutusu içerir. İşlevselliği, karalama uygulamasındaki **kalın çizgi** menü öğesinin işlevselliğine benzer.

Özgün karalama uygulaması, kullanıcının menüdeki **Kalem genişlikleri** ' ne tıkladığında görüntülenen iletişim kutusundan Kalem genişlikleri seçmesini sağlar. Şerit çubuğunun yeni denetimler için geniş bir yeri olduğundan, şeritte iki Birleşik giriş kutusu kullanarak iletişim kutusunu değiştirebilirsiniz. Bir Birleşik giriş kutusu ince kalemin genişliğini ayarlar ve diğer açılan kutu kalın kalemin genişliğini ayarlar.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Şerite bir kalem paneli ve Birleşik giriş kutuları eklemek için

1. **Araç kutusundan** bir **paneli** **giriş** kategorisine sürükleyin. Ardından, bir **onay kutusunu** ve Iki **Birleşik giriş** kutusunu panele sürükleyin.

1. Özelliklerini değiştirmek için panele tıklayın. **Açıklamalı alt yazı** değiştirin `Pen` .

1. Onay kutusuna tıklayın. **Açıklamalı** alt yazısını `Use Thick` ve **kimliğini** değiştirin `ID_PEN_THICK_OR_THIN` .

1. İlk açılan kutuya tıklayın. **Açıklamalı alt yazı** , `Thin Pen` **kimlik** , `ID_PEN_THIN_WIDTH` tür  , tür `Drop List` , **veri** `1;2;3;4;5;6;7;8;9;` ve **metin** olarak değiştirin `2` .

1. İkinci Birleşik giriş kutusuna tıklayın. **Açıklamalı alt yazı** , `Thick Pen` **kimlik** , `ID_PEN_THICK_WIDTH` tür  , tür `Drop List` , **veri** `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;` ve **metin** olarak değiştirin `5` .

1. Yeni Birleşik giriş kutuları mevcut menü öğelerine karşılık gelmiyor, bu nedenle her kalem seçeneği için bir menü öğesi oluşturmanız gerekir.

   1. **Kaynak görünümü** penceresinde **IDR_SCRIBBTYPE** menü kaynağını açın.

   1. Kalem menüsünü açmak için **kalem** ' e tıklayın. Ardından **buraya yaz** ' a tıklayın ve yazın `Thi&n Pen` .

   1. **Özellikler** penceresini açmak için yazdığınız metni sağ tıklatın ve ardından kimlik özelliğini olarak değiştirin `ID_PEN_THIN_WIDTH` .

   1. Her kalem menü öğesi için bir olay işleyicisi oluşturun. Oluşturduğunuz **Thi&n kalem** menü öğesine sağ tıklayın ve ardından **olay işleyicisi Ekle**' ye tıklayın. **Olay Işleyicisi Sihirbazı** görüntülenir.

   1. Sihirbazdaki **sınıf listesi** kutusunda **Ckaralama bblidoc** ' ı seçin ve ardından **Ekle ve Düzenle**' ye tıklayın. Komut adlı bir olay işleyicisi oluşturur `CScribbleDoc::OnPenThinWidth` .

   1. Aşağıdaki kodu öğesine ekleyin `CScribbleDoc::OnPenThinWidth` .

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
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Ardından, kalın kalem için bir menü öğesi ve olay işleyicileri oluşturun.

   1. **Kaynak görünümü** penceresinde **IDR_SCRIBBTYPE** menü kaynağını açın.

   1. Kalem menüsünü açmak için **kalem** ' e tıklayın. Ardından **buraya yaz** ' a tıklayın ve yazın `Thic&k Pen` .

   1. **Özellikler** penceresini göstermek için yazdığınız metne sağ tıklayın. ID özelliğini olarak değiştirin `ID_PEN_THICK_WIDTH` .

   1. Oluşturduğunuz **kalın kalem** menü öğesine sağ tıklayın ve ardından **olay işleyicisi Ekle**' ye tıklayın. **Olay Işleyicisi Sihirbazı** görüntülenir.

   1. Sihirbazın **sınıf listesi** kutusunda **Ckaralama bblidoc** ' ı seçin ve ardından **Ekle ve Düzenle**' ye tıklayın. Komut adlı bir olay işleyicisi oluşturur `CScribbleDoc::OnPenThickWidth` .

   1. Aşağıdaki kodu öğesine ekleyin `CScribbleDoc::OnPenThickWidth` .

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
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Yeni düğmeler ve Birleşik giriş kutuları görüntülenmelidir. Karalama için farklı Kalem genişlikleri kullanmayı deneyin.

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a> Kalem paneline renk düğmesi ekleme

Daha sonra, kullanıcının renkli olarak çalışmasına imkan tanıyan bir [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) nesnesi ekleyin.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Kalem paneline renk düğmesi eklemek için

1. Renk düğmesini eklemeden önce, bir menü öğesi oluşturun. **Kaynak görünümü** penceresinde **IDR_SCRIBBTYPE** menü kaynağını açın. Kalem menüsünü açmak için **kalem** menü öğesine tıklayın. Ardından **buraya yaz** ' a tıklayın ve yazın `&Color` . **Özellikler** penceresini göstermek için yazdığınız metne sağ tıklayın. KIMLIĞI olarak değiştirin `ID_PEN_COLOR` .

1. Şimdi renk düğmesini ekleyin. **Araç kutusundan** **kalem** paneline bir **renk düğmesi** sürükleyin.

1. Renk düğmesine tıklayın. **Açıklamalı** alt yazı `Color` , **kimlik** - `ID_PEN_COLOR` , **basit görünüm** `True` , **büyük görüntü dizini** `1` ' ni ve **bölme modunu** değiştirin `False` .

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Yeni renk düğmesi **kalem** panelinde görüntülenmelidir. Ancak, henüz bir olay işleyicisi olmadığından kullanılamaz. Sonraki adımlarda, renk düğmesi için bir olay işleyicisinin nasıl ekleneceği gösterilmektedir.

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a> Belge sınıfına bir renk üyesi ekleme

Orijinal karalama uygulamasının renk kalemleri olmadığından, bunlar için bir uygulama yazmanız gerekir. Belgenin kalem rengini depolamak için belge sınıfına yeni bir üye ekleyin `CscribbleDoc` .

### <a name="to-add-a-color-member-to-the-document-class"></a>Belge sınıfına bir renk üyesi eklemek için

1. Bubdoc. h içinde, `CScribbleDoc` sınıfında `// Attributes` bölümünü bulun. Veri üyesinin tanımından sonra aşağıdaki kod satırlarını ekleyin `m_nThickWidth` .

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. Her belge, kullanıcının zaten çizmiş olduğu bir Stokes listesi içerir. Her vuruş bir nesne tarafından tanımlanır `CStroke` . `CStroke`Sınıfı kalem rengi hakkında bilgi içermez, bu nedenle sınıfı değiştirmelisiniz. Bu. h ' de, `CStroke` sınıfında, veri üyesinin tanımından sonra aşağıdaki kod satırlarını ekleyin `m_nPenWidth` .

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. Karalama. h içinde, `CStroke` parametreleri genişlik ve renk belirten yeni bir Oluşturucu ekleyin. Deyimden sonra aşağıdaki kod satırını ekleyin `CStroke(UINT nPenWidth);` .

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. Bu, yeni oluşturucunun uygulamasını ekleyin `CStroke` . Oluşturucunun uygulamasından sonra aşağıdaki kodu ekleyin `CStroke::CStroke(UINT nPenWidth)` .

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. Metodun ikinci satırını `CStroke::DrawStroke` aşağıdaki şekilde değiştirin.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. Belge sınıfı için varsayılan kalem rengini ayarlayın. Bu. cpp ' de, ' den sonra aşağıdaki satırları öğesine ekleyin `CScribbleDoc::InitDocument` `m_nThickWidth = 5;` .

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. Abone. cpp içinde, yöntemin ilk satırını `CScribbleDoc::NewStroke` aşağıdaki şekilde değiştirin.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. Metodun son satırını `CScribbleDoc::ReplacePen` aşağıdaki şekilde değiştirin.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. `m_penColor`Üyeyi önceki bir adımda eklediniz. Şimdi, üyeyi ayarlayan renk düğmesi için bir olay işleyicisi oluşturun.

   1. **Kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağını açın.

   1. **Renk** menü öğesine sağ tıklayın ve **olay işleyicisi Ekle**' ye tıklayın. **Olay Işleyicisi Sihirbazı** görüntülenir.

   1. Sihirbazdaki **sınıf listesi** kutusunda **Ckaralama bblidoc** öğesini seçin ve sonra **Ekle ve Düzenle** düğmesine tıklayın. Komut, `CScribbleDoc::OnPenColor` olay işleyicisi saplaması oluşturur.

1. `CScribbleDoc::OnPenColor`Olay işleyicisinin saplamasını aşağıdaki kodla değiştirin.

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

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Artık renk düğmesine basabilir ve kalemin rengini değiştirebilirsiniz.

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a> Kalemleri başlatma ve tercihleri kaydetme

Sonra, kalemlerin rengini ve genişliğini başlatın. Son olarak, bir dosyadan renk çizimi kaydedin ve yükleyin.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Şerit çubuğundaki denetimleri başlatmak için

1. Şerit çubuğundaki kalemleri başlatın.

   Aşağıdaki kodu, yöntemi içinde,, ' den sonra, ' a ekleyin `CScribbleDoc::InitDocument` `m_sizeDoc = CSize(200,200)` .

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

1. Bir renk çizimini bir dosyaya kaydedin. Aşağıdaki ifadeyi, yönteminin öğesinden sonra, yöntemi içinde,,. cpp öğesine ekleyin `CStroke::Serialize` `ar << (WORD)m_nPenWidth;` .

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. Son olarak, bir dosyadan renk çizimi yükleyin. Aşağıdaki kod satırını, `CStroke::Serialize` deyimden sonra yöntemine ekleyin `m_nPenWidth = w;` .

   ```cpp
   ar >> m_penColor;
   ```

1. Şimdi renkli olarak yeniden Karalama yapın ve Çiziminizi bir dosyaya kaydedin.

## <a name="conclusion"></a>Sonuç

MFC karalama uygulamasını güncelleştirdiniz. Mevcut uygulamalarınızı değiştirirken bu yönergeyi kılavuz olarak kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC karalama uygulamasını güncelleştirme (Bölüm 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
