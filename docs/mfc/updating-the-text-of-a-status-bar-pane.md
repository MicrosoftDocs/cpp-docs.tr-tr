---
description: 'Hakkında daha fazla bilgi edinin: Status-Bar bölmesinin metnini güncelleştirme'
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
ms.openlocfilehash: 2c3a922072fe117719c1cea803b16ca9c998ce1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263731"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Durum Çubuğu Bölmesinin Metnini Güncelleştirme

Bu makalede, bir MFC durum çubuğu bölmesinde görünen metnin nasıl değiştirileceği açıklanır. Bir durum çubuğu — [CStatusBar](../mfc/reference/cstatusbar-class.md) sınıfının bir pencere nesnesi — birkaç "bölme" içerir. Her bölme, durum çubuğunun bilgileri göstermek için kullanabileceğiniz dikdörtgen bir alandır. Örneğin, birçok uygulama, en sağdaki bölmelerde Caps Lock, NUM LOCK ve diğer anahtarların durumunu görüntüler. Uygulamalar genellikle, "ileti bölmesi" olarak da adlandırılan en sol bölmede (bölme 0) bilgilendirici metin görüntüler. Örneğin, varsayılan MFC durum çubuğu şu anda seçili olan menü öğesini veya araç çubuğu düğmesini açıklayan bir dizeyi göstermek için ileti bölmesini kullanır. [Durum çubuklarındaki](../mfc/status-bar-implementation-in-mfc.md) şekil, uygulama Sihirbazı tarafından oluşturulan MFC uygulamasından bir durum çubuğu gösterir.

Varsayılan olarak, MFC `CStatusBar` bölmesi oluşturduğunda bir bölmeyi etkinleştirmez. Bir bölmeyi etkinleştirmek için, durum çubuğundaki her bölme için ON_UPDATE_COMMAND_UI makrosunu kullanmanız ve bölmeleri güncelleştirmeniz gerekir. Bölmeler WM_COMMAND iletileri göndermediğinden (araç çubuğu düğmeleri gibi), kodu el ile yazmanız gerekir.

Örneğin, bir bölmenin `ID_INDICATOR_PAGE` komut tanımlayıcısı olarak olduğunu ve bir belgedeki geçerli sayfa numarasını içerdiğini varsayalım. Aşağıdaki yordamda durum çubuğunda yeni bir bölmenin nasıl oluşturulacağı açıklanmaktadır.

### <a name="to-make-a-new-pane"></a>Yeni bir bölme oluşturmak için

1. Bölmenin komut KIMLIĞINI tanımlayın.

   **Görünüm** menüsünde **kaynak görünümü**' a tıklayın. Proje kaynağına sağ tıklayın ve **kaynak sembolleri**' ne tıklayın. Kaynak sembolleri iletişim kutusunda, öğesine tıklayın `New` . Bir komut KIMLIĞI adı yazın: Örneğin, `ID_INDICATOR_PAGE` . KIMLIK için bir değer belirtin veya kaynak sembolleri iletişim kutusu tarafından önerilen değeri kabul edin. Örneğin, için `ID_INDICATOR_PAGE` varsayılan değeri kabul edin. Kaynak sembolleri iletişim kutusunu kapatın.

1. Bölmede görüntülenecek bir varsayılan dize tanımlayın.

   Kaynak Görünümü açıkken, uygulamanız için kaynak türlerini listeleyen pencerede **dize tablosuna** çift tıklayın. **Dize tablosu** Düzenleyicisi açıkken, **Ekle** menüsünden **Yeni dize** ' yi seçin. Bölmesin komut KIMLIĞINI (örneğin,) seçin `ID_INDICATOR_PAGE` ve "sayfa" gibi bir varsayılan dize değeri yazın. Dize düzenleyicisini kapatın. (Derleyici hatasından kaçınmak için varsayılan bir dizeye ihtiyacınız vardır.)

1. Bölmeyi *göstergeler* dizisine ekleyin.

   Dosya MAINFRM ' de. CPP, *göstergeler* dizisini bulun. Bu dizi, soldan sağa sırayla tüm durum çubuğu göstergelerinin komut kimliklerini listeler. Dizideki uygun noktada, aşağıdaki gibi, bölmesinin komut KIMLIĞINI aşağıda gösterildiği gibi girin `ID_INDICATOR_PAGE` :

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

Bir bölmede metin görüntülemenin önerilen yolu, `SetText` `CCmdUI` bölmesi için bir Update Handler işlevinde sınıfının üye işlevini çağırmanız olur. Örneğin, geçerli sayfa numarasını içeren *m_nPage* bir tamsayı değişkeni ayarlamak ve `SetText` bölmenin metnini bu sayının dize sürümüne ayarlamak için kullanmak isteyebilirsiniz.

> [!NOTE]
> `SetText`Yaklaşım önerilir. Üye işlevini çağırarak bu görevi biraz daha düşük bir düzeyde gerçekleştirmek mümkündür `CStatusBar` `SetPaneText` . Bu nedenle, yine de bir güncelleştirme işleyicisine ihtiyacınız vardır. Pano için böyle bir işleyici olmadan, MFC otomatik olarak bölmesini devre dışı bırakır ve içeriğini siliyor.

Aşağıdaki yordamda, bir bölmede metin göstermek için bir güncelleştirme işleyici işlevinin nasıl kullanılacağı gösterilmektedir.

#### <a name="to-make-a-pane-display-text"></a>Bir bölmeyi görüntüleme metni

1. Komut için bir komut güncelleştirme işleyicisi ekleyin.

   İçin burada gösterildiği gibi, işleyici için el ile bir prototip ekleyin `ID_INDICATOR_PAGE` (MAINFRM içinde). H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. Uygun. CPP dosyası için burada gösterildiği gibi işleyicinin tanımını ekleyin `ID_INDICATOR_PAGE` (MAINFRM içinde). CPP):

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   Bu işleyicinin son üç satırı, metninizi görüntüleyen koddur.

1. Uygun ileti eşlemesinde, için burada gösterildiği gibi ON_UPDATE_COMMAND_UI makrosunu ekleyin `ID_INDICATOR_PAGE` (MAINFRM içinde). CPP):

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

*M_nPage* üye değişkeninin değerini tanımladıktan sonra `CMainFrame` , bu yöntem, boş işlem sırasında uygulamanın diğer göstergeleri güncelleştirmesiyle aynı şekilde, sayfa numarasının panelde görünmesine neden olur. *M_nPage* değişirse, bir sonraki boşta döngüsü sırasında görüntü değişir.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Kullanıcı arabirimi nesnelerini güncelleştirme (araç çubuğu düğmelerini ve menü öğelerini program koşulları değişikliği olarak güncelleştirme)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de durum çubuğu uygulama](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar sınıfı](../mfc/reference/cstatusbar-class.md)
