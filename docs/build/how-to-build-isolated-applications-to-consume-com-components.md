---
description: 'Şu konuda daha fazla bilgi edinin: nasıl yapılır: COM bileşenlerini kullanmak için yalıtılmış uygulamalar oluşturma'
title: 'Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 31a54683974b8539724ecee24aa45917674a6e82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156391"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme

Yalıtılmış uygulamalar, programa yerleşik bildirimleri olan uygulamalardır. COM bileşenlerini kullanmak için yalıtılmış uygulamalar oluşturabilirsiniz.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>Yalıtılmış uygulamaların bildirimlerine COM başvuruları eklemek için

1. Yalıtılmış uygulama için proje özelliği sayfalarını açın.

1. **Yapılandırma özellikleri** düğümünü genişletin ve ardından **bildirim aracı** düğümünü genişletin.

1. **YALıTıLMıŞ com** özellik sayfasını seçin ve ardından **Bileşen dosya adı** özelliğini YALıTıLMıŞ uygulamanın kullanmasını istediğiniz com bileşeni adına ayarlayın.

1. **Tamam** düğmesine tıklayın.

### <a name="to-build-manifests-into-isolated-applications"></a>Yalıtılmış uygulamalarda bildirim oluşturmak için

1. Yalıtılmış uygulama için proje özelliği sayfalarını açın.

1. **Yapılandırma özellikleri** düğümünü genişletin ve ardından **bildirim aracı** düğümünü genişletin.

1. **Giriş ve çıkış** özellik sayfasını seçin ve ardından **ekleme bildirimi** özelliğini **Evet** olarak ayarlayın.

1. **Tamam** düğmesine tıklayın.

1. Çözümü derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış uygulamalar](/windows/win32/SbsCs/isolated-applications)<br/>
[Yan yana derlemeler hakkında](/windows/win32/SbsCs/about-side-by-side-assemblies-)
