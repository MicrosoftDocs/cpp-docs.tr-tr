---
title: Dinamik Düzen
ms.date: 09/09/2019
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
ms.openlocfilehash: 1b0d035d3c551fd309d515ccb8b22159218c1b0a
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "70907556"
---
# <a name="dynamic-layout"></a>Dinamik Düzen

Visual Studio 2015 ' de MFC ile kullanıcının yeniden boyutlandırılabilmesini sağlayan iletişim kutuları oluşturabilir ve düzenin boyut değişikliğine ne şekilde ayarlanır. Örneğin, her zaman en altta kalmak için, bir iletişim kutusunun alt kenarına düğme ekleyebilirsiniz. Kullanıcı iletişim kutusunu genişledikçe genişletmek için listkutularý, editkutularý ve metin alanları gibi belirli denetimleri de ayarlayabilirsiniz.

## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>MFC iletişim kutusu için dinamik düzen ayarlarını belirtme

Kullanıcı bir iletişim kutusunu yeniden boyutlandırdığında, iletişim kutusundaki denetimler X ve Y yönlerini yeniden boyutlandırabilir veya taşıyabilir. Kullanıcı bir iletişim kutusunu yeniden boyutlandırdığında bir denetimin boyut veya konum değişikliği dinamik düzen olarak adlandırılır. Örneğin, yeniden boyutlandırılmaz bir iletişim kutusu aşağıda verilmiştir:

![Yeniden boyutlandırmadan önce iletişim kutusu.](../mfc/media/mfcdynamiclayout4.png "Yeniden boyutlandırmadan önce iletişim kutusu.")

Yeniden boyutlandırdıktan sonra, ListBox alanı daha fazla öğe göstermek için artar ve düğmeler sağ alt köşesinden birlikte taşınır:

![Yeniden boyutlandırıldıktan sonra iletişim kutusu.](../mfc/media/mfcdynamiclayout5.png "Yeniden boyutlandırıldıktan sonra iletişim kutusu.")

IDE 'deki kaynak düzenleyicisinde her bir denetimin ayrıntılarını belirterek dinamik düzeni denetleyebilir veya belirli bir denetim için `CMFCDynamicLayout` nesnesine erişerek ve özellikleri ayarlayarak programlama yoluyla bu yapabilirsiniz.

### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>Kaynak düzenleyicisinde dinamik düzen özelliklerini ayarlama

Kaynak düzenleyicisini kullanarak bir kod yazmak zorunda kalmadan bir iletişim kutusu için dinamik düzen davranışını ayarlayabilirsiniz.

#### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>Kaynak düzenleyicisinde dinamik düzen özelliklerini ayarlamak için

1. MFC projesi açıkken, iletişim kutusu düzenleyicisinde birlikte çalışmak istediğiniz iletişim kutusunu açın.

   ![Kaynak düzenleyicisinde iletişim kutusunu açın.](../mfc/media/mfcdynamiclayout3.png "Kaynak düzenleyicisinde iletişim kutusunu açın.")

1. Bir denetim seçin ve **Özellikler** penceresinde ( **sınıf görünümü**), dinamik düzen özelliklerini ayarlayın. **Özellikler** penceresindeki **Dinamik düzen** bölümü, **taşıma türü**, **boyutlandırma türü**ve bu özellikler için seçilen değerlere bağlı olarak, ne kadar denetim taşınacağını tanımlayan belirli özellikler ve boyutu değiştirin. **Taşıma türü** , iletişim kutusunun boyutu değiştirildiğinde bir denetimin nasıl taşındığını belirler; **Boyutlandırma türü** , iletişim kutusunun boyutu değiştirildiğinde bir denetimin nasıl yeniden boyutlandırılacağını belirler. Dinamik olarak değiştirmek istediğiniz boyutlara bağlı olarak tür ve **boyutlandırma türünün** **taşınması** **yatay**, **Dikey**, **her ikisi de**veya **none** olabilir. Yatay X boyutudur; Dikey, Y yönü.

