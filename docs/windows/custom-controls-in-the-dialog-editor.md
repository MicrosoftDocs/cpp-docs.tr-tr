---
title: "Özel denetimler iletişim kutusu Düzenleyicisi'nde | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Custom Control
dev_langs: C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [Visual Studio], dialog boxes
- custom controls [Visual Studio]
- dialog box controls, custom (user) controls
- Dialog editor, custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c507f4d252100055d4ed7f24e9c407bf8edb82d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="custom-controls-in-the-dialog-editor"></a>İletişim Kutusu Düzenleyicisindeki Özel Denetimler
İletişim kutusu Düzenleyicisi kullan "özel" var olan veya bir iletişim kutusu şablonunda "kullanıcı" denetimleri sağlar.  
  
> [!NOTE]
>  ActiveX denetimleri ile karıştırılmamalıdır bu bağlamdaki özel denetimleri bulunur. ActiveX denetimleri bazen OLE özel denetimler adı veriliyordu. Ayrıca, bu denetimlerin Windows sahip tarafından çizilmiş denetimleri ile karıştırmayın.  
  
 Bu işlev, bu Windows tarafından sağlanan dışında denetimleri kullanmanıza olanak tanır için tasarlanmıştır. Çalışma zamanında denetim bir pencere sınıfı (aynı C++ sınıfı) ile ilişkilidir. Aynı görevi gerçekleştirmenin daha yaygın bir yolu, iletişim kutusunda statik bir denetimi gibi herhangi bir denetimi yüklemektir. Ardından çalışma zamanında, buna [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlev, bu denetim kaldırın ve kendi özel denetimi ile değiştirin.  
  
 Bu eski bir tekniktir. Günümüzde çoğu durumda bir ActiveX denetimi veya alt Windows yaygın bir denetim yazmak için önerilir.  
  
 Bu özel denetimler için sınırlı şunlardır:  
  
-   Konum iletişim kutusunda ayar.  
  
-   Bir başlık yazın.  
  
-   (Uygulama kodunuz denetimi bu ada göre kaydetmeniz gerekir) denetimin Windows sınıfın adını tanımlama.  
  
-   Denetimin stilini ayarlar bir 32 bit onaltılık değer yazma.  
  
-   Genişletilmiş stili ayarlanıyor.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)

