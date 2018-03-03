---
title: "İzlenecek yol: MFC karalama uygulamasını (Bölüm 2) güncelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 861e0b1f76fcd441ccf5da8f56d5c5dcb23a2b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)
[Bölüm 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) klasik bir Office Fluent Şerit ekleme gösterdi bu kılavuzun uygulama karalama. Bu bölümü Şerit paneller ve kullanıcıların menüleri ve komutları yerine kullanabileceğiniz denetimleri nasıl ekleneceğini gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 [Visual C++ Örnekleri](../visual-cpp-samples.md)  
  
##  <a name="top"></a>Bölümler  
 Kılavuzun bu bölümü aşağıdaki bölümleri içerir:  
  
- [Şerit'e yeni paneller ekleme](#addnewpanel)  
  
- [Yardım Masası için Şerit ekleme](#addhelppanel)  
  
- [Şerit'e bir kalem Panel ekleme](#addpenpanel)  
  
- [Şerit'e bir renk düğmesi ekleme](#addcolorbutton)  
  
- [Belge sınıfına renk üye ekleme](#addcolormember)  
  
- [Kalemler başlatma ve tercihleri kaydetme](#initpensave)  
  
##  <a name="addnewpanel"></a>Şerit'e yeni paneller ekleme  
 Bu adımlar nasıl ekleneceğini gösterir bir **Görünüm** araç çubuğu ve durum çubuğunun görünürlüğünü kontrol iki onay kutuları içeren paneli ve ayrıca bir **penceresi** dikey yönelimli bölme içeren paneli oluşturma ve düzenleme birden çok belge arabirimi (MDI) Windows denetimleri düğmesi.  
  
#### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Bir görünüm paneliyle ve pencere Şerit çubuğuna eklemek için  
  
1.  Adlı bir bölme oluşturmak `View`, araç çubuğu ve durum çubuğunu Değiştir iki onay kutularını sahiptir.  
  
    1.  Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. İki sürükleyin **onay kutularını** paneline.  
  
    2.  Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `View`.  
  
    3.  Özelliklerini değiştirmek için onay kutusuna tıklayın. Değişiklik **kimliği** için `ID_VIEW_TOOLBAR` ve **resim yazısı** için `Toolbar`.  
  
    4.  Özelliklerini değiştirmek için ikinci onay kutusuna tıklayın. Değişiklik **kimliği** için `ID_VIEW_STATUS_BAR` ve **resim yazısı** için `Status Bar`.  
  
2.  Adlı bir bölme oluşturmak `Window` Bölünmüş düğme vardır. Bir kullanıcı bölme düğmesine tıkladığında, bir kısayol menüsü karalama uygulamada önceden tanımlanmış üç komutları görüntüler.  
  
    1.  Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. Ardından sürükleyin bir **düğmesini** paneline.  
  
    2.  Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `Window`.  
  
    3.  Düğmesini tıklatın. Değişiklik **resim yazısı** için `Windows`, **anahtarları** için `w`, **büyük görüntü dizini** için `1`, ve **ayırma modu** için `False`. Üç nokta düğmesine (**...** ) yanındaki **menü öğeleri** açmak için **öğeleri Düzenleyicisi** iletişim kutusu.  
  
    4.  Tıklatın **Ekle** üç düğme eklemek için üç kez.  
  
    5.  İlk düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `New Window`, ve **kimliği** için `ID_WINDOW_NEW`.  
  
    6.  İkinci düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `Cascade`, ve **kimliği** için `ID_WINDOW_CASCADE`.  
  
    7.  Üçüncü düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `Tile`, ve **kimliği** için `ID_WINDOW_TILE_HORZ`.  
  
3.  Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. **Görünüm** ve **penceresi** paneller görüntülenmesi. Düğmeleri düzgün şekilde çalıştıklarının onaylamak için tıklatın.  
  
 [[Bölümleri](#top)]  
  
##  <a name="addhelppanel"></a>Yardım Masası için Şerit ekleme  
 Şimdi, karalama uygulamasını adlandırıldığı Şerit düğmeleri için tanımlanan iki menü öğeleri atayabilirsiniz **Yardım konuları** ve **hakkında karalama**. Düğmeleri adlı yeni bir paneline eklenen **yardımcı**.  
  
#### <a name="to-add-a-help-panel"></a>Yardım Masası eklemek için  
  
1.  Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. İki sürükleyin **düğmeleri** paneline.  
  
2.  Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `Help`.  
  
3.  İlk düğmesini tıklatın. Değişiklik **resim yazısı** için `Help Topics`, ve **kimliği** için `ID_HELP_FINDER`.  
  
4.  İkinci düğmesini tıklatın. Değişiklik **resim yazısı** için `About Scribble...`, ve **kimliği** için `ID_APP_ABOUT`.  
  
5.  Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. A **yardımcı** iki Şerit düğmeleri içeren paneli görüntülenmesi.  
  
    > [!IMPORTANT]
    >  Tıkladığınızda **Yardım konuları** düğmesi, karalama uygulamasını açar adlı bir sıkıştırılmış (.chm) HTML Yardım dosyası *your_project_name*. chm. Projenizi karalama adlandırılmamışsa sonuç olarak, size yardım dosyasını proje adınızı yeniden adlandırmanız gerekir.  
  
 [[Bölümleri](#top)]  
  
##  <a name="addpenpanel"></a>Şerit'e bir kalem Panel ekleme  
 Şimdi, kalınlığı ve kalemin rengini kontrol düğmeleri görüntülemek için bir panel ekleyin. Bu panoyu kalın ve ince kalemler arasında geçiş yapar bir onay kutusu içerir. İşlevselliği, benzer **Kalın çizgi** karalama uygulamasını menü öğesi.  
  
 Özgün karalama uygulamasını kullanıcının kullanıcı tıkladığında, görünen bir iletişim kutusundan kalem genişliği seçmesine olanak tanır **kalem genişliği** menüsünde. Şerit çubuğu yeni denetimler için yeterli yeri olduğundan, Şeritteki iki birleşik giriş kutuları kullanarak iletişim kutusunda değiştirebilirsiniz. Tek bir birleşik giriş kutusu ince kalem genişliği ayarlar ve diğer birleşik giriş kutusu kalın kalem genişliğini ayarlar.  
  
#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Şerit kalem paneli ve birleşik giriş kutuları eklemek için  
  
1.  Gelen **araç**, sürükleyin bir **Masası** için **giriş** kategorisi. Ardından sürükleyin bir **onay kutusunu** ve iki **birleşik giriş kutuları** paneline.  
  
2.  Özelliklerini değiştirmek için Denetim Masası'ı tıklatın. Değişiklik **resim yazısı** için `Pen`.  
  
3.  Onay kutusuna tıklayın. Değişiklik **resim yazısı** için `Use Thick`, ve **kimliği** için `ID_PEN_THICK_OR_THIN`.  
  
4.  İlk açılan kutu'ı tıklatın. Değişiklik **resim yazısı** için `Thin Pen`, **kimliği** için `ID_PEN_THIN_WIDTH`, **metin** için `2`, **türü** için `Drop List`, ve **veri** için `1;2;3;4;5;6;7;8;9;`.  
  
5.  İkinci birleşik giriş kutusu'ı tıklatın. Değişiklik **resim yazısı** için `Thick Pen`, **kimliği** için `ID_PEN_THICK_WIDTH`, **metin** için `5`, **türü** için `Drop List`, ve **veri** için `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`.  
  
6.  Yeni birleşik giriş kutuları varolan tüm menü öğelerini karşılık gelmemelidir. Bu nedenle, her kalem seçeneği için bir menü öğesi oluşturmanız gerekir.  
  
    1.  İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.  
  
    2.  Tıklatın **kalem** p açmak için**tr** menüsü. Ardından **burada türü** ve türü `Thi&n Pen`.  
  
    3.  Açmak için yazdığınız metni sağ **özellikleri** penceresi ve değişiklik kimliği özelliğini `ID_PEN_THIN_WIDTH`.  
  
    4.  Ayrıca her kalem menü öğesi için bir olay işleyicisi oluşturmanız gerekir. Sağ **düzeltmeyi & n kalem** yeni oluşturduğunuz ve ardından menü öğesi **olay işleyicisi ekleme**. **Olay işleyici Sihirbazı** görüntülenir.  
  
    5.  İçinde **sınıf listesi** Sihirbazı, select kutusunda **CScribbleDoc** ve ardından **ekleme ve düzenleme**. Bu adlı bir olay işleyicisi oluşturur `CScribbleDoc::OnPenThinWidth`.  
  
    6.  Aşağıdaki kodu ekleyin `CScribbleDoc::OnPenThinWidth`.  
  
 ``` *Şerit'e bir işaretçi alma çubuk CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) -> GetRibbonBar(); ASSERT_VALID(pRibbon); */ / İnce genişliği birleşik giriş kutusu CMFCRibbonComboBox bir işaretçi alma* pThinComboBox dynamıc_downcast = (CMFCRibbonComboBox, pRibbon FindByID(ID_PEN_THIN_WIDTH)); -> * //Get seçilen değeri  
    int nCurSel = pThinComboBox -> GetCurSel(); varsa (nCurSel > = 0)  
{  
m_nThinWidth atoi = (pThinComboBox -> GetItem(nCurSel));

 } * / / Seçili genişliği kullanarak yeni bir kalem oluşturma  
    ReplacePen();

 ```  
  
7.  Next, create a menu item and event handlers for the thick pen.  
  
    1.  In the **Resource View** window, open the IDR_SCRIBBTYPE menu resource.  
  
    2.  Click **Pen** to open the pen menu. Then click **Type Here** and type `Thic&k Pen`.  
  
    3.  Right-click the text that you just typed to display the **Properties** window. Change the ID property to `ID_PEN_THICK_WIDTH`.  
  
    4.  Right-click the **Thick Pen** menu item that you just created and then click **Add Event Handler**. The **Event Handler Wizard** is displayed.  
  
    5.  In the **Class list** box of the wizard, select **CScribbleDoc** and then click **Add and Edit**. This creates an event handler named `CScribbleDoc::OnPenThickWidth`.  
  
    6.  Add the following code to `CScribbleDoc::OnPenThickWidth`.  
  
 ``` *// Get a pointer to the ribbon bar  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
    CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
*// Get the selected value  
    int nCurSel = pThickComboBox->GetCurSel();
if (nCurSel>= 0)  
 {  
    m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));

 } *// Create a new pen using the selected width  
    ReplacePen();

 ```  
  
8.  Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Yeni düğmeler ve birleşik giriş kutuları görüntülenmesi gerekir. Farklı kalem genişliği karalama kullanmayı deneyin.  
  
 [[Bölümleri](#top)]  
  
##  <a name="addcolorbutton"></a>Kalem paneline renk düğme ekleme  
 Ardından, eklemek bir [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) kullanıcı sağlayan nesne karalama renkte.  
  
#### <a name="to-add-a-color-button-to-the-pen-panel"></a>Bir renk düğmesi kalem paneline eklemek için  
  
1.  Renk düğmesi eklemeden önce menü öğesi için oluşturun. İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın. Tıklatın **kalem** kalem menüsünü açmak için menü öğesi. Ardından **burada türü** ve türü `&Color`. Görüntülenecek yazdığınız metni sağ **özellikleri** penceresi. Değişiklik kimliği `ID_PEN_COLOR`.  
  
2.  Renk düğmesi. Şimdi ekleyin. Gelen **araç**, sürükleyin bir **renk düğmesi** için **kalem** paneli.  
  
3.  Renk düğmesini tıklatın. Değişiklik **resim yazısı** için `Color`, **kimliği** için `ID_PEN_COLOR`, **SimpleLook** için `True`, **büyük görüntü dizini** için `1`, ve **ayırma modu** için `False`.  
  
4.  Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Yeni renk düğmesi görüntülenmesi gerekip **kalem** paneli. Ancak, bir olay işleyicisi henüz olmadığı için kullanılamaz. Sonraki adımlar için renk düğmesi olay işleyicisi ekleme gösterir.  
  
 [[Bölümleri](#top)]  
  
##  <a name="addcolormember"></a>Belge sınıfına renk üye ekleme  
 Özgün karalama uygulamasını renkli kalemler sahip olmadığından, onlar için bir uygulama yazmanız gerekir. Belge kalem rengini depolamak için yeni bir üye belge sınıfına ekleyin,`CscribbleDoc.`  
  
#### <a name="to-add-a-color-member-to-the-document-class"></a>Belge sınıfına renk üye eklemek için  
  
1.  Scribdoc.h içinde içinde `CScribbleDoc` sınıfı, Bul `// Attributes` bölümü. Aşağıdaki kod satırlarını sonra tanımını ekleyin `m_nThickWidth` veri üyesi.  
  
 ''' * / / Geçerli kalem rengi  
    COLORREF m_penColor;  
 ```  
  
2.  Every document contains a list of stokes that the user has already drawn. Every stroke is defined by a `CStroke` object. The `CStroke` class does not include information about pen color. Therefore, you must modify the class. In scribdoc.h, in the `CStroke` class, add the following lines of code after the definition of the `m_nPenWidth` data member.  
  
 ``` *// Pen color for the stroke  
    COLORREF m_penColor;  
 ```  
  
3.  Scribdoc.h içinde yeni bir ekleme `CStroke` Oluşturucusu bir genişlik ve renk parametreleri belirtin. Koddan sonra aşağıdaki satırı ekleyin `CStroke(UINT nPenWidth);` deyimi.  
  
 ```  
    CStroke(UINT nPenWidth, COLORREF penColor);

 ```  
  
4.  Yeni uygulama scribdoc.cpp içinde eklemek `CStroke` Oluşturucusu. Uygulamasının sonra aşağıdaki kodu ekleyin `CStroke::CStroke(UINT nPenWidth)` Oluşturucusu.  
  
 ''' * / / Belge kullandığı Oluşturucusu geçerli genişlik ve rengi  
    CStroke::CStroke (UINT nPenWidth, COLORREF GraphicsWindow)  
 {  
    m_nPenWidth nPenWidth; =  
    m_penColor GraphicsWindow; =  
    m_rectBounding.SetRectEmpty();

 }  
 ```  
  
5.  Change the second line of the `CStroke::DrawStroke` method as follows.  
  
 ```  
    varsa (! penStroke.CreatePen (PS_SOLID, m_nPenWidth, m_penColor))  
 ```  
  
6.  Set the default pen color for the document class. In scribdoc.cpp, add the following lines to `CScribbleDoc::InitDocument`, after the `m_nThickWidth = 5;` statement.  
  
 ``` *// default pen color is black  
    m_penColor = RGB(0,
    0,
    0);

 ```  
  
7.  İlk satırı scribdoc.cpp içinde değiştirmek `CScribbleDoc::NewStroke` şu yöntemi.  
  
 ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);

 ```  
  
8.  Son satırının değiştirmek `CScribbleDoc::ReplacePen` şu yöntemi.  
  
 ```  
    m_penCur.CreatePen(PS_SOLID,
    m_nPenWidth,
    m_penColor);

 ```  
  
9. Eklediğiniz `m_penColor` bir önceki adımda üye. Şimdi, üye ayarlar renk düğmesi olay işleyicisi oluşturun.  
  
    1.  İçinde **kaynak görünümü** penceresinde IDR_SCRIBBTYPE menü kaynağı açın.  
  
    2.  Sağ **renk** menü öğesi ve tıklatın **olay işleyicisi ekleme**. **Olay işleyici Sihirbazı** görüntülenir.  
  
    3.  İçinde **sınıf listesi** Sihirbazı, select kutusunda **CScribbleDoc** ve ardından **ekleme ve düzenleme** düğmesi. Bu oluşturur `CScribbleDoc::OnPenColor` olay işleyicisi saplama.  
  
10. Saplama için değiştirme `CScribbleDoc::OnPenColor` aşağıdaki kod ile olay işleyicisi.  
  
 ```  
    void CScribbleDoc::OnPenColor()  
 { *// Change pen color to reflect color button's current selection  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
    CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

    m_penColor = pColorBtn->GetColor();
*// Create new pen using the selected color  
    ReplacePen();

 }  
 ```  
  
11. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Renk düğmesine basın ve Kalem rengi değiştirin yapabiliyor olmanız gerekir.  
  
 [[Bölümleri](#top)]  
  
##  <a name="initpensave"></a>Kalemler başlatma ve tercihleri kaydetme  
 Ardından, rengini ve genişliğini kalemler başlatır. Son olarak, kaydedin ve bir dosyadan çizim renk yükleyin.  
  
#### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Şerit çubuğundaki denetimlerinin başlatmak için  
  
1.  Şerit çubuğunda kalemler başlatır.  
  
     Scribdoc.cpp için aşağıdaki kodu ekleyin `CScribbleDoc::InitDocument` yöntemi, sonra `m_sizeDoc = CSize(200,200)` deyimi.  
  
 ```*/ / Şerit UI'si, ilk değerlerinin CMFCRibbonBar sıfırlama* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) -> GetRibbonBar(); ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton * pColorBtn dynamıc_downcast = (CMFCRibbonColorButton, pRibbon -> FindByID(ID_PEN_COLOR)); * / / Set ColorButton siyah  
    pColorBtn -> SetColor (RGB (0, 0, 0));

 CMFCRibbonComboBox * pThinComboBox dynamıc_downcast = (CMFCRibbonComboBox, pRibbon -> FindByID(ID_PEN_THIN_WIDTH)); * / / Set ince kalem combobox 2  
    pThinComboBox SelectItem(1) ->;

 CMFCRibbonComboBox * pThickComboBox dynamıc_downcast = (CMFCRibbonComboBox, pRibbon -> FindByID(ID_PEN_THICK_WIDTH)); * / / Set kalın kalem combobox 5  
    pThickComboBox SelectItem(0) ->;

 ```  
  
2.  Save a color drawing to a file. Add the following statement to scribdoc.cpp, in the `CStroke::Serialize` method, after the `ar << (WORD)m_nPenWidth;` statement.  
  
 ```  
    ar << (COLORREF) m_penColor;  
 ```  
  
3.  Finally, load a color drawing from a file. Add the following line of code, in the `CStroke::Serialize` method, after the `m_nPenWidth = w;` statement.  
  
 ```  
    ar >> m_penColor;  
 ```  
  
4.  Now scribble in color and save your drawing to a file.  
  
 [[Sections](#top)]  
  
## Conclusion  
 You have updated the MFC Scribble application. Use this walkthrough as a guide when you modify your existing applications.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)   
 [Walkthrough: Updating the MFC Scribble Application (Part 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)