1. Düğme gibi bir denetimin sabit boyutta olmasını istiyorsanız ve sağ altta, **Tamam** veya **iptal** düğmeleri için ortak olduğu gibi, **boyutlandırma türünü** **hiçbiri**olarak ayarlayın ve **taşınan türü** **her ikisine de**ayarlayın. Taşıma **türü**altındaki **X** ve hareketli **Y** değerleri için, denetimin sağ alt köşesinden sabit bir uzaklığı sürmesine neden olacak şekilde %100 ayarlayın.

   ![Dinamik Düzen](../mfc/media/mfcdynamiclayout1.png "Dinamik Düzen")

1. İletişim kutusu genişledikçe genişletmek istediğiniz bir denetim de olduğunu varsayalım. Genellikle, bir Kullanıcı, metin alanının boyutunu artırmak için çok satırlı bir EditBox genişletmek üzere bir iletişim kutusunu genişletebilir veya daha fazla veri görmek için bir liste denetimini genişletebilirler. Bu durumda, **boyutlandırma türünü** her ikisi olarak ayarlayın ve **taşınan türü** yok olarak ayarlayın. Ardından, **boyutlandırma X** ve **boyutlandırma Y** değerlerini 100 olarak ayarlayın.

   ![Dinamik Düzen ayarları](../mfc/media/mfcdynamiclayout2.png "Dinamik Düzen ayarları")

1. Denetimleriniz için anlamlı olabilecek diğer değerlerle denemeler yapın. Tek satırlık bir metin kutusuna sahip bir iletişim kutusu, örneğin **boyutlandırma türü** yalnızca **yatay** olarak ayarlanmış olabilir.

### <a name="setting-dynamic-layout-properties-programmatically"></a>Dinamik düzen özelliklerini programlı olarak ayarlama

Önceki yordam, tasarım zamanında bir iletişim kutusu için dinamik düzen özellikleri belirlemek için faydalıdır, ancak çalışma zamanında dinamik düzeni denetlemek isterseniz, dinamik düzen özelliklerini programlı bir şekilde ayarlayabilirsiniz.

#### <a name="to-set-dynamic-layout-properties-programmatically"></a>Dinamik düzen özelliklerini programlı bir şekilde ayarlamak için

1. İletişim kutusunun dinamik yerleşimini belirtmek istediğiniz iletişim kutusu sınıfınızın uygulama kodunda bir yer bulun veya oluşturun. Örneğin, diyaloğa `AdjustLayout` gibi bir yöntem eklemek ve düzeni değiştirilmesi gereken yerlerden çağırmak isteyebilirsiniz. Önce bunu oluşturucudan veya iletişim kutusunda değişiklik yaptıktan sonra çağırabilirsiniz.

