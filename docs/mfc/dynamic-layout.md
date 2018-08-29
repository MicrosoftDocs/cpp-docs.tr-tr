---
title: Dinamik düzen | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
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
ms.openlocfilehash: a6976669127dca79be59b85efbd15273b0f580a1
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132068"
---
# <a name="dynamic-layout"></a>Dinamik Düzen

MFC Visual Studio 2015'te kullanıcı boyutlandırabilirsiniz iletişim kutuları oluşturabilirsiniz ve düzenini değiştirme boyutu ayarlar yolunu kontrol edebilirsiniz. Örneğin, her zaman alt kısmında kalır, düğme bir iletişim kutusunun altındaki alt kenarı için ekleyebilirsiniz. Ayrıca liste kutuları ve editboxes metin alanları gibi belirli denetimler iletişim kullanıcının genişledikçe genişletmek için ayarlayabilirsiniz.

## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>MFC iletişim kutusu için dinamik düzen ayarlarını belirtme

Kullanıcı bir iletişim kutusu boyutlandırdığında iletişim kutusu denetimleri yeniden boyutlandırma veya X ve Y yönde taşıyın. Boyut ve konum bir denetimin bir iletişim kutusu kullanıcı yeniden boyutlandırdığında değişiklik dinamik düzeni olarak adlandırılır. Örneğin, bir iletişim kutusu yeniden boyutlandırılmış önce verilmiştir:

![Yeniden boyutlandırılmaya önce iletişim. ](../mfc/media/mfcdynamiclayout4.png "mfcdynamiclayout4")

Yeniden boyutlandırılmakta olan sonra listbox alan daha fazla öğe gösterilecek artırılır ve düğmelerinin sağ alt köşedeki birlikte taşınır:

![Yeniden boyutlandırılan sonra iletişim. ](../mfc/media/mfcdynamiclayout5.png "mfcdynamiclayout5")

Dinamik düzen Kaynak Düzenleyicisi'nde IDE içindeki her denetimin ayrıntılarını belirterek denetleyebilir veya bunu programlı erişerek yapabilirsiniz `CMFCDynamicLayout` nesne belirli bir denetim için ve özelliklerini ayarlama.

### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>Dinamik düzen özelliklerini kaynak düzenleyicisinde ayarlama

Dinamik düzen davranışı bir iletişim kutusu için kaynak düzenleyicisini kullanarak herhangi bir kod yazmak zorunda kalmadan ayarlayabilirsiniz.

#### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>Kaynak Düzenleyicisi'nde dinamik düzen özelliklerini ayarlamak için

1. Açık bir MFC projesi ile iletişim kutusu Düzenleyicisi'nde çalışmak istediğiniz iletişim kutusunu açın.

     ![İletişim kutusu kaynak düzenleyicisinde açın. ](../mfc/media/mfcdynamiclayout3.png "mfcdynamiclayout3")

2. Bir denetim seçin ve Özellikler penceresinde dinamik düzen özelliklerini ayarlayın. **Dinamik düzen** bölümünde Özellikler penceresindeki özelliklerini içeren **taşıma türü**, **boyutlandırma türü**ve bu özellikler için seçtiğiniz değerlere bağlı olarak ne kadar denetimleri tanımlayan belirli özellikleri, taşıyın veya boyutunu değiştirin. **Taşıma türü** bir denetimi nasıl taşındığını belirler iletişim kutusunun boyutunu değiştikçe; **Boyutlandırma türü** bir denetimin nasıl yeniden boyutlandırıldığını belirler iletişim kutusunun boyutunu değiştikçe. **Taşıma türü** ve **boyutlandırma türü** olabilir **yatay**, **dikey**, **hem**, veya **hiçbiri**dinamik olarak değiştirmek istediğiniz boyutlarına bağlı olarak. Yatay X boyutudur; Y yönünde dikey olur.

3. Bir sabit boyutta olması ve sağ alt köşede yerinde kalın düğmesi gibi bir denetim istiyorsanız, olduğu gibi yaygın **Tamam** veya **iptal** düğmeler kümesi **boyutlandırma türü** için **Hiçbiri**, ayarlayıp **taşıma türü** için **hem**. İçin **X taşıma** ve **Y taşıma** altındaki değerler **taşıma türü**, denetimi altındaki bir sabit uzaklıkta sağ alt köşesinde kalmak neden %100 ayarlayın.

     ![Dinamik düzen](../mfc/media/mfcdynamiclayout1.png "mfcdynamiclayout1")

4. İletişim genişledikçe genişletmek istediğiniz bir denetim de olduğunu varsayalım. Genellikle, bir kullanıcının metin alanının boyutunu artırmak için çok satırlı bir editbox'ta genişletmek için bir iletişim kutusu genişletebilir veya daha fazla veri görme bir liste denetimini genişletin. Bu durumda, ayarlama **boyutlandırma türü** her ikisine de ve **taşıma türü** yok. Ardından, **boyutlandırma X** ve **boyutlandırma Y** 100 değerleri.

     ![Dinamik düzen ayarları](../mfc/media/mfcdynamiclayout2.png "mfcdynamiclayout2")

5. Denetimleri için mantıklı olabilir diğer değerleri ile denemeler yapın. Tek satırlık metin içeren bir iletişim kutusu olabilir **boyutlandırma türü** kümesine **yatay** yalnızca, örneğin.

