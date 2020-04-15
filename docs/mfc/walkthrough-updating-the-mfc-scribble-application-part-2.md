---
title: 'İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: bc204a152168accf3731eede8ca9ef960ab121d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360224"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)

Bu izbin [bölüm 1'i,](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) klasik Karalama uygulamasına Office Fluent Ribbon'un nasıl ekleyeceğini gösterdi. Bu bölümde, menüler ve komutlar yerine kullanıcıların kullanabileceği şerit panelleri ve denetimleri nasıl ekleyeceğiniz gösterilmektedir.

## <a name="prerequisites"></a>Ön koşullar

[Visual C++ Örnekleri](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a>Bölüm

Bu bölümün bu bölümü aşağıdaki bölümlere sahiptir:

- [Şerite Yeni Paneller Ekleme](#addnewpanel)

- [Şerite Yardım Paneli Ekleme](#addhelppanel)

- [Şerite Kalem Paneli Ekleme](#addpenpanel)

- [Şerite Renk Düğmesi Ekleme](#addcolorbutton)

- [Belge Sınıfına Renkli Üye Ekleme](#addcolormember)

- [Kalemleri Başlatma ve Tercihleri Kaydetme](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a>Şerite Yeni Paneller Ekleme

Bu adımlar, araç çubuğunun ve durum çubuğunun görünürlüğünü kontrol eden iki onay kutusu içeren bir **Görünüm** paneli nin ve ayrıca birden çok belge arabirimi (MDI) penceresinin oluşturulmasını ve düzenlenmesini kontrol eden dikey olarak yönlendirilmiş bölünmüş düğme içeren bir **Pencere** panelini gösterir.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Şerit çubuğuna Görünüm paneli ve Pencere paneli eklemek için

1. Durum çubuğunu `View`ve araç çubuğunu değiştiren iki onay kutusu olan , adlı bir panel oluşturun.

   1. Araç **Kutusundan,** Bir **Paneli** **Ana Sayfa** kategorisine sürükleyin. Ardından iki **Onay Kutusu'nu** panele sürükleyin.

   1. Özelliklerini değiştirmek için paneli tıklatın. **Resim Yazısını** ' ile `View`değiştir

   1. Özelliklerini değiştirmek için ilk onay kutusunu tıklatın. **Kimliği** `ID_VIEW_TOOLBAR` ve **Resim Yazısını** ' olarak `Toolbar`değiştirin

   1. Özelliklerini değiştirmek için ikinci onay kutusunu tıklatın. **Kimliği** `ID_VIEW_STATUS_BAR` ve **Resim Yazısını** ' olarak `Status Bar`değiştirin

1. Bölünmüş düğmesi `Window` olan adlandırılmış bir panel oluşturun. Bir kullanıcı bölme düğmesini tıklattığında, kısayol menüsü Karalama uygulamasında zaten tanımlanmış üç komut görüntüler.

   1. Araç **Kutusundan,** Bir **Paneli** **Ana Sayfa** kategorisine sürükleyin. Ardından bir **Düğmeyi** panele sürükleyin.

   1. Özelliklerini değiştirmek için paneli tıklatın. **Resim Yazısını** ' ile `Window`değiştir

   1. Düğmeyi tıklatın. Resim Yazı `Windows`Resim **Yazısını** , `1` **Anahtarlar** `w`için, `False`Büyük Görüntü **Dizini'ni** ve Split Mode **'u** ' ya değiştirin. Ardından **Öğeler Düzenleyicisi** iletişim kutusunu açmak için **Menü Öğeleri'nin** yanındaki elipsis (**...**) öğesini tıklatın.

   1. Üç düğme eklemek için üç kez **Ekle'yi** tıklatın.

   1. İlk düğmeyi tıklatın ve `New Window`ardından Resim `ID_WINDOW_NEW` **Yazısı'nı** ve **kimliği** ' olarak değiştirin.

   1. İkinci düğmeyi tıklatın ve `Cascade`ardından Resim `ID_WINDOW_CASCADE` **Yazısı'nı** ve **kimliği** ' olarak değiştirin.

   1. Üçüncü düğmeyi tıklatın ve `Tile`ardından Resim `ID_WINDOW_TILE_HORZ` **Yazısı'nı** ve **kimliği** ' olarak değiştirin.

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. **Görünüm** ve **Pencere** panelleri görüntülenmelidir. Doğru çalıştığını doğrulamak için düğmeleri tıklatın.

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a>Şerite Yardım Paneli Ekleme

Şimdi, Karalama uygulamasında tanımlanan iki menü öğesini **Yardım Konuları** ve **Karalama Hakkında**adlı şerit düğmelerine atayabilirsiniz. Düğmeler **Yardım**adlı yeni bir panele eklenir.

### <a name="to-add-a-help-panel"></a>Yardım paneli eklemek için

1. Araç **Kutusundan,** Bir **Paneli** **Ana Sayfa** kategorisine sürükleyin. Ardından panele iki **Düğme** sürükleyin.

1. Özelliklerini değiştirmek için paneli tıklatın. **Resim Yazısını** ' ile `Help`değiştir

1. İlk düğmeyi tıklatın. **Resim Yazısını** `Help Topics`ve `ID_HELP_FINDER` **Kimliğini** ' olarak değiştirin

1. İkinci düğmeyi tıklatın. **Resim Yazısını** `About Scribble...`ve `ID_APP_ABOUT` **Kimliğini** ' olarak değiştirin

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. İki şerit düğmesi içeren bir **Yardım** paneli görüntülenmelidir.

   > [!IMPORTANT]
   > **Yardım Konuları** düğmesini tıklattığınızda, Karalama uygulaması sıkıştırılmış bir HTML (.chm) yardım *dosyasını*your_project_name.chm olarak açar. Sonuç olarak, projenizin adı Karalama değilse, yardım dosyasını proje adınıza yeniden adlandırmanız gerekir.

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a>Şerite Kalem Paneli Ekleme

Şimdi, kalemin kalınlığını ve rengini kontrol eden düğmeleri görüntülemek için bir panel ekleyin. Bu panel, kalın ve ince kalemler arasında geçiş yapan bir onay kutusu içerir. İşlevselliği, Karalama uygulamasındaki **Kalın Satır** menü öğesine benzer.

Özgün Karalama uygulaması, kullanıcı nın menüde **Kalem Genişlikleri'ni** tıklattığında görünen bir iletişim kutusundan kalem genişliklerini seçmesine olanak tanır. Şerit çubuğunda yeni denetimler için yeterli alan olduğundan, şeritteki iki açılan kutuyu kullanarak iletişim kutusunu değiştirebilirsiniz. Bir açılan kutu ince kalemin genişliğini, diğer açılan kutu ise kalın kalemin genişliğini ayarlar.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Şerite Kalem paneli ve açılan kutular eklemek için

1. Araç **Kutusundan,** Bir **Paneli** **Ana Sayfa** kategorisine sürükleyin. Ardından bir **Onay Kutusu** ve iki Açılan **Kutu'yu** panele sürükleyin.

1. Özelliklerini değiştirmek için paneli tıklatın. **Resim Yazısını** ' ile `Pen`değiştir

1. Onay kutusunu tıklatın. **Resim Yazısını** `Use Thick`ve `ID_PEN_THICK_OR_THIN` **Kimliğini** ' olarak değiştirin

1. İlk açılan kutuyu tıklatın. Resim Yazı `Thin Pen`resim **yazısını** `Drop List`, **ID'ye,** `ID_PEN_THIN_WIDTH` `2` **Yazın,** **Veri'ye** `1;2;3;4;5;6;7;8;9;`ve **Metin'e** ' olarak değiştirin.

1. İkinci açılan kutuyu tıklatın. Resim Yazı `Thick Pen`resim **yazısını** `Drop List`, **ID'ye,** `ID_PEN_THICK_WIDTH` `5` **Yazın,** **Veri'ye** `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`ve **Metin'e** ' olarak değiştirin.

1. Yeni açılan kutular varolan menü öğelerine karşılık gelmez, bu nedenle her kalem seçeneği için bir menü öğesi oluşturmanız gerekir.

   1. Kaynak **Görünümü** penceresinde, **IDR_SCRIBBTYPE** menü kaynağını açın.

   1. Kalem menüsünü açmak için **Kalem'i** tıklatın. Ardından **Buraya Yazın'ı** tıklatın ve yazın. `Thi&n Pen`

   1. **Özellikler** penceresini açmak için yazdığınız metni sağ tıklatın ve ardından `ID_PEN_THIN_WIDTH`kimlik özelliğini '' olarak değiştirin

   1. Her kalem menü öğesi için bir olay işleyicisi oluşturun. Oluşturduğunuz **Thi&n Pen** menü öğesini sağ tıklatın ve ardından **Olay İşleyicisi Ekle'yi**tıklatın. **Olay Işleyicisihirbazı** görüntülenir.

   1. Sihirbazdaki **Sınıf listesi** kutusunda **CScribbleDoc'u** seçin ve ardından **Ekle ve Edit'i**tıklatın. Komut, adlı `CScribbleDoc::OnPenThinWidth`bir olay işleyicisi oluşturur.

   1. Aşağıdaki kodu `CScribbleDoc::OnPenThinWidth` içine ekleyin.

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

   1. Kaynak **Görünümü** penceresinde, **IDR_SCRIBBTYPE** menü kaynağını açın.

   1. Kalem menüsünü açmak için **Kalem'i** tıklatın. Ardından **Buraya Yazın'ı** tıklatın ve yazın. `Thic&k Pen`

   1. **Özellikler** penceresini görüntülemek için yazdığınız metni sağ tıklatın. Kimlik özelliğini `ID_PEN_THICK_WIDTH`' ' olarak değiştirin

   1. Oluşturduğunuz **Kalın Kalem** menü öğesini sağ tıklatın ve ardından **Olay İşleyicisi Ekle'yi**tıklatın. **Olay Işleyicisihirbazı** görüntülenir.

   1. Sihirbazın **Sınıf listesi** kutusunda **CScribbleDoc'u** seçin ve ardından **Ekle ve Edit'i**tıklatın. Komut, adlı `CScribbleDoc::OnPenThickWidth`bir olay işleyicisi oluşturur.

   1. Aşağıdaki kodu `CScribbleDoc::OnPenThickWidth` içine ekleyin.

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

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. Yeni düğmeler ve açılan kutular görüntülenmelidir. Karalamak için farklı kalem genişlikleri kullanmayı deneyin.

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a>Kalem Paneline Renk Düğmesi Ekleme

Ardından, kullanıcının renkli karalamasına izin veren bir [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) nesnesi ekleyin.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Kalem paneline renk düğmesi eklemek için

1. Renk düğmesini eklemeden önce, bunun için bir menü öğesi oluşturun. Kaynak **Görünümü** penceresinde, **IDR_SCRIBBTYPE** menü kaynağını açın. Kalem menüsünü açmak için **Kalem** menüsü öğesini tıklatın. Ardından **Buraya Yazın'ı** tıklatın ve yazın. `&Color` **Özellikler** penceresini görüntülemek için yazdığınız metni sağ tıklatın. Kimliği ' `ID_PEN_COLOR`yi ' olarak değiştirin

1. Şimdi renk düğmesini ekleyin. Araç **Kutusundan,** **Renk Düğmesini** **Kalem** paneline sürükleyin.

1. Renk düğmesini tıklatın. Resim Yazı `Color`Resim **Yazısını** , **ID** `ID_PEN_COLOR`için `1`, Simple **Look** to `True`, Büyük Görüntü **Dizini** için ve Split **Mode** için `False`değiştirin.

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. Yeni renk düğmesi **Kalem** panelinde görüntülenmelidir. Ancak, henüz bir olay işleyicisi olmadığından kullanılamaz. Sonraki adımlar, renk düğmesi için bir olay işleyicisi eklemek için nasıl gösterir.

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a>Belge Sınıfına Renkli Üye Ekleme

Özgün Karalama uygulamasında renkli kalemler olmadığından, bunlar için bir uygulama yazmanız gerekir. Belgenin kalem rengini depolamak için belge sınıfına yeni `CscribbleDoc`bir üye ekleyin.

### <a name="to-add-a-color-member-to-the-document-class"></a>Belge sınıfına renk üyesi eklemek için

1. Scribdoc.h olarak, `CScribbleDoc` sınıfta, `// Attributes` bölümü bulun. `m_nThickWidth` Veri üyesinin tanımından sonra aşağıdaki kod satırlarını ekleyin.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. Her belge, kullanıcının zaten çizdiği bir stokes listesi içerir. Her kontur bir `CStroke` nesne tarafından tanımlanır. Sınıf `CStroke` kalem rengi yle ilgili bilgiler içermez, bu nedenle sınıfı değiştirmeniz gerekir. Scribdoc.h'de, `CStroke` sınıfta, `m_nPenWidth` veri üyesinin tanımından sonra aşağıdaki kod satırlarını ekleyin.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. Scribdoc.h olarak, parametreleri bir genişlik ve renk belirten yeni `CStroke` bir yapıcı ekleyin. İfadeden sonra aşağıdaki kod `CStroke(UINT nPenWidth);` satırını ekleyin.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. Scribdoc.cpp olarak, yeni `CStroke` yapıcı nın uygulanmasını ekleyin. `CStroke::CStroke(UINT nPenWidth)` Oluşturucunun uygulanmasından sonra aşağıdaki kodu ekleyin.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. Yöntemin ikinci satırını aşağıdaki gibi değiştirin. `CStroke::DrawStroke`

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. Belge sınıfı için varsayılan kalem rengini ayarlayın. Scribdoc.cpp olarak, aşağıdaki satırları `CScribbleDoc::InitDocument`ekleyin `m_nThickWidth = 5;` , ifadeden sonra.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. Scribdoc.cpp olarak, aşağıdaki yöntemin `CScribbleDoc::NewStroke` ilk satırı değiştirin.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. Yöntemin son satırını `CScribbleDoc::ReplacePen` aşağıdakiyle değiştirin.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. Üyeyi `m_penColor` önceki bir adıma eklediniz. Şimdi, üyeyi ayarlayan renk düğmesi için bir olay işleyicisi oluşturun.

   1. Kaynak **Görünümü** penceresinde, IDR_SCRIBBTYPE menü kaynağını açın.

   1. **Renk** menüsü öğesini sağ tıklatın ve **Olay İşleyicisi Ekle'yi**tıklatın. **Olay Işleyicisihirbazı** görüntülenir.

   1. Sihirbazdaki **Sınıf listesi** kutusunda **CScribbleDoc'u** seçin ve ardından Ekle ve **Edit** düğmesini tıklatın. Komut `CScribbleDoc::OnPenColor` olay işleyicisi saplaması oluşturur.

1. Olay işleyicisi `CScribbleDoc::OnPenColor` için saplamayı aşağıdaki kodla değiştirin.

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

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. Artık renk düğmesine basabilir ve kalemin rengini değiştirebilirsiniz.

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a>Kalemleri Başlatma ve Tercihleri Kaydetme

Ardından, kalemlerin rengini ve genişliğini başlangıç olarak algıla. Son olarak, bir dosyadan renkli çizim kaydedin ve yükleyin.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Şerit çubuğundaki denetimleri başlatma

1. Şerit çubuğundaki kalemleri baş harfe doğru açın.

   `m_sizeDoc = CSize(200,200)` Açıklamadan sonra `CScribbleDoc::InitDocument` yöntemde scribdoc.cpp'ye aşağıdaki kodu ekleyin.

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

1. Renkli çizimi dosyaya kaydedin. Açıklamadan sonra yöntemde scribdoc.cpp'ye aşağıdaki `ar << (WORD)m_nPenWidth;` ifadeyi `CStroke::Serialize` ekleyin.

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. Son olarak, bir dosyadan renk çizimi yükleyin. İfadeden sonra `CStroke::Serialize` yönteme aşağıdaki kod satırını `m_nPenWidth = w;` ekleyin.

   ```cpp
   ar >> m_penColor;
   ```

1. Şimdi renkli karalama ve bir dosyaya çizim kaydedin.

## <a name="conclusion"></a>Sonuç

MFC Karalama uygulamasını güncellediniz. Varolan uygulamalarınızı değiştirirken bu izbiyi kılavuz olarak kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (1. Bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
