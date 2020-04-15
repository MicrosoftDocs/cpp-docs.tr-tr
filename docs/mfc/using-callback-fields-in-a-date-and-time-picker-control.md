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
ms.openlocfilehash: 50350e51b6747d8c010db9d0dcaa9dff2e56e1f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366564"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Bir Tarih ve Saat Seçici Denetiminde Geri Çağrı Alanlarını Kullanma

Tarih ve saat seçici alanlarını tanımlayan standart biçim karakterlerine ek olarak, özel biçim dizesinin belirli bölümlerini geri arama alanları olarak belirterek çıktınızı özelleştirebilirsiniz. Geri arama alanını bildirmek için biçim dizesinin gövdesinde herhangi bir yere bir veya daha fazla "X" karakteri (ASCII Code 88) ekleyin. Örneğin, aşağıdaki dize "'Bugün: 'yy'/'MM'/'dd' (Gün 'X')'", tarih ve saat seçici denetiminin geçerli değeri ay, tarih ve son olarak yılın günü olarak izleyen yıl olarak görüntülemesine neden olur.

> [!NOTE]
> Geri arama alanındaki X sayısı, görüntülenecek karakter sayısına karşılık gelmez.

"X" karakterini yineleyerek özel bir dizedeki birden çok geri arama alanını ayırt edebilirsiniz. Böylece, biçim dizesi "XXddddMMMdd', "yyyXXX" iki benzersiz geri çağırma alanları, "XX" ve "XXX" içerir.

> [!NOTE]
> Geri arama alanları geçerli alanlar olarak kabul edilir, bu nedenle uygulamanızın bildirim iletileri DTN_WMKEYDOWN işlemek için hazır olması gerekir.

Tarih ve saat seçici denetiminizde geri arama alanlarının uygulanması üç bölümden oluşur:

- Özel biçim dizesini başlatma

- DTN_FORMATQUERY bildiriminin işlenmesi

- DTN_FORMAT bildiriminin işlenmesi

## <a name="initializing-the-custom-format-string"></a>Özel Biçim Dizesini Başlatma

Bir çağrı ile özel dize sini `CDateTimeCtrl::SetFormat`başlatma. Daha fazla bilgi için, [Tarih ve Zaman Seçici Denetiminde Özel Biçim Dizeleri Kullanma'ya](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)bakın. Özel biçim dizesini ayarlamak için `OnInitDialog` ortak bir yer, içeren `OnInitialUpdate` iletişim sınıfınızın veya içeren görünüm sınıfınızın işlevindedir.

## <a name="handling-the-dtn_formatquery-notification"></a>DTN_FORMATQUERY Bildiriminin İşletilmesi

Denetim biçim dizesini ayrışttığında ve bir geri arama alanıyla karşılaştığında, uygulama DTN_FORMAT ve DTN_FORMATQUERY bildirim iletileri gönderir. Geri arama alanı dizesi bildirimlere dahildir, böylece hangi geri arama alanının sorgulandığını belirleyebilirsiniz.

DTN_FORMATQUERY bildirimi, geçerli geri arama alanında görüntülenecek dize piksellerinde izin verilen maksimum boyutu almak için gönderilir.

Bu değeri düzgün hesaplamak için, denetimin görüntü yazı tipini kullanarak alanın yerine geçebilmek için dizeyüksekliği ve genişliğini hesaplamanız gerekir. String gerçek hesaplama [kolayca GetTextExtentPoint32](/windows/win32/api/wingdi/nf-wingdi-gettextextentpoint32w) Win32 işlevine bir çağrı ile elde edilir. Boyut belirlendikten sonra, değeri uygulamaya geri geçirin ve işleyici işlevinden çıkın.

Aşağıdaki örnek, geri arama dizesinin boyutunu sağlama yöntemidir:

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

Geçerli geri arama alanının boyutu hesaplandıktan sonra, alan için bir değer sağlamanız gerekir. Bu, DTN_FORMAT bildirimi için işleyicide yapılır.

## <a name="handling-the-dtn_format-notification"></a>DTN_FORMAT Bildiriminin İşletilmesi

DTN_FORMAT bildirimi yerine karakter dizesini istemek için uygulama tarafından kullanılır. Aşağıdaki örnek, olası bir yöntemi göstermektedir:

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
> **NMDATETIMEFORMAT** yapısına işaretçi, bildirim işleyicisinin ilk parametresini uygun türe atılarak bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