### <a name="setting-dynamic-layout-properties-programmatically"></a>Dinamik düzen özelliklerini programlı olarak ayarlama

Önceki yordamı, tasarım zamanında bir iletişim kutusu için dinamik bir düzen özelliklerini belirtmek için kullanışlıdır ancak çalışma zamanında dinamik düzenini denetlemek istiyorsanız, dinamik bir düzen özelliklerini programlı olarak ayarlayabilirsiniz.

#### <a name="to-set-dynamic-layout-properties-programmatically"></a>Dinamik düzen özelliklerini program üzerinden ayarlamak için

1. Bulmak veya bir yere dinamik düzeni iletişim kutusu için belirtmek istediğiniz iletişim sınıfınızın uygulama kodu oluşturun. Örneğin, bir yöntem eklemek isteyebilirsiniz `AdjustLayout` düzeni, iletişim ve ondan yerleştirir nerede çağrı değiştirilmesi gerekir. Bu oluşturucu veya iletişim kutusuna değişiklik yaptıktan sonra ilk çağırabilirsiniz.

2. Arama iletişim kutusu için [GetDynamicLayout](../mfc/reference/cwnd-class.md#getdynamiclayout), yöntemi `CWnd` sınıfı. `GetDynamicLayout` bir işaretçi döndüren bir `CMFCDynamicLayout` nesne.

    ```cpp
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();
    ```

3. Dinamik davranışı eklemek istediğiniz ilk denetim için statik yöntemler oluşturmak için dinamik düzen sınıfını kullanın [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure) denetim belirlenebilir şekilde kodlar yapısı. Uygun bir statik yöntemi seçerek bunu: [CMFCDynamicLayout::MoveHorizontal](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal), [CMFCDynamicLayout::MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical), [CMFCDynamicLayout::MoveNone](../mfc/reference/cmfcdynamiclayout-class.md#movenone), veya [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical). Taşıma/yatay veya dikey yönlerini yüzde olarak geçirdiğiniz. Tüm bu statik yöntemler, bir denetimin taşıma davranışını belirtmek için kullanabileceğiniz yeni oluşturulan bir MoveSettings nesnesi döndürür.

   Tam olarak iletişim yeni kenarlık sabit bir uzaklıkta kalmak bir denetimin edge neden olan boyutu, değişiklikler kadar 100 anlamına gelir taşıma aklınızda bulundurun.

    ```cpp
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);
    ```

4. Kullanır ve boyutu davranışı için aynı şeyi yapmak [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure) türü. Örneğin, iletişim boyutlandırdığında denetimin boyutunu değiştirmez belirtmek için aşağıdaki kodu kullanın:

    ```cpp
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();
    ```

5. Denetim kullanarak dinamik düzen Manager'a ekleme [CMFCDynamicLayout::AddItem](../mfc/reference/cmfcdynamiclayout-class.md#additem) yöntemi. İstenen denetimini belirtme farklı yollar için iki aşırı yüklemesi vardır. Denetimin pencere tanıtıcısı (HWND) alır ve diğer denetim kimliği alır.

    ```cpp
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);
    ```

6. Taşınan veya yeniden boyutlandırılan gereken her denetim için yineleyin.

7. Gerekirse, kullanabilir, [CMFCDynamicLayout::HasItem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem) bir denetim zaten dyamic düzen değişiklikleri, tabi denetimleri listesinde olup olmadığını belirlemek için yöntemi veya [CMFCDynamicLayout::IsEmpty](../mfc/reference/cmfcdynamiclayout-class.md#isempty) değişiklikleri tabi olan herhangi bir denetim olup olmadığını belirlemek için yöntemi.

8. İletişim düzeni etkinleştirmek için çağrı [CWnd::EnableDynamicLayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) yöntemi.

    ```cpp
    pDialog->EnableDynamicLayout(TRUE);
    ```

9. Kullanıcı yeniden boyutlandırır iletişim, sonraki açışınızda [CMFCDynamicLayout::Adjust](../mfc/reference/cmfcdynamiclayout-class.md#adjust) gerçekten ayarların uygulandığı yöntemi çağrılır.

10. Dinamik düzen devre dışı bırakmak isterseniz, çağrı [CWnd::EnableDynamicLayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) ile **FALSE** olarak *bEtkin* parametresi.

    ```cpp
    pDialog->EnableDynamicLayout(FALSE);
    ```

#### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>Dinamik düzeni bir kaynak dosyasından program üzerinden ayarlamak için

1. Kullanım [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical) yöntem aşağıdaki örnekteki gibi dinamik düzen bilgilerini belirten ilgili kaynak betiği (.rc dosyası) bir kaynak adı belirtmek için:

    ```cpp
    dynamicLayout->LoadResource("IDD_DIALOG1");
    ```

     Adlandırılmış kaynağı biçiminde düzeni bilgilerini içeren bir iletişim kutusu başvurmalıdır bir **AFX_DIALOG_LAYOUT** kaynak dosyasında, aşağıdaki örnekte olduğu gibi giriş:

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

[CMFCDynamicLayout Sınıfı](../mfc/reference/cmfcdynamiclayout-class.md)  
[Denetim Sınıfları](../mfc/control-classes.md)  
[İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)  
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)  
[Visual C++ 2015'te MFC için dinamik iletişim düzeni](https://mariusbancila.ro/blog/2015/07/27/dynamic-dialog-layout-for-mfc-in-visual-c-2015/)
