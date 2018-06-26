---
title: Dinamik düzen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0fcfff6bcca8cb073c337043490d32f8724aad
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930358"
---
# <a name="dynamic-layout"></a>Dinamik Düzen
MFC Visual Studio 2015'te kullanıcı genişletebilir iletişim kutuları oluşturma ve düzeni boyutundaki değişikliği ayarlar yolunu kontrol edebilirsiniz. Örneğin, her zaman en altında kalırlar şekilde alt kenarı bir iletişim kutusunun altındaki düğmeleri ekleyebilirsiniz. Ayrıca belirli denetimleri süzer, editboxes ve metin alanları gibi kullanıcı iletişim kutusu genişlediği sürece genişletmek için ayarlayabilirsiniz.  
  
## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>MFC iletişim kutusu için dinamik düzen ayarları belirtme  
 Kullanıcı bir iletişim kutusu yeniden boyutlandırır, iletişim kutusu denetimleri yeniden boyutlandırma veya X ve Y yönde taşıma. Değiştirme boyutu ya da kullanıcı bir iletişim kutusu yeniden boyutlandırır olduğunda bir denetimin konumunu dinamik düzen adı verilir. Örneğin, bir iletişim kutusu yeniden boyutlandırılabilir önce verilmiştir:  
  
 ![Yeniden boyutlandırılan önce iletişim. ] (../mfc/media/mfcdynamiclayout4.png "mfcdynamiclayout4")  
  
 Yeniden boyutlandırılan sonra listbox alan daha fazla öğeleri gösterecek şekilde artar ve düğmelerinin sağ alt köşedeki birlikte taşınır:  
  
 ![Yeniden boyutlandırılan sonra iletişim. ] (../mfc/media/mfcdynamiclayout5.png "mfcdynamiclayout5")  
  
 Dinamik düzen kaynak düzenleyicisinde IDE içinde her denetim için ayrıntıları belirterek kontrol edebilirsiniz ya da bunu programlı erişerek yapabilirsiniz `CMFCDynamicLayout` nesne belirli bir denetim için ve özelliklerini ayarlama.  
  
### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>Kaynak Düzenleyicisi'nde dinamik düzen özelliklerini ayarlama  
 Kaynak Düzenleyicisi'ni kullanarak herhangi bir kod yazmak zorunda kalmadan bir iletişim kutusu için dinamik düzen davranışı ayarlayabilirsiniz.  
  
##### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>Kaynak Düzenleyicisi'nde dinamik düzen özelliklerini ayarlamak için  
  
1.  Açık bir MFC projesine ile iletişim kutusu Düzenleyicisi'nde çalışmak istediğiniz iletişim kutusunu açın.  
  
     ![İletişim kutusu, kaynak düzenleyicisinde açın. ] (../mfc/media/mfcdynamiclayout3.png "mfcdynamiclayout3")  
  
2.  Bir denetim seçin ve Özellikler penceresinde dinamik düzen özelliklerini ayarlayın. **Dinamik düzen** Özellikler penceresini bölümünde özelliklerini içeren **taşıma türü**, **boyutlandırma türü**ve bu özellikler için seçilen değerlere bağlı olarak ne kadar denetimleri tanımlayan belirli özellikleri taşıyın veya boyutunu değiştirin. **Türü taşıma** denetim nasıl taşınır belirler iletişim kutusunun boyutunu değiştikçe; **Boyutlandırma türü** denetim nasıl boyutlandırılır belirler iletişim kutusunun boyutunu değiştirilmiş olarak. **Türü taşıma** ve **boyutlandırma türü** olabilir **yatay**, **dikey**, **her ikisi de**, veya **hiçbiri**bağlı olarak, dinamik olarak değiştirmek istediğiniz boyutları. Yatay X boyutudur; Dikey Y yönünde ' dir.  
  
3.  Bir sabit boyutta olmasını ve sağ alt köşede yerinde kalmaya düğmesi gibi bir denetim isterseniz, olduğu gibi yaygın **Tamam** veya **iptal** düğmeler kümesi **boyutlandırma türü** için **Hiçbiri**ve **taşıma türü** için **her ikisi de**. İçin **taşıma X** ve **taşıma Y** altında değerleri **taşıma türü**, % 100 alt sabit bir uzaklıkta sağ alt köşesinde kalmak denetimi neden ayarlayın.  
  
     ![Dinamik düzen](../mfc/media/mfcdynamiclayout1.png "mfcdynamiclayout1")  
  
4.  Ayrıca iletişim genişlediği sürece genişletmek istediğiniz bir denetim olduğunu varsayalım. Genellikle, bir kullanıcı bir iletişim kutusunu metin alanının boyutunu artırmak için çok satırlı editbox genişletmek için Genişlet ya da daha fazla verileri görmek için liste denetimi genişletin. Bu durumda, ayarlamak **boyutlandırma türü** hem ve **taşıma türü** yok. Ardından, **boyutlandırma X** ve **boyutlandırma Y** 100 değerleri.  
  
     ![Dinamik düzen ayarları](../mfc/media/mfcdynamiclayout2.png "mfcdynamiclayout2")  
  
5.  Denetimleri için mantıklı olabilir diğer değerler deneyin. Tek satırlı metin kutusu içeren bir iletişim kutusu olabilir **boyutlandırma türü** kümesine **yatay** yalnızca, örneğin.  
  
