---
title: İletişim kutusuna denetimler ekleme, iletişim kutusunun çalışmamasına neden oluyor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], troubleshooting
- common controls, troubleshooting
- troubleshooting controls
- dialog boxes, troubleshooting
- dialog box controls, troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d27c12b491fc5f05da58a84703ea13e84e9e9c6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215376"
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>İletişim Kutusuna Denetimler Ekleme, İletişim Kutusunun Çalışmamasına Neden Oluyor

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

[İletişim Kutusu Düzenleyicisinde Sorun Giderme](../windows/troubleshooting-the-dialog-editor.md)  
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)