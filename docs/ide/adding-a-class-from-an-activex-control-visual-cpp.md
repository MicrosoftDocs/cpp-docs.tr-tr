---
title: "(Visual C++) ActiveX denetiminden sınıf ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f059396c91ddb51247347d10e6c8f79a6c95522f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>ActiveX Denetiminden Sınıf Ekleme (Visual C++)
Bir MFC sınıfı kullanılabilir ActiveX denetimindeki bir arabirim oluşturmak için bu sihirbazı kullanın. Bir MFC sınıfı ekleme bir [MFC uygulaması](../mfc/reference/creating-an-mfc-application.md), bir [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md), veya bir [MFC ActiveX denetimini](../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  ActiveX denetiminden sınıf eklemek için etkin otomasyon ile MFC projesi oluşturmak gerekmez.  
  
 ActiveX denetimi, Bileşen Nesne Modeli (çok çeşitli OLE işlevselliğini destekleyen ve çok sayıda yazılım gereksinimlerine uyacak şekilde özelleştirilmiş COM) dayalı bir yeniden kullanılabilir yazılım bileşenidir. ActiveX denetimleri, hem sıradan ActiveX denetimi kapsayıcıları ve World Wide Web sayfalarında Internet'te kullanımı için tasarlanmıştır.  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>ActiveX denetiminden bir MFC sınıfı ekleme  
  
1.  Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), ActiveX denetimi sınıfı eklemek istediğiniz proje adına sağ tıklayın.  
  
2.  Kısayol menüsünden tıklatın **Ekle**ve ardından **sınıfı Ekle**.  
  
3.  İçinde [sınıfı Ekle](../ide/add-class-dialog-box.md) Şablonlar bölmesinde iletişim kutusu **MFC ActiveX denetim sınıfından**ve ardından **açık** görüntülemek için [activex'den sınıfı Ekle Denetim Sihirbazı](../ide/add-class-from-activex-control-wizard.md).  
  
 Sihirbazda, birden fazla arabiriminde bir ActiveX denetimi ekleyebilirsiniz. Benzer şekilde, tek bir sihirbaz oturumunda birden fazla ActiveX denetiminden sınıfları oluşturabilirsiniz.  
  
 ActiveX denetimlerinde sisteminizde kayıtlı sınıfları ekleyebilir veya ilk bunları sisteminizde kaydettirmeden türü kitaplık dosyalarını (.tlb, .olb, .dll, .ocx veya .exe) bulunan ActiveX denetimlerinde sınıfları ekleyebilirsiniz. Bkz: [kaydetme OLE denetimleri](../mfc/reference/registering-ole-controls.md) ActiveX denetimlerini kaydetme hakkında daha fazla bilgi.  
  
 Türetilen bir MFC Sınıf Sihirbazı'nı oluşturur [CWnd](../mfc/reference/cwnd-class.md) veya [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), seçili ActiveX denetiminden eklediğiniz her bir arabirim için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [COM ve ATL’ye Giriş](../atl/introduction-to-com-and-atl.md)