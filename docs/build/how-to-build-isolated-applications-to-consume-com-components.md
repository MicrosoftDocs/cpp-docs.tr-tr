---
title: 'Nasıl yapılır: COM bileşenlerini kullanacak yalıtılmış uygulamalar derleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b94a41aef1122a507a8966c475b9a87c69e3789
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196838"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme
Yalıtılmış uygulamalar programa oluşturulan bildirimleri sahip uygulamalardır. COM bileşenlerini kullanacak yalıtılmış uygulamalar oluşturabilirsiniz.  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>Yalıtılmış uygulama bildirimlerinin COM başvuruları eklemek için  
  
1.  Yalıtılmış bir uygulama için proje özelliği sayfalarından açın.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü ve ardından **bildirim aracında** düğümü.  
  
3.  Seçin **yalıtılmış COM** özellik sayfası ve ardından **Bileşen dosyası adı** özelliğini kullanmak için yalıtılmış bir uygulama istediğiniz COM bileşeni adı.  
  
4.  **Tamam**'ı tıklatın.  
  
### <a name="to-build-manifests-into-isolated-applications"></a>Yalıtılmış uygulamalarınızı bildirimleri oluşturmak için  
  
1.  Yalıtılmış bir uygulama için proje özelliği sayfalarından açın.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü ve ardından **bildirim aracında** düğümü.  
  
3.  Seçin **giriş ve çıkış** özellik sayfası ve ardından **ekleme bildirimi** özelliği eşit **Evet**.  
  
4.  **Tamam**'ı tıklatın.  
  
5.  Çözümü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications)   
 [Yan yana derlemeler hakkında](/windows/desktop/SbsCs/about-side-by-side-assemblies-)