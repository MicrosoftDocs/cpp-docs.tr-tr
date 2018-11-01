---
title: Bir iletişim kutusuna denetimler ekleme iletişim bundan böyle işlevi (C++) neden olur
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
ms.openlocfilehash: d95c89c0a07e02ab0934a54ca1fe067961348766
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648298"
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function-c"></a>Bir iletişim kutusuna denetimler ekleme iletişim bundan böyle işlevi (C++) neden olur

Bir iletişim kutusu için bir ortak denetimi veya zengin düzenleme denetimi ekledikten sonra bu iletişim kutusunu test ya da iletişim görüntülenmez görünmez.

### <a name="example-of-the-problem"></a>Sorun örneği

1. Bir Windows uygulaması (konsol uygulaması değil) oluşturmak için uygulama ayarları değiştirme bir Win32 projesi oluşturun.

2. İçinde [kaynak görünümü](../windows/resource-view-window.md), üzerinde .rc dosyasına çift tıklayın.

3. İletişim seçeneği altında çift tıklayın **hakkında** kutusu.

4. Ekleme bir **IP adresi denetimi** iletişim kutusu.

5. Kaydet ve **tümünü yeniden derle**.

6. Programı çalıştırın.

7. İletişim kutusunun üzerinde **yardımcı** menüsünde tıklatın **hakkında** komut; hiçbir iletişim kutusu görüntülenir.

### <a name="the-cause"></a>Nedeni

Şu anda, iletişim kutusu düzenleyicisinde otomatik olarak kod projenize aşağıdaki ortak denetimleri sürükleyip veya zengin düzenleme denetimleri bir iletişim kutusu üzerine eklemez. Ya da bu sorun ortaya çıktığında, Visual Studio bir hata veya uyarı sağlar. Denetimin kodunu el ile eklemeniz gerekir.

||||
|-|-|-|
|Kaydırıcı denetimi|Ağaç denetimi|Tarih Saat Seçici|
|Döndürme denetimi|Sekme denetimi|Aylık takvim|
|İlerleme denetimi|Animasyon denetimi|IP adresi denetimi|
|Kısayol tuşu|Zengin düzenleme denetimi|Genişletilmiş Birleşik giriş kutusu|
|Liste denetimi|Zengin düzenleme 2.0 denetimi|Özel Denetim|

## <a name="the-fix-for-common-controls"></a>Ortak denetimleri için düzeltme

İletişim kutusunda ortak denetimleri kullanmak için çağırmanız gerekir [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) veya `AFXInitCommonControls` iletişim kutusu oluşturmadan önce.

## <a name="the-fix-for-richedit-controls"></a>RichEdit denetimleri için düzeltme

Çağırmalısınız `LoadLibrary` zengin düzenleme denetimleri için. Daha fazla bilgi için [MFC ile RichEdit 1.0 denetimini kullanma](../windows/using-the-richedit-1-0-control-with-mfc.md), [hakkında zengin düzenleme denetimleri](/windows/desktop/Controls/about-rich-edit-controls) Windows SDK ve [zengin düzenleme denetimine genel bakış](../mfc/overview-of-the-rich-edit-control.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisinde Sorun Giderme](../windows/troubleshooting-the-dialog-editor.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)