### <a name="setting-dynamic-layout-properties-programmatically"></a>Dinamik düzen özelliklerini programlı olarak ayarlama  
 Önceki yordamda tasarım zamanında bir iletişim kutusu dinamik düzen özelliklerini belirtmek için yararlıdır, ancak çalışma zamanında dinamik düzen denetlemek istiyorsanız, dinamik düzen özellikleri programlı olarak ayarlayabilirsiniz.  
  
##### <a name="to-set-dynamic-layout-properties-programmatically"></a>Dinamik düzen özellikleri programlı olarak ayarlamak için  
  
1.  Bulunamadı veya bir yere dinamik düzen iletişim kutusu için belirtmek istediğiniz iletişim sınıfınızın uygulama kodu oluşturun. Örneğin, bir yöntem eklemek isteyebilirsiniz `AdjustLayout` düzeni, iletişim ve buradan nereye yerleştirir çağrısı değiştirilmesi gerekir. Bu oluşturucu veya iletişim kutusuna değişiklik yaptıktan sonra ilk çağırabilirsiniz.  
  
2.  Arama iletişim kutusu için [GetDynamicLayout](../mfc/reference/cwnd-class.md#getdynamiclayout), yöntemi `CWnd` sınıfı. `GetDynamicLayout` bir işaretçi döndüren bir `CMFCDynamicLayout` nesnesi.  
  
 ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();

 ```  
  
3.  Dinamik davranış eklemek istediğiniz ilk denetimi için statik yöntemler oluşturmak için dinamik düzen sınıfını kullanma [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure) Denetimi ayarlanmış şekilde kodlar yapısı. Uygun statik yöntemi seçerek bunu: [CMFCDynamicLayout::MoveHorizontal](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal), [CMFCDynamicLayout::MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical), [CMFCDynamicLayout::MoveNone](../mfc/reference/cmfcdynamiclayout-class.md#movenone), veya [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical). Taşıma yatay ve/veya dikey yönlerini yüzde olarak geçirin. Tüm bu statik yöntemler bir denetimin taşıma davranışını belirtmek için kullanabileceğiniz yeni oluşturulan bir MoveSettings nesnesi döndürür.  
  
     Tam olarak iletişim yeni kenarlık sabit bir uzaklıkta kalmak bir denetimin kenar neden olan boyutu, değişiklikler kadar 100 anlamına gelir taşıma göz önünde bulundurun.  
  
 ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);

 ```  
  
4.  Kullanan boyutu davranışı için aynı şeyler [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure) türü. Örneğin, iletişim kutusunu yeniden boyutlandırır olduğunda denetim boyutunu değiştirmez belirtmek için aşağıdaki kodu kullanın:  
  
 ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();

 ```  
  
5.  Denetimi kullanarak dinamik düzen Yöneticisi eklemek [CMFCDynamicLayout::AddItem](../mfc/reference/cmfcdynamiclayout-class.md#additem) yöntemi. İstenen denetimi belirtme farklı yöntemler için iki aşırı vardır. Bir denetimin pencere işleyicisi (HWND) alır ve diğer denetim kimliğini alır  
  
 ```  
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);

 ```  
  
6.  Taşınan veya yeniden boyutlandırılan gereken her denetim için yineleyin.  
  
7.  Gerekirse, kullanma, [CMFCDynamicLayout::HasItem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem) bir denetim zaten dyamic düzen değişiklikleri tabi denetimleri listesinde olup olmadığını belirlemek için yöntemi veya [CMFCDynamicLayout::IsEmpty](../mfc/reference/cmfcdynamiclayout-class.md#isempty) değişiklikleri tabi olan herhangi bir denetim olup olmadığını belirlemek için yöntem.  
  
8.  İletişim düzeni etkinleştirmek için arama [CWnd::EnableDynamicLayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) yöntemi.  
  
 ```  
    pDialog->EnableDynamicLayout(TRUE);

 ```  
  
9. Kullanıcı yeniden boyutlandırır iletişim sonraki açışınızda [CMFCDynamicLayout::Adjust](../mfc/reference/cmfcdynamiclayout-class.md#adjust) gerçekten ayarları uygulandığı yöntemi çağrılır.  
  
10. Dinamik düzen devre dışı bırakmak istiyorsanız, çağrı [CWnd::EnableDynamicLayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) ile **FALSE** olarak *bEtkin* parametresi.  
  
 ```  
    pDialog->EnableDynamicLayout(FALSE);

 ```  
  
##### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>Dinamik düzen kaynak dosyasından programlı olarak ayarlamak için  
  
1.  Kullanım [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical) yöntem aşağıdaki örnekteki gibi dinamik düzen bilgileri belirten ilgili kaynak komut dosyasında (.rc dosyası) bir kaynak adı belirtin:  
  
 ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");

 ```  
  
     Adlandırılmış kaynak biçiminde düzen bilgilerini içeren bir iletişim kutusu başvurmalıdır bir **AFX_DIALOG_LAYOUT** kaynak dosyasında aşağıdaki örnekteki gibi girişi:  
  
 ''' * / / / * / / * / / AFX_DIALOG_LAYOUT * / /  
 
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    BEGIN 0X0000, 0X6400, 0X0028 =, 0X643C, 0X0028 =  
    END 
 
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    BEGIN 0X0000, 0X6464, 0X0000, 0X6464, 0X0000, 0X0000, 0X6464, 0X0000, 0X0000  
 
    END 
 ```  
  
## See Also  
 [CMFCDynamicLayout Class](../mfc/reference/cmfcdynamiclayout-class.md)   
 [Control Classes](../mfc/control-classes.md)   
 [Dialog Box Classes](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../windows/dialog-editor.md)

