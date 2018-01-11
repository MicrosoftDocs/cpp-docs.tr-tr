---
title: "Nasıl yapılır: COM bileşenlerini kullanacak yalıtılmış uygulamalar derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aaeef56f122d10f983313ab1c839db40f4e92aa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme
Yalıtılmış uygulamalar programa yerleşik bildirimleri sahip uygulamalardır. COM bileşenlerini kullanacak yalıtılmış uygulamalar oluşturabilirsiniz.  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>Yalıtılmış uygulamalar bildirimleri COM başvurular eklemek için  
  
1.  Yalıtılmış uygulama için proje özellik sayfalarını açın.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü genişletin ve ardından **bildirim aracı** düğümü.  
  
3.  Seçin **yalıtılmış COM** özellik sayfası olarak ayarlayın ve ardından **bileşen dosya adı** özelliğini kullanmak için yalıtılmış uygulama istediğiniz COM bileşeninin adına.  
  
4.  **Tamam**'ı tıklatın.  
  
### <a name="to-build-manifests-into-isolated-applications"></a>Bildirimleri yalıtılmış uygulamaları oluşturmak için  
  
1.  Yalıtılmış uygulama için proje özellik sayfalarını açın.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü genişletin ve ardından **bildirim aracı** düğümü.  
  
3.  Seçin **giriş ve çıkış** özellik sayfası olarak ayarlayın ve ardından **katıştırmak bildirim** özelliği eşit **Evet**.  
  
4.  **Tamam**'ı tıklatın.  
  
5.  Çözümü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar](http://msdn.microsoft.com/library/aa375190)   
 [Yan yana derlemeler hakkında](http://msdn.microsoft.com/library/ff951640)