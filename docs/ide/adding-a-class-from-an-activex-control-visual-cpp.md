---
title: (Visual C++) ActiveX denetiminden sınıf ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fd284236d2e9267d281061eef3915ed41f6f590
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375963"
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>ActiveX Denetiminden Sınıf Ekleme (Visual C++)

Kullanılabilir bir ActiveX denetimi bir arabirimde bir MFC sınıfı oluşturmak için bu sihirbazı kullanın. Bir MFC sınıfı için ekleyebileceğiniz bir [MFC uygulaması](../mfc/reference/creating-an-mfc-application.md), bir [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md), veya bir [MFC ActiveX denetimi](../mfc/reference/creating-an-mfc-activex-control.md).

> [!NOTE]
>  ActiveX denetiminden sınıf ekleme için etkinleştirilmiş Otomasyonu ile MFC projenizi oluşturmak gerekmez.

ActiveX denetimi Bileşen Nesne Modeli (çok çeşitli OLE işlevselliği destekleyen ve çok sayıda yazılım gereksinimlerini karşılayacak şekilde özelleştirilebilir COM) dayalı bir yeniden kullanılabilir yazılım bileşenidir. ActiveX denetimleri, sıradan bir ActiveX denetim kapsayıcıları hem Internet World Wide Web sayfalarında kullanmak için tasarlanmıştır.

### <a name="to-add-an-mfc-class-from-an-activex-control"></a>ActiveX denetiminden MFC sınıfı ekleme

1. Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), ActiveX denetim sınıfı eklemek istediğiniz proje adına sağ tıklayın.

1. Kısayol menüsünden tıklayın **Ekle**ve ardından **sınıfı Ekle**.

1. İçinde [sınıfı Ekle](../ide/add-class-dialog-box.md) Şablonlar bölmesinde, iletişim kutusu **ActiveX denetiminden MFC sınıfı**ve ardından **açık** görüntülenecek [activex'den sınıfı Ekle Denetim Sihirbazı](../ide/add-class-from-activex-control-wizard.md).

Sihirbazda, birden fazla ActiveX denetimi arabiriminde ekleyebilirsiniz. Benzer şekilde, tek bir sihirbaz oturumunda birden fazla ActiveX denetiminden sınıf oluşturabilirsiniz.

ActiveX denetimlerinde sisteminizdeki kayıtlı sınıfları ekleyebilirsiniz ya da ActiveX denetimlerinde ilk bunları sisteminizde kayıt olmadan tür kitaplığı dosyalarını (.tlb, .olb, .dll, .ocx veya .exe) içinde bulunan sınıfları ekleyebilirsiniz. Bkz: [kaydetme OLE denetimleri](../mfc/reference/registering-ole-controls.md) ActiveX denetimlerini kaydetme hakkında daha fazla bilgi.

MFC sınıfından türetilen bir sihirbaz [CWnd](../mfc/reference/cwnd-class.md) veya [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), seçilen ActiveX denetiminden eklediğiniz her arabirim için.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br>
[COM ve ATL’ye Giriş](../atl/introduction-to-com-and-atl.md)