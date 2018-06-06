---
title: COM arabirimini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.editing.interfaces
dev_langs:
- C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd7a61593a1024c00c0fd0de6bd62ff3ee9323b3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33338688"
---
# <a name="editing-a-com-interface"></a>COM Arabirimini Düzenleme
Sınıf Görünümü kısayol menüsünden komutlarını kullanarak Visual C++ projelerinde yeni yöntemlerini ve COM arabirimleri özelliklerini tanımlayabilirsiniz. Ayrıca, araç kutusu'ndan ActiveX denetimleri için olaylar tanımlayabilirsiniz.  
  
 ATL ve MFC tabanlı COM nesne sınıfları için sınıf uygulamasını arabirimi düzenlemek aynı zamanda düzenleyebilirsiniz.  
  
> [!NOTE]
>  Dışında tanımladığınız arabirimleri için **sınıfı Ekle** iletişim kutusu, Visual C++ .idl dosyanın özelliklerini ve yöntemlerini ekler ve arabirimler el ile eklense bile yöntemlerini uygulayan sınıflar için yer tutucular ekleyin.  
  
 Aşağıdaki üç sihirbazları varolan arabirimler özelleştirmenize yardımcı olur. Bunlar, sınıf görünümünden kullanılabilir:  
  
|Sihirbazı|Proje türü|  
|------------|------------------|  
|[Ekleme özelliği Sihirbazı](../ide/names-add-property-wizard.md)|ATL veya MFC destekleyen ATL projeleri Özellik eklemek istediğiniz bir arabirime sağ tıklayın.<br /><br /> Visual C++ proje türü algılar ve Özellik Ekleme Sihirbazı'nı seçeneklerinde buna uygun olarak değiştirir:<br /><br /> -İçin dispinterfaces kullanılarak oluşturulmuş projelerde [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md), Özellik Ekleme Sihirbazı'nı harekete, MFC için belirli seçenekleri sağlar.<br />-MFC ActiveX denetim arabirimleri için Özellik Ekleme Sihirbazı'nı stok yöntemleri ve sağlanan kullanması veya denetiminiz için özelleştirme özellikleri listesini sağlar.<br />-Diğer tüm arabirimler için ekleme özelliği sihirbazlar çoğu durumlarda yararlı seçenekleri sağlar.|  
|[Yöntem Ekleme Sihirbazı](../ide/add-method-wizard.md)|ATL veya MFC destekleyen ATL projeleri Yöntem eklemek istediğiniz bir arabirime sağ tıklayın.<br /><br /> Visual C++ proje türü algılar ve yöntem Ekleme Sihirbazı'nı seçeneklerinde buna uygun olarak değiştirir:<br /><br /> -İçin dispinterfaces kullanılarak oluşturulmuş projelerde [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md), yöntem Ekleme Sihirbazı'nı harekete, MFC için belirli seçenekleri sağlar.<br />-MFC ActiveX denetim arabirimleri için yöntem Ekleme Sihirbazı'nı stok yöntemleri ve sağlanan kullanması veya denetiminiz için özelleştirme özellikleri listesini sağlar.<br />-Diğer tüm arabirimler için **ekleme yöntemi** sihirbazlar çoğu durumlarda yararlı seçenekleri sağlar.|  
  
 Ayrıca, nesnenin control sınıfı Sınıf Görünümü'nde sağ tıklatıp, COM denetimi yeni arabirimleri uygulayabileceğiniz [arabirimini uygulayan](../ide/implement-interface-wizard.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları ile çalışma](../windows/working-with-resource-files.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)