---
title: "Uygulamanızdaki özellik sayfalarını kullanma | Microsoft Docs"
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
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4247a40fa364774674c1c79845625df51ecd34ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-property-sheets-in-your-application"></a>Uygulamanızdaki Özellik Sayfalarını Kullanma
Özellik sayfasını, uygulamanızda kullanmak için aşağıdaki adımları tamamlayın:  
  
1.  Her özellik sayfası için bir iletişim şablonunu kaynağı oluşturun. Her çıkışı yerleşim sayfasında olarak tutarlı bir şekilde olabildiğince, böylece kullanıcı bir sayfadan diğerine geçişi göz önünde bulundurun.  
  
     Tüm sayfalar için iletişim kutusu şablonları aynı boyutta olması gerekmez. Çerçeve en büyük sayfa boyutu özellik sayfaları için özellik sayfasındaki ayırmak için ne kadar alan belirlemek için kullanır.  
  
     Özellik sayfası iletişim şablon kaynağı oluşturduğunuzda, aşağıdaki stiller iletişim özelliklerini özellik sayfasında belirtmeniz gerekir:  
  
    -   Ayarlama **resim yazısı** üzerinde düzenleme kutusu **genel** sayfa için bu sayfayı sekmesindeki görünmesini istediğiniz metin.  
  
    -   Ayarlama **stili** liste kutusunu **stilleri** sayfasına **alt**.  
  
    -   Ayarlama **kenarlık** liste kutusunu **stilleri** sayfasına **ince**.  
  
    -   Emin **Titlebar** onay kutusunu **stilleri** sayfa seçilidir.  
  
    -   Emin **devre dışı** onay kutusunu **daha fazla stil** sayfa seçilidir.  
  
2.  Oluşturma bir [CPropertyPage](../mfc/reference/cpropertypage-class.md)-türetilmiş her bir özellik sayfası iletişim şablon karşılık gelen sınıf. Bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md). Seçin `CPropertyPage` temel sınıf olarak.  
  
3.  Üye bu özellik sayfası için değerleri tutması için değişkenleri oluşturun. Özelleştirilmiş bir iletişim kutusu bir özellik sayfası olduğu için üye değişkenleri için özellik sayfası ekleme işlemi tam olarak bir iletişim kutusu için üye değişkenleri ekleme aynıdır. Daha fazla bilgi için bkz: [iletişim kutusu denetimleri için üye değişkenleri tanımlama](../windows/defining-member-variables-for-dialog-controls.md).  
  
4.  Oluşturmak bir [CPropertySheet](../mfc/reference/cpropertysheet-class.md) kaynak kodunuzu nesne. Genellikle, oluşturmak `CPropertySheet` özellik sayfasını görüntüler komut işleyici nesnesi. Bu nesnenin tüm özellik sayfasını temsil eder. Kalıcı özellik sayfası ile oluşturursanız [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) işlevi, framework varsayılan olarak üç komut düğmesi sağlar: Tamam, iptal et ve Uygula. Kalıcı olmayan özellik sayfaları ile oluşturulan için hiçbir komut düğmeleri framework oluşturur [oluşturma](../mfc/reference/cpropertysheet-class.md#create) işlevi. Öğesinden bir sınıf türetin gerekmez `CPropertySheet` (örneğin, bir önizleme penceresi) diğer denetimleri ekleme ya da kalıcı olmayan özellik sayfasını görüntülemek istediğiniz sürece. Özellik sayfasını kapatmak için kullanılabilir tüm varsayılan denetimler içermediğinden kalıcı olmayan özellik sayfaları için bu adım gereklidir.  
  
5.  Özellik sayfasına eklenecek her bir sayfa için aşağıdakileri yapın:  
  
    -   Her biri için bir nesne oluşturmak `CPropertyPage`-türetilen bu işlemde daha önce oluşturduğunuz sınıfı.  
  
    -   Çağrı [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage) her sayfa için.  
  
     Genellikle, oluşturur nesne `CPropertySheet` da oluşturur `CPropertyPage` Bu adımda nesneleri. Ancak, uygulamanız varsa bir `CPropertySheet`-türetilmiş sınıf, katıştırmak `CPropertyPage` nesnelerini `CPropertySheet` nesne ve çağrı `AddPage` her sayfasından için `CPropertySheet`-türetilmiş sınıf oluşturucu. `AddPage`ekler `CPropertyPage` nesne özelliği sayfanın sayfaları listesine ancak aslında bu sayfa için pencere oluşturmaz. Bu nedenle, çağırmak için özellik sayfası penceresi oluşturma kadar beklenecek gerekli değil `AddPage`; çağırabilirsiniz `AddPage` özelliği sayfanın oluşturucusundan.  
  
     Bir özellik sayfası özellik sayfasını, tek bir satır sığmayacak kadar çok daha fazla sekme varsa, varsayılan olarak, birden çok satır sekmeleri yığın. Yığınlama devre dışı bırakmak için çağrı [CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) kümesine parametresiyle **FALSE**. Çağırmalısınız `EnableStackedTabs` özellik sayfası oluşturduğunuzda.  
  
6.  Çağrı [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) veya [oluşturma](../mfc/reference/cpropertysheet-class.md#create) özellik sayfasını görüntülemek için. Çağrı `DoModal` modal bir iletişim kutusu olarak bir özellik sayfası oluşturmak için. Çağrı **oluşturma** kalıcı olmayan iletişim kutusu olarak özellik sayfası oluşturmak için.  
  
7.  Özellik sayfaları ve özellik sayfasını sahibi arasında veri değişimi. Bu makalede açıklanan [veri değişimi](../mfc/exchanging-data.md).  
  
 MFC genel örnek özellik sayfalarını kullanma örneği için bkz: [PROPDLG](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)

