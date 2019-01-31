---
title: (C++) iletişim kutusu Düzenleyicisi sorunlarını giderme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 21882868-5ac4-4a41-a4a6-eaaa059402ea
ms.openlocfilehash: fe0fe704b5c17d0db4e3419f29d21f0e60bc4211
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484961"
---
# <a name="troubleshooting-the-dialog-editor-c"></a>(C++) iletişim kutusu Düzenleyicisi sorunlarını giderme

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

Aşağıda birkaç sorun hangi olmanız gerekir C++ ile çalışırken duyarlı olan **iletişim** Düzenleyicisi:

## <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>Bir iletişim kutusuna denetimler ekleme iletişim kutusu artık işlev neden olur

Bir iletişim kutusu için bir ortak denetimi veya zengin düzenleme denetimi ekledikten sonra iletişim kutusunu test ya da iletişim görünmez görünmez.

### <a name="example-of-the-problem"></a>Sorun örneği

1. Bir Windows uygulaması (konsol uygulaması değil) oluşturmak için uygulama ayarları değiştirme bir Win32 projesi oluşturun.

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına çift tıklayın.

1. İletişim seçeneği altında çift **hakkında** kutusu.

1. Ekleme bir **IP adresi denetimi** iletişim kutusu.

1. Kaydet ve **tümünü yeniden derle**.

1. Programı çalıştırın.

1. İletişim kutusunun üzerinde **yardımcı** menüsünde tıklatın **hakkında** komut; hiçbir iletişim kutusu görüntülenir.

### <a name="the-cause"></a>Nedeni

Şu anda **iletişim** Düzenleyicisi değil otomatik olarak Ekle kod projenize aşağıdaki ortak denetimleri sürükleyip veya zengin düzenleme denetimleri üzerine bir iletişim kutusu. Ya da bu sorun ortaya çıktığında, Visual Studio bir hata veya uyarı sağlar. Sorunu gidermek için el ile denetim için kod ekleyin.

||||
|-|-|-|
|Kaydırıcı denetimi|Ağaç denetimi|Tarih Saat Seçici|
|Döndürme denetimi|Sekme denetimi|Aylık takvim|
|İlerleme denetimi|Animasyon denetimi|IP adresi denetimi|
|Kısayol tuşu|Zengin düzenleme denetimi|Genişletilmiş Birleşik giriş kutusu|
|Liste denetimi|Zengin düzenleme 2.0 denetimi|Özel Denetim|

### <a name="fix-for-common-controls"></a>Ortak denetimleri için düzeltme

İletişim kutusunda ortak denetimleri kullanmak için çağrı gerekir [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) veya `AFXInitCommonControls` iletişim kutusu oluşturmadan önce.

### <a name="fix-for-richedit-controls"></a>RichEdit denetimleri için düzeltme

Çağırmalısınız `LoadLibrary` zengin düzenleme denetimleri için. Daha fazla bilgi için [hakkında zengin düzenleme denetimleri](/windows/desktop/Controls/about-rich-edit-controls) Windows SDK ve [zengin düzenleme denetimine genel bakış](../mfc/overview-of-the-rich-edit-control.md).

### <a name="requirements"></a>Gereksinimler

Win32

## <a name="using-the-richedit-10-control-with-mfc"></a>MFC ile RichEdit 1.0 Denetimini Kullanma

RichEdit denetimini kullanmak için öncelikle çağırmalısınız [Afxınitrichedit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 denetimi (RICHED20. yüklemek için DLL) veya çağrı [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) eski RichEdit 1.0 denetimini (RICHED32. yüklemek için DLL).

Geçerli kullanabilir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) eski RichEdit 1.0 denetimi sınıfıyla ancak `CRichEditCtrl` yalnızca 2.0 RichEdit denetimini desteklemek için tasarlanmıştır. RichEdit 1.0 ve 2.0 RichEdit benzer olduğundan, çoğu yöntemleri çalışır. Ancak, bazı yöntemler yanlış çalışmasına veya hiç çalışmıyor 1.0 ve 2.0 denetimlerini arasında bazı farklar vardır unutmayın.

### <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)