---
title: Bir tarih ve Saat Seçici geri çağrı alanlarını kullanma Denetim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b0d59aa8c30e9308448467bb198e898106e61f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383792"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Bir Tarih ve Saat Seçici Denetiminde Geri Çağrı Alanlarını Kullanma
Tarih ve Saat Seçici alanlarını tanımlayan standart biçimi karakterler ek olarak, özel bir biçim dizesi belirli bölümlerini geri arama alanları belirterek, çıktı özelleştirebilirsiniz. Bir geri çağırma alanı bildirmek için bir veya daha fazla "X" karakter (ASCII kodu 88) herhangi bir yere biçim dizesi gövdesinde içerir. Örneğin, aşağıdaki dizeyi "' Bugün: 'yy' / 'MM' / 'dd' (gün 'X')'" ay, tarih ve yılın günü tarafından son ardından yıl geçerli değerini görüntülemek tarih ve Saat Seçici denetimini neden olur.  
  
> [!NOTE]
>  Sayısı X'lerin çağırma işleminde görüntülenecek olan karakter sayısı için alan karşılık gelmiyor.  
  
 Birden çok geri arama alanları "X" karakter yineleyerek özel bir dize ayırt edebilirsiniz. Bu nedenle, biçim dizesi "XXddddMMMdd', ' yyyXXX", "XX" ve "XXX" iki benzersiz geri arama alanları içerir.  
  
> [!NOTE]
>  Geri arama alanları uygulamanızı işlemek için hazırlanması gerekir böylece geçerli alanlar olarak kabul edilir **DTN_WMKEYDOWN** bildirim iletileri.  
  
 Tarih ve Saat Seçici denetiminde geri çağrı alanlarını uygulama üç bölümden oluşur:  
  
-   Özel biçim dizesi başlatılıyor  
  
-   İşleme **DTN_FORMATQUERY** bildirim  
  
-   İşleme **DTN_FORMAT** bildirim  
  
## <a name="initializing-the-custom-format-string"></a>Özel biçim dizesi başlatılıyor  
 Özel bir dize çağrısıyla başlatma `CDateTimeCtrl::SetFormat`. Daha fazla bilgi için bkz: [kullanarak özel biçim dizeleri tarih ve Saat Seçici denetimini](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Özel biçim dizesine ayarlamak için bir ortak yerdir `OnInitDialog` içeren iletişim sınıfınızı işlevinin veya `OnInitialUpdate` içeren görünüm sınıfınızın işlevi.  
  
## <a name="handling-the-dtnformatquery-notification"></a>DTN_FORMATQUERY bildirimi işleme  
 Denetim biçim dizesi ayrıştırır ve bir geri çağırma alan karşılaştığında, uygulamanın gönderdiği **DTN_FORMAT** ve **DTN_FORMATQUERY** bildirim iletileri. Geri arama alanı sorgulanan belirlemek için geri çağırma alan dize bildirimlerle dahil edilir.  
  
 **DTN_FORMATQUERY** bildirim geçerli bir geri çağırma alanında görüntülenen dizesinin piksel cinsinden izin verilen boyut sınırı almak için gönderilir.  
  
 Bu değer doğru hesaplamak için yüksekliğini ve genişliğini alan için değiştirilecek bu dizenin denetimin görüntüleme yazı tipi kullanarak hesaplayabilirsiniz gerekir. Dizenin gerçek hesaplama kolayca çağrısıyla elde [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938) Win32 işlevi. Boyutu belirlendikten sonra uygulama için değer geçirin ve işleyici işlevi çıkın.  
  
 Aşağıdaki örnek geri çağırma dize boyutu sağlayarak, bir yöntemdir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 Geçerli geri çağırma alan boyutu hesaplanan sonra alan için bir değer sağlamanız gerekir. Bu işleyicisindeki yapılır **DTN_FORMAT** bildirim.  
  
## <a name="handling-the-dtnformat-notification"></a>DTN_FORMAT bildirimi işleme  
 **DTN_FORMAT** bildirim değiştirilecektir karakter dizesi istemek için uygulama tarafından kullanılır. Aşağıdaki örnek, olası bir yöntemi gösterir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  İşaretçi **NMDATETIMEFORMAT** yapısına uygun türde bildirim işleyicisine ilk parametresi atama tarafından bulundu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

