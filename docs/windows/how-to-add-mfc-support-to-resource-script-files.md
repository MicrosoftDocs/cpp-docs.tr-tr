---
title: "Nasıl yapılır: kaynak betik dosyalarına MFC desteği ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.resvw.add.MFC
dev_langs: C++
helpviewer_keywords:
- rc files, adding MFC support
- .rc files, adding MFC support
- MFC, adding support to resource scripts files
- resource script files, adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1d931c1309d583b8904afa403130411e495e0408
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-add-mfc-support-to-resource-script-files"></a>Nasıl Yapılır: Kaynak Betik Dosyalarına MFC Desteği Ekleme
Normalde, Windows kullanarak bir MFC uygulaması oluşturduğunuzda [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md), Microsoft Foundation çekirdek özelliklerini içeren temel bir kümesi (bir kaynak (.rc) komut dosyası dahil olmak üzere) dosyaları sihirbaz oluşturur sınıfları (MFC). MFC dayalı olmayan bir Windows uygulaması için bir .rc dosyası düzenliyorsanız, ancak, MFC çerçevesi belirli aşağıdaki özellikler kullanılabilir değil:  
  
-   MFC kodu sihirbazlar (daha önce adı "[MFC ClassWizard](http://msdn.microsoft.com/en-us/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)")  
  
-   Menü komut istemi dizeleri  
  
-   Birleşik giriş kutusu denetimleri için içeriğini listele  
  
-   ActiveX denetimi barındırma  
  
 Ancak, bunu olmayan mevcut .rc dosyaları için MFC desteği ekleyebilirsiniz.  
  
### <a name="to-add-mfc-support-to-rc-files"></a>.Rc dosyaları için MFC desteği ekleme  
  
1.  Kaynak betik dosyasını açın.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde [kaynak görünümü](../windows/resource-view-window.md), Kaynaklar klasörünü (örneğin, MFC.rc) vurgulayın.  
  
3.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window)ayarlayın **MFC modu** özelliğine **doğru**.  
  
    > [!NOTE]
    >  Bu bayrağını ayarlamanın yanı sıra .rc dosyası bir MFC projesine bir parçası olmalıdır. Örneğin, yalnızca ayarlama **MFC modu** için **True** Win32 .rc dosyasında üzerinde proje MFC özelliklerinden herhangi birini size olmaz.  
  

  
 **Gereksinimler**  
  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak düzenleyicileri](../windows/resource-editors.md)