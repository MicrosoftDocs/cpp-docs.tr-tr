---
title: 'Nasıl Yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme'
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 4f4ebf121b761c37969fa3f9788bda52d913f340
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463537"
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