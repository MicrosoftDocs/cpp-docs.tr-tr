---
title: Tek Bir Belgeye Birden Çok Görünüm Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: b665f090fc680221be70f170452d756dd5f68dc5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284287"
---
# <a name="adding-multiple-views-to-a-single-document"></a>Tek Bir Belgeye Birden Çok Görünüm Ekleme

Microsoft Foundation Class (MFC) kitaplığı ile oluşturulan bir tek Belgeli Arabirim (SDI) uygulamasında, her bir belge türü tek bir görünüm türü ile ilişkilidir. Bazı durumlarda, bir belge öğesinin geçerli görünümü ile yeni bir görünüm geçiş olanağı sağlamak için tercih edilir.

> [!TIP]
>  Tek bir belgenin birden çok görünüm uygulama ile ilgili ek yordamlar için bkz. [CDocument::AddView](../mfc/reference/cdocument-class.md#addview) ve [TOPLAMAK](../visual-cpp-samples.md) MFC örneği.

Yeni bir ekleyerek bu işlevi uygulayabilirsiniz `CView`-türetilmiş sınıf ve görünümler varolan bir MFC uygulamasına dinamik geçiş için ek kod.

Adımlar aşağıdaki gibidir:

- [Mevcut uygulama sınıfını değiştirme](#vcconmodifyexistingapplicationa1)

- [Oluşturma ve değiştirme yeni görünüm sınıfı](#vcconnewviewclassa2)

- [Oluşturma ve yeni görünüm ekleme](#vcconattachnewviewa3)

- [Geçiş işlevi uygulayın](#vcconswitchingfunctiona4)

- [Görünüme geçiş yapmak için destek eklendi](#vcconswitchingtheviewa5)

Bu konunun geri kalanı aşağıdaki varsayılır:

- Adını `CWinApp`-türetilmiş nesne `CMyWinApp`, ve `CMyWinApp` bildirildi ve içinde tanımlanan *MYWINAPP. H* ve *MYWINAPP. CPP*.

- `CNewView` Yeni adı `CView`-nesne, türetilmiş ve `CNewView` bildirildi ve içinde tanımlanan *NEWVIEW. H* ve *NEWVIEW. CPP*.

##  <a name="vcconmodifyexistingapplicationa1"></a> Mevcut uygulama sınıfını değiştirme

Görünümler arasında geçiş yapmak uygulama için uygulama sınıfı görünümleri ve bunlara geçiş yapmak için bir yöntem depolamak için üye değişkenleri ekleyerek değiştirmeniz gerekir.

Bildirimi için aşağıdaki kodu ekleyin `CMyWinApp` içinde *MYWINAPP. H*:

[!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

Yeni üye değişkenleri `m_pOldView` ve `m_pNewView`, geçerli görünümü ve yeni oluşturulan bir gelin. Yeni yöntemi (`SwitchView`) kullanıcı tarafından istendiğinde görünümleri geçer. Yöntemin gövdesi içinde bu konunun ilerleyen bölümlerinde açıklanan [geçiş işlevi uygulayın](#vcconswitchingfunctiona4).

Windows ileti tanımlayan yeni bir üst bilgi dosyası dahil olmak üzere uygulama sınıfı son değiştirilme gerektirir (**WM_INITIALUPDATE**) geçiş işlevi kullanılır.

INCLUDE bölümünde aşağıdaki satırı ekleyin *MYWINAPP. CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

Değişikliklerinizi kaydedip sonraki adıma devam edin.

##  <a name="vcconnewviewclassa2"></a> Oluşturma ve değiştirme yeni görünüm sınıfı

Yeni Görünüm sınıfı oluşturma yapılan kolay kullanarak **yeni sınıf** komut sınıf görünümünden kullanılabilir. Öğesinden türetilen Bu sınıf için tek gereksinim olmasıdır `CView`. Bu yeni bir sınıf uygulamaya ekleyin. Projeye yeni bir sınıf ekleme ile ilgili ayrıntılı bilgi için bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md).

Sınıf projeye ekledikten sonra bazı görünüm sınıfı üyeleri erişilebilirliğini değiştirmeniz gerekir.

Değiştirme *NEWVIEW. H* gelen erişim belirticisi değiştirerek **korumalı** için **genel** oluşturucu ve yıkıcı için. Bu, oluşturulan ve dinamik olarak yok ve görünür hale gelmeden önce görünümü görünümünü değiştirmek için sınıf sağlar.

Değişikliklerinizi kaydedip sonraki adıma devam edin.

##  <a name="vcconattachnewviewa3"></a> Oluşturma ve yeni görünüm ekleme

Oluşturup yeni görünüm eklemek için değiştirmeniz gerekir `InitInstance` uygulama sınıfınızın işlevi. Yeni bir görünüm nesnesi ve ardından başlatır hem oluşturan yeni bir kod değişikliği ekler `m_pOldView` ve `m_pNewView` ile iki varolan nesneleri görüntüle.

İçinde yeni görünüm oluşturulduğundan `InitInstance` işlevi, yeni ve var olan görünümleri kalıcı uygulama ömrü boyunca. Ancak, uygulama yeni görünüm kolayca dinamik olarak oluşturabilir.

Çağırdıktan sonra bu kodu ekleyin `ProcessShellCommand`:

[!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

Değişikliklerinizi kaydedip sonraki adıma devam edin.

##  <a name="vcconswitchingfunctiona4"></a> Geçiş işlevi uygulayın

Önceki adımda oluşturulan ve başlatılan yeni bir görünüm nesnesi kod eklendi. Geçiş yöntemi uygulamak için son ana parçası olan `SwitchView`.

Uygulama sınıfınız için uygulama dosyasının sonunda (*MYWINAPP. CPP*), aşağıdaki yöntemi ekleyin:

[!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

Değişikliklerinizi kaydedip sonraki adıma devam edin.

##  <a name="vcconswitchingtheviewa5"></a> Görünüme geçiş yapmak için destek eklendi

Son adım, çağıran kod ekleyerek içerir `SwitchView` görünümler arasında geçiş yapmak uygulama gerektiğinde yöntemi. Bu çeşitli şekillerde yapılabilir: seçim yapması için yeni menü öğesi ekleme ya da belirli koşullar karşılandığında görünüm dahili olarak geçiş.

Yeni menü öğeleri ve komut işleyici işlevleri ekleme hakkında daha fazla bilgi için bkz. [komutlar ve denetim bildirimleri için işleyiciler](../mfc/handlers-for-commands-and-control-notifications.md).

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)