1. İletişim kutusunda, `CWnd` sınıfının bir yöntemi olan [Getdynamiclayout](../mfc/reference/cwnd-class.md#getdynamiclayout)' ı çağırın. `GetDynamicLayout`, bir `CMFCDynamicLayout` nesnesine bir işaretçi döndürür.

    ```cpp
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();
    ```

1. Dinamik davranış eklemek istediğiniz ilk denetim için, denetimin ayarlanması gerektiği şekilde kodlayan [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure) yapısını oluşturmak için dinamik düzen sınıfındaki statik yöntemleri kullanın. Bunu ilk olarak uygun statik yöntemi seçerek yapabilirsiniz: [CMFCDynamicLayout:: Moveyatay](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal), [CMFCDynamicLayout:: MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical), CMFCDynamicLayout:: [MoveNone](../mfc/reference/cmfcdynamiclayout-class.md#movenone)veya [CMFCDynamicLayout:: MoveHorizontalAndVertical ](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical). Taşımanın yatay ve/veya dikey yönleri için bir yüzde değeri geçirin. Bu statik yöntemler, bir denetimin taşıma davranışını belirtmek için kullanabileceğiniz yeni oluşturulan bir MoveSettings nesnesi döndürür.

   100, bir denetimin kenarının yeni kenarlıktan sabit bir mesafe kalmasına neden olacak şekilde, iletişim kutusunun boyutunun tam olarak hareket etmesini sağlar.

    ```cpp
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);
    ```

1. Boyut davranışı için, [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure) türünü kullanan aynı şeyi yapın. Örneğin, iletişim kutusu yeniden boyutlandırdığında bir denetimin boyutu değiştirmediğinden emin olmak için aşağıdaki kodu kullanın:

    ```cpp
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();
    ```

1. [CMFCDynamicLayout:: Addidıtem](../mfc/reference/cmfcdynamiclayout-class.md#additem) metodunu kullanarak denetimi dinamik düzen yöneticisi 'ne ekleyin. İstenen denetimi belirtmenin farklı yolları için iki aşırı yükleme vardır. Biri denetimin pencere tanıtıcısını (HWND) alır ve diğeri denetim KIMLIĞINI alır.

    ```cpp
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);
    ```

1. Taşınması veya yeniden boyutlandırılması gereken her denetim için tekrarlayın.

1. Gerekirse, bir denetimin zaten dinamik düzen değişikliklerine sahip olup olmadığını denetlemek için [CMFCDynamicLayout:: HasItem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem) yöntemini kullanabilir ve bu tür bir denetim olup olmadığını anlamak Için [CMFCDynamicLayout:: IsEmpty](../mfc/reference/cmfcdynamiclayout-class.md#isempty) yöntemi kullanılabilir değişikliklere tabidir.

1. İletişim kutusu yerleşimini etkinleştirmek için [CWnd:: EnableDynamicLayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) yöntemini çağırın.

    ```cpp
    pDialog->EnableDynamicLayout(TRUE);
    ```

1. Kullanıcı iletişim kutusunu bir sonraki yeniden boyutlandırdığında, bu ayarları gerçekten uygulayan [CMFCDynamicLayout:: ayarla](../mfc/reference/cmfcdynamiclayout-class.md#adjust) yöntemi çağırılır.

1. Dinamik düzeni devre dışı bırakmak istiyorsanız, *Benabled* parametresi Için [CWnd:: EnableDynamicLayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) **değerini false** ile çağırın.

    ```cpp
    pDialog->EnableDynamicLayout(FALSE);
    ```

#### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>Dinamik düzeni bir kaynak dosyasından programlı bir şekilde ayarlamak için

1. Aşağıdaki örnekte olduğu gibi, dinamik düzen bilgilerini belirten ilgili kaynak betik dosyasında (. rc dosyası) bir kaynak adı belirtmek için [CMFCDynamicLayout:: MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical) yöntemini kullanın:

    ```cpp
    dynamicLayout->LoadResource("IDD_DIALOG1");
    ```

   Adlandırılmış kaynak, aşağıdaki örnekte olduğu gibi, kaynak dosyasındaki bir **AFX_DIALOG_LAYOUT** girişi biçiminde düzen bilgilerini içeren bir iletişim kutusuna başvurmalıdır:

    ```RC
    /////////////////////////////////////////////////////////////////////////////
    //
    // AFX_DIALOG_LAYOUT
    //

    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT
    BEGIN
    0x0000,
    0x6400,
    0x0028,
    0x643c,
    0x0028
    END

    IDD_DIALOG1 AFX_DIALOG_LAYOUT
    BEGIN
    0x0000,
    0x6464,
    0x0000,
    0x6464,
    0x0000,
    0x0000,
    0x6464,
    0x0000,
    0x0000

    END
    ```

## <a name="see-also"></a>Ayrıca bkz.

[CMFCDynamicLayout Sınıfı](../mfc/reference/cmfcdynamiclayout-class.md)<br/>
[Denetim Sınıfları](../mfc/control-classes.md)<br/>
[İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[Visual C++ 2015 ' de MFC Için dinamik Iletişim kutusu düzeni](https://mariusbancila.ro/blog/2015/07/27/dynamic-dialog-layout-for-mfc-in-visual-c-2015/)
