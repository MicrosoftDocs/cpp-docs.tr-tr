---
title: Bir Tarih ve Saat Seçici Denetiminde Geri Çağrı Alanlarını Kullanma
ms.date: 11/04/2016
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
ms.openlocfilehash: 5d08c349253e62c15553cfa0452cee930b1a1876
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513511"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Bir Tarih ve Saat Seçici Denetiminde Geri Çağrı Alanlarını Kullanma

Tarih ve saat seçici alanlarını tanımlayan standart biçim karakterlerinin yanı sıra, özel biçim dizesinin belirli parçalarını geri arama alanları olarak belirterek çıktlarınızı özelleştirebilirsiniz. Bir geri arama alanı bildirmek için, biçim dizesinin gövdesinde herhangi bir yere bir veya daha fazla "X" karakteri (ASCII kodu 88) ekleyin. Örneğin, bugün şu "' dizesi: ' yy '/' AA '/' gg ' (gün ' X ') '", tarih ve saat seçici denetiminin geçerli değeri yıl, tarih ve son olarak yılın gününde görüntülemesine neden olur.

> [!NOTE]
>  Bir geri çağırma alanındaki X sayısı, görüntülenecek karakter sayısına karşılık gelmiyor.

"X" karakterini yineleyerek özel bir dizedeki birden fazla geri çağırma alanı arasında ayrım yapabilirsiniz. Bu nedenle, "XXddddMMMdd", ' yyyXXX "biçim dizesi," XX "ve" XXX "adlı iki benzersiz geri arama alanı içerir.

> [!NOTE]
>  Geri çağırma alanları geçerli alan olarak değerlendirilir, bu nedenle uygulamanızın DTN_WMKEYDOWN Notification iletilerini işlemeye hazır olması gerekir.

Tarih ve saat seçici denetiişinizde geri çağırma alanları uygulamak üç bölümden oluşur:

- Özel biçim dizesi başlatılıyor

- DTN_FORMATQUERY bildirimini işleme

- DTN_FORMAT bildirimini işleme

## <a name="initializing-the-custom-format-string"></a>Özel biçim dizesi başlatılıyor

Özel dizeyi öğesine `CDateTimeCtrl::SetFormat`çağrısıyla başlatın. Daha fazla bilgi için bkz. [Tarih ve saat seçici denetiminde özel biçim dizeleri kullanma](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Özel biçim dizesini `OnInitDialog` ayarlamak için ortak bir yer, içeren bir iletişim sınıfınızın veya `OnInitialUpdate` içeren Görünüm sınıfınızın işlevinizin işlevidir.

## <a name="handling-the-dtn_formatquery-notification"></a>DTN_FORMATQUERY bildirimini işleme

Denetim, biçim dizesini ayrıştırır ve bir geri çağırma alanıyla karşılaştığında, uygulama DTN_FORMAT ve DTN_FORMATQUERY bildirim iletileri gönderir. Geri çağırma alanı dizesi bildirimlere dahildir, böylece hangi geri çağırma alanının sorgulandığını belirleyebilirsiniz.

DTN_FORMATQUERY bildirimi, geçerli geri arama alanında görüntülenecek olan dizenin piksel olarak izin verilen en büyük boyutunu almak için gönderilir.

Bu değeri doğru bir şekilde hesaplamak için, denetimin görüntüleme yazı tipini kullanarak, alan için yerine kullanılacak dizenin yüksekliğini ve genişliğini hesaplamanız gerekir. Dizenin gerçek hesaplamasına, [GetTextExtentPoint32](/windows/win32/api/wingdi/nf-wingdi-gettextextentpoint32w) Win32 işlevine yapılan bir çağrıyla kolayca ulaşılır. Boyut belirlendikten sonra, değeri uygulamaya geri geçirin ve işleyici işlevinden çıkın.

Aşağıdaki örnek, geri çağırma dizesinin boyutunu sağlamanın bir yöntemidir:

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

Geçerli geri çağırma alanının boyutu hesaplandıktan sonra alan için bir değer belirtmeniz gerekir. Bu, DTN_FORMAT bildirimi için işleyicide yapılır.

## <a name="handling-the-dtn_format-notification"></a>DTN_FORMAT bildirimini işleme

DTN_FORMAT bildirimi, uygulama tarafından değiştirilecek karakter dizesini istemek için kullanılır. Aşağıdaki örnek, olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  **Nmdatetimeformat** yapısına yönelik işaretçi, bildirim işleyicisinin ilk parametresi doğru türe ayarlandığında bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
