---
title: Bir durum çubuğu bölmesinin metnini güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa04fdee2b63f9d91d2bdd7dfd62100b3e32a2c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393327"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Durum Çubuğu Bölmesinin Metnini Güncelleştirme

Bu makalede, bir MFC durum çubuğu bölmesinde görüntülenen metni değiştirme açıklanmaktadır. Durum çubuğu — sınıfın bir pencere nesnesi [CStatusBar](../mfc/reference/cstatusbar-class.md) — çeşitli "bölmeleri." içerir Her bölmede bir dikdörtgen bilgilerini görüntülemek için kullanabileceğiniz bir durum çubuğu alanıdır. Örneğin, birçok uygulama en sağdaki bölmelerinde CAPS LOCK NUM LOCK ve diğer anahtarlar durumunu görüntüler. Uygulamalar ayrıca genellikle en soldaki bölmesi (0), bilgilendirici metin "ileti bölmesi." olarak da adlandırılır gösterir Örneğin, varsayılan MFC durum çubuğu ileti bölmesinde seçili menü öğesi veya araç çubuğu düğmesini açıklayan bir dize görüntülemek için kullanır. Aşağıdaki şekilde [durum çubukları](../mfc/status-bar-implementation-in-mfc.md) MFC Uygulama Sihirbazı tarafından oluşturulan bir uygulamadan bir durum çubuğu gösterir.

Varsayılan olarak, MFC olmayan etkinleştirmez bir `CStatusBar` bölmesinde bölmesi oluşturur. Bir bölme etkinleştirmek için durum çubuğundaki her bölme için on_update_command_uı makrosu kullanın ve bölmeleri güncelleştirmeniz gerekir. Çünkü bölmeler WM_COMMAND iletileri gönderme (bunlar, araç çubuğu düğmeleri gibi değil), el ile kod yazmanız gerekir.

Örneğin, bir bölme olduğunu varsayalım `ID_INDICATOR_PAGE` komut tanımlayıcısını ve bu belgede geçerli sayfa numarası içeriyor. Aşağıdaki yordam, yeni bir bölme durum çubuğunda oluşturmayı açıklar.

### <a name="to-make-a-new-pane"></a>Yeni bir bölme yapma

1. Bölmedeki komut kimliği tanımlayın

     Üzerinde **görünümü** menüsünü tıklatın **kaynak görünümü**. Proje kaynağını sağ tıklatıp **kaynak sembolleri**. Kaynak sembolleri iletişim kutusuna tıklayın `New`. Bir komut Kimliğini yazın: Örneğin, `ID_INDICATOR_PAGE`. Kimliği için bir değer belirtin veya kaynak sembolleri iletişim kutusu tarafından önerilen değeri kabul edin. Örneğin, `ID_INDICATOR_PAGE`, varsayılan değeri kabul edin. Kaynak sembolleri iletişim kutusunu kapatın.

1. Bölmede görüntülemek için bir varsayılan dizesini tanımlar.

     Açık kaynak görünümü ile çift **dize tablosu** penceresinde uygulamanız için kaynak türlerini listeler. İle **dize tablosu** açık bir düzenleyici seçin **yeni dize** gelen **Ekle** menüsü. Dize özellikleri penceresinde, bölmedeki komut kimliği (örneğin, `ID_INDICATOR_PAGE`) ve "Page" gibi varsayılan bir dize değeri yazın. Dize Düzenleyicisi'ni kapatın. (Bir derleyici hatası kaçınmak için bir varsayılan dizesine ihtiyacınız vardır.)

1. Bölmesine eklemek *göstergeleri* dizisi.

     Dosya MAINFRM. CPP, bulun *göstergeleri* dizisi. Bu dizinin tüm sırayla soldan sağa doğru durum çubuğunun göstergeleri için komut kimlikleri listeler. Dizideki uygun noktada için burada gösterildiği gibi bölmedeki komut kimliği girin `ID_INDICATOR_PAGE`:

     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

Metni bir bölmede görüntülemek için önerilen yöntem çağırmaktır `SetText` sınıfının üye işlevinde `CCmdUI` bölmesi için bir güncelleştirme işleyici işlevi içinde. Örneğin, bir tamsayı değişkeni ayarlamak isteyebilirsiniz *m_nPage* kullanın ve geçerli sayfa numarası içeren `SetText` bölmedeki metni bir dize, sayı sürümüne ayarlamak için.

> [!NOTE]
>  `SetText` Yaklaşım önerilir. Çağırarak biraz daha düşük bir düzeyde bu görevi gerçekleştirmek mümkündür `CStatusBar` üye işlevi `SetPaneText`. Buna rağmen yine de bir güncelleştirme işleyici gerekir. Bu tür için bir işleyici bölmesinde, MFC otomatik olarak bölmesinde içeriği silmeyi devre dışı bırakır.

Aşağıdaki yordam bir bölmede metni görüntülemek için bir güncelleştirme işleyici işlevi kullanmayı gösterir.

#### <a name="to-make-a-pane-display-text"></a>Metni görüntülemek için bir bölme yapma

1. Komut için bir komut güncelleştirme işleyicisi ekleyin.

     İşleyici için bir prototip için burada gösterildiği gibi el ile eklemeniz `ID_INDICATOR_PAGE` (içinde MAINFRM. H):

     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. Uygun. CPP işleyicinin tanımı için burada gösterildiği gibi ekleyin `ID_INDICATOR_PAGE` (içinde MAINFRM. CPP):

     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

     Bu işleyicinin son üç satır metni görüntüler kodu var.

1. On_update_command_uı makrosu, için aşağıda gösterildiği gibi uygun ileti eşlemede ekleme `ID_INDICATOR_PAGE` (içinde MAINFRM. CPP):

     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

Değerini tanımladıktan sonra *m_nPage* üye değişkeni (sınıf `CMainFrame`), bu teknik, sayfa numarası, uygulamanın diğer göstergeleri güncelleştirmeleri aynı şekilde boşta işleme sırasında bölmesinde görüntülenecek neden olur. Varsa *m_nPage* değişiklikler, sonraki boşta döngü sırasında görüntü değişiklikleri.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [(Program koşullar değiştikçe araç çubuğu düğmeleri ve menü öğeleri güncelleştirmek nasıl) kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Durum Çubuğu Uygulaması](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar Sınıfı](../mfc/reference/cstatusbar-class.md)
