---
title: Durum Çubuğu Bölmesinin Metnini Güncelleştirme
ms.date: 11/04/2016
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
ms.openlocfilehash: 723046fc1721cc46608e00f19a4431ef081be13d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366686"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Durum Çubuğu Bölmesinin Metnini Güncelleştirme

Bu makalede, MFC durum çubuğu bölmesinde görünen metnin nasıl değiştirilen açıklanmıştır. [CStatusBar](../mfc/reference/cstatusbar-class.md) sınıfının bir pencere nesnesi olan durum çubuğu birkaç "bölme" içerir. Her bölme, durum çubuğunun bilgileri görüntülemek için kullanabileceğiniz dikdörtgen bir alanıdır. Örneğin, birçok uygulama CAPS LOCK, NUM LOCK ve diğer anahtarların durumunu en sağ bölmelerde görüntüler. Uygulamalar da genellikle soldaki bölmede bilgilendirici metin görüntüler (bölme 0), bazen "ileti bölmesi" olarak adlandırılır. Örneğin, varsayılan MFC durum çubuğu, şu anda seçili menü öğesini veya araç çubuğu düğmesini açıklayan bir dize görüntülemek için ileti bölmesi kullanır. [Durum Çubukları'ndaki](../mfc/status-bar-implementation-in-mfc.md) şekil, Uygulama Sihirbazı tarafından oluşturulan MFC uygulamasından bir durum çubuğunu gösterir.

Varsayılan olarak, MFC bölmeyi oluşturduğunda bölmeyi `CStatusBar` etkinleştirmez. Bölmeyi etkinleştirmek için durum çubuğundaki her bölme için ON_UPDATE_COMMAND_UI makroyu kullanmanız ve bölmeleri güncelleştirmeniz gerekir. Bölmeler WM_COMMAND iletigöndermediği için (araç çubuğu düğmelerine benzemezler), kodu el ile yazmanız gerekir.

Örneğin, bir bölmenin `ID_INDICATOR_PAGE` komut tanımlayıcısı olduğunu ve bir belgedeki geçerli sayfa numarasını içerdiğini varsayalım. Aşağıdaki yordam, durum çubuğunda yeni bir bölme oluşturma açıklar.

### <a name="to-make-a-new-pane"></a>Yeni bir bölme yapmak için

1. Bölmenin komut kimliğini tanımlayın.

   **Görünüm** menüsünde **Kaynak Görünümü'nü**tıklatın. Proje kaynağını sağ tıklatın ve **Kaynak Sembolleri'ni**tıklatın. Kaynak Sembolleri iletişim `New`kutusunda. Komut kimliği adı yazın: `ID_INDICATOR_PAGE`örneğin. Kimlik için bir değer belirtin veya Kaynak Sembolleri iletişim kutusu tarafından önerilen değeri kabul edin. Örneğin, varsayılan `ID_INDICATOR_PAGE`değeri kabul etmek için. Kaynak Sembolleri iletişim kutusunu kapatın.

1. Bölmede görüntülenecek varsayılan bir dize tanımlayın.

   Kaynak Görünümü açıkken, uygulamanızın kaynak türlerini listeleyen pencerede **String Tablosu'nu** çift tıklatın. String **Table** düzenleyicisi açıkken, **Ekle** menüsünden **Yeni String'i** seçin. Bölmenizin komut kimliğini seçin (örneğin, `ID_INDICATOR_PAGE`) ve "Sayfa " gibi varsayılan bir dize değeri yazın. Dize düzenleyicisini kapatın. (Derleyici hatasını önlemek için varsayılan bir dize gerekir.)

1. Bölmeyi *göstergeler* dizisine ekleyin.

   DOSYA MAINFRM'de. CPP, *göstergeler* dizisini bulun. Bu dizi, soldan sağa sırayla durum çubuğunun tüm göstergeleri için komut iD'lerini listeler. Dizideki uygun noktada, burada gösterildiği gibi bölmenizin komut kimliğini `ID_INDICATOR_PAGE`girin:

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

Metni bölmede görüntülemenin önerilen yolu, bölme `SetText` için güncelleştirme `CCmdUI` işleyicisi işlevinde sınıfın üye işlevini çağırmaktır. Örneğin, geçerli sayfa numarasını içeren bir tamsayı *değişkeni m_nPage* ayarlamak `SetText` ve bölmenin metnini bu sayının dize sürümüne ayarlamak için kullanmak isteyebilirsiniz.

> [!NOTE]
> Yaklaşım `SetText` önerilir. Bu görevi `CStatusBar` üye işlevi `SetPaneText`çağırarak biraz daha düşük bir düzeyde gerçekleştirmek mümkündür. Yine de, yine de bir güncelleştirme işleyicisi gerekir. Bölme için böyle bir işleyici olmadan, MFC bölmeyi otomatik olarak devre dışı kakarak içeriğini siler.

Aşağıdaki yordam, bir bölmede metin görüntülemek için bir güncelleştirme işleyicisi işlevinin nasıl kullanılacağını gösterir.

#### <a name="to-make-a-pane-display-text"></a>Bölme görüntüleme metni yapmak için

1. Komut için bir komut güncelleştirme işleyicisi ekleyin.

   Burada gösterildiği gibi işleyici için el ile `ID_INDICATOR_PAGE` bir prototip ekleyin (MAINFRM'de). H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. Uygun olarak . CPP dosyası, işleyicitanımını ekleyin, burada `ID_INDICATOR_PAGE` gösterildiği gibi (MAINFRM'de). CPP:

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   Bu işleyicinin son üç satırı, metninizi görüntüleyen koddur.

1. Uygun ileti haritasında, burada gösterildiği gibi ON_UPDATE_COMMAND_UI `ID_INDICATOR_PAGE` makroyu ekleyin (MAINFRM'de). CPP:

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

*m_nPage* üye değişkenin (sınıf) `CMainFrame`değerini tanımladıktan sonra, bu teknik, uygulamanın diğer göstergeleri güncelleştirdiği şekilde boşta işleme sırasında sayfa numarasının bölmede görünmesine neden olur. *m_nPage* değişirse, bir sonraki boşalma döngüsü sırasında ekran değişir.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Kullanıcı arabirimi nesnelerinin güncellenmesi (program koşulları değiştikçe araç çubuğu düğmeleri ve menü öğeleri nasıl güncellenir)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Durum Çubuğu Uygulaması](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar Sınıfı](../mfc/reference/cstatusbar-class.md)
