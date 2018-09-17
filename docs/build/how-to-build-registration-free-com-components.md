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
ms.openlocfilehash: e0a9e1769ff0ba9a0589f9d59c3d1f1ed2fc5bcb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699861"
---
# <a name="how-to-build-registration-free-com-components"></a>Nasıl Yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme

Kayıt gerektirmeyen COM bileşenlerini DLL'lere oluşturulan bildirimleri sahip bir COM bileşenlerdir.

### <a name="to-build-manifests-into-com-components"></a>COM bileşenlerine bildirimleri oluşturmak için

1. COM bileşeni için proje özelliği sayfalarından açın.

1. Genişletin **yapılandırma özellikleri** düğümünü ve ardından **bildirim aracında** düğümü.

1. Seçin **giriş ve çıkış** özellik sayfası ve ardından **ekleme bildirimi** özelliği eşit **Evet**.

1. **Tamam**'ı tıklatın.

1. Çözümü oluşturun.

## <a name="see-also"></a>Ayrıca Bkz.

[Yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications)<br/>
[Yan yana derlemeler hakkında](/windows/desktop/SbsCs/about-side-by-side-assemblies-)<br/>
[Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../build/how-to-build-isolated-applications-to-consume-com-components.md)