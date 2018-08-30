---
title: 'Nasıl yapılır: kayıt gerektirmeyen COM bileşenlerini derleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eaf9417f4d2b3b825933589556055772b84e057
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197419"
---
# <a name="how-to-build-registration-free-com-components"></a>Nasıl Yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme
Kayıt gerektirmeyen COM bileşenlerini DLL'lere oluşturulan bildirimleri sahip bir COM bileşenlerdir.  
  
### <a name="to-build-manifests-into-com-components"></a>COM bileşenlerine bildirimleri oluşturmak için  
  
1.  COM bileşeni için proje özelliği sayfalarından açın.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü ve ardından **bildirim aracında** düğümü.  
  
3.  Seçin **giriş ve çıkış** özellik sayfası ve ardından **ekleme bildirimi** özelliği eşit **Evet**.  
  
4.  **Tamam**'ı tıklatın.  
  
5.  Çözümü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications)   
 [Yan yana derlemeler hakkında](/windows/desktop/SbsCs/about-side-by-side-assemblies-)   
 [Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../build/how-to-build-isolated-applications-to-consume-com-components.md)