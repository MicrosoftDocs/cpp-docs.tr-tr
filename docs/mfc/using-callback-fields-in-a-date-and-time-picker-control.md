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
ms.openlocfilehash: 874f73df3dda3a720d4346ae3fb0136c662221db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299406"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Bir Tarih ve Saat Seçici Denetiminde Geri Çağrı Alanlarını Kullanma

Tarih ve Saat Seçici alanlarını tanımlayan standart biçim karakterleri ek olarak, bir özel biçim dizesinde belirli bölümlerini geri arama alanları belirterek çıkışınızı özelleştirebilirsiniz. Bir veya daha fazla "X" karakterleri (ASCII kodu 88) geri çağırma alanı bildirmek için herhangi bir biçim dizesi gövdesinde içerir. Örneğin, aşağıdaki dize "' Bugün: 'yy' / 'MM' / 'dd' (Günlük 'X')'" olarak yıl, ay, tarih yılın gününü son ardından ve geçerli değerini görüntülemek tarih ve Saat Seçici denetimini neden olur.

> [!NOTE]
>  Sayısını X'lerin içinde bir geri çağırma alanı görüntülenecek karakter sayısına karşılık gelmiyor.

"X" karakteri yineleyerek özel bir dize içinde birden fazla geri çağrı alanlarını ayırt edebilirsiniz. Bu nedenle, Biçim dizesinde "XXddddMMMdd', ' yyyXXX", "XX" ve "XXX" iki benzersiz bir geri arama alanları içerir.

> [!NOTE]
>  Geri arama alanları, uygulamanızın DTN_WMKEYDOWN bildirim iletilerini işlemek için hazırlanması gerekir böylece geçerli alanları olarak kabul edilir.

Tarih ve Saat Seçici denetiminde geri çağrı alanlarını uygulama, üç bölümden oluşur:

- Özel biçim dizesi başlatılıyor

- DTN_FORMATQUERY bildirimi işleme

- DTN_FORMAT bildirimi işleme

## <a name="initializing-the-custom-format-string"></a>Özel biçim dizesi başlatılıyor

Özel bir dize ile çağrı başlatmak `CDateTimeCtrl::SetFormat`. Daha fazla bilgi için [kullanarak özel biçim dizeleri bir tarih ve Saat Seçici denetiminin](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Özel biçim dizesi ayarlamak için bir ortak konum `OnInitDialog` işlevi içeren iletişim sınıfınızın veya `OnInitialUpdate` işlevi içeren, görünüm sınıfı.

## <a name="handling-the-dtnformatquery-notification"></a>DTN_FORMATQUERY bildirimi işleme

Denetim biçim dizesini ayrıştırmak ve bir geri çağırma alanı karşılaştığı uygulama DTN_FORMAT ve DTN_FORMATQUERY bildirimi iletileri gönderir. Geri çağırma alanı sorgulanan belirlemek için geri çağırma alanı dize ile bildirimleri dahildir.

DTN_FORMATQUERY bildirimi, izin verilen en büyük boyutu geçerli bir geri çağırma alanında gösterilecek dizeyi piksel almak için gönderilir.

Bu değeri doğru hesaplamak için denetimin görünen yazı tipi kullanarak yükseklik ve genişlik alan için değiştirilecek dizenin karşılaştırılmalıdır. Dizenin gerçek olan hesaplamayı çağrısı ile kolayca elde [GetTextExtentPoint32](/windows/desktop/api/wingdi/nf-wingdi-gettextextentpoint32a) Win32 işlevi. Boyutu belirlendikten sonra uygulamaya değeri geçirin ve işleyici işlevi çıkın.

Aşağıdaki örnekte geri çağırma dize boyutu sağlayan bir yöntemdir:

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

Geçerli geri çağırma alanı boyut hesaplanmadı sonra alan için değer sağlamanız gerekir. Bu işleyici DTN_FORMAT bildirimi için gerçekleştirilir.

## <a name="handling-the-dtnformat-notification"></a>DTN_FORMAT bildirimi işleme

DTN_FORMAT bildirimi, uygulama tarafından kullanılacak karakter dizesi istemek için kullanılır. Aşağıdaki örnek, olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  İşaretçi **NMDATETIMEFORMAT** yapısı uygun türde bildirim işleyicisine ilk parametresi atayarak bulundu.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
