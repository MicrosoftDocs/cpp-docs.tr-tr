---
title: Bir iletişim kutusu denetimleri ekleme neden olan iletişim kutusunun çalışmamasına neden | Microsoft Docs
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
ms.openlocfilehash: b10c24955e74d08ab570b5b694628f42bb394268
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>İletişim Kutusuna Denetimler Ekleme, İletişim Kutusunun Çalışmamasına Neden Oluyor
Bir iletişim kutusu için bir ortak denetimi veya zengin düzenleme denetimine ekledikten sonra bu iletişim kutusunu test ya da iletişim görüntülenmez görünmez.  
  
 **Sorun örneği**  
  
1.  Bir Windows uygulaması (konsol uygulaması değil) oluşturmak için uygulama ayarlarını değiştirerek bir Win32 projesi oluşturun.  
  
2.  İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına çift tıklayın.  
  
3.  İletişim seçeneği altında çift tıklayarak **hakkında** kutusu.  
  
4.  Ekleme bir **IP adresi denetimi** iletişim kutusu.  
  
5.  Kaydet ve **tüm yeniden**.  
  
6.  Programını çalıştırın.  
  
7.  İletişim kutusunun üzerinde **yardımcı** menüsünde tıklatın **hakkında** komut; hiçbir iletişim kutusu görüntülenir.  
  
 **Nedeni**  
  
 Şu anda, iletişim kutusu Düzenleyicisi otomatik olarak kod projenize aşağıdaki ortak denetimler sürükleyip veya zengin düzenleme denetimleri bir iletişim kutusu üzerine eklemez. Ne de bu sorun ortaya çıktığında Visual Studio bir hata veya uyarı sağlar. Kodu denetimi için el ile eklemeniz gerekir.  
  
||||  
|-|-|-|  
|Kaydırıcı denetimi|Ağaç denetimi|Tarih Saat Seçici|  
|Döndürme denetimi|Sekme denetimi|Ay takvim|  
|İlerleme denetimi|Animasyon denetimi|IP adresi denetimi|  
|Kısayol tuşu|Zengin düzenleme denetimi|Genişletilmiş Birleşik giriş kutusu|  
|Liste denetimi|Zengin düzenleme 2.0 denetimi|Özel Denetim|  
  
## <a name="the-fix-for-common-controls"></a>Ortak Denetimler için düzeltme  
 İletişim kutusunda ortak denetimleri kullanmak için çağırmanız gerekir [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) veya **AFXInitCommonControls** iletişim kutusu oluşturmadan önce.  
  
## <a name="the-fix-for-richedit-controls"></a>RichEdit denetimleri için düzeltme  
 Çağırmalısınız **LoadLibrary** zengin düzenleme denetimleri için. Daha fazla bilgi için bkz: [MFC ile RichEdit 1.0 denetimi kullanarak](../windows/using-the-richedit-1-0-control-with-mfc.md), [hakkında zengin düzenleme denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb787873) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)], ve [zengin düzenleme denetimine genel bakış](../mfc/overview-of-the-rich-edit-control.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu Düzenleyicisi sorunlarını giderme](../windows/troubleshooting-the-dialog-editor.md)   
 [İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

