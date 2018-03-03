---
title: "Nasıl yapılır: kayıt gerektirmeyen COM bileşenlerini derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 018a3ba707f4c5cff73b5a5c54f82400a79a8d46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../build/how-to-build-isolated-applications-to-consume-com-components.md)