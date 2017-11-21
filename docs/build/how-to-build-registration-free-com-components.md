---
title: "Nasıl yapılır: kayıt gerektirmeyen COM bileşenlerini derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bba711f88a53a3d9b6f9eae1faed09670e95d497
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-build-registration-free-com-components"></a>Nasıl Yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme
Kayıtsız COM bileşenlerini bildirimleri DLL'leri içinde yerleşik olan COM bileşenleridir.  
  
### <a name="to-build-manifests-into-com-components"></a>COM bileşenlerine bildirimleri oluşturmak için  
  
1.  COM bileşeni için proje özellik sayfalarını açın.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü genişletin ve ardından **bildirim aracı** düğümü.  
  
3.  Seçin **giriş ve çıkış** özellik sayfası olarak ayarlayın ve ardından **katıştırmak bildirim** özelliği eşit **Evet**.  
  
4.  **Tamam**'ı tıklatın.  
  
5.  Çözümü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar](http://msdn.microsoft.com/library/aa375190)   
 [Yan yana derlemeler hakkında](http://msdn.microsoft.com/library/ff951640)   
 [Nasıl yapılır: COM bileşenlerini kullanacak yalıtılmış uygulamalar oluşturma](../build/how-to-build-isolated-applications-to-consume-com-components.md)