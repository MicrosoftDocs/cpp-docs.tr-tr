---
title: 'Nasıl yapılır: COM bileşenlerini kullanacak yalıtılmış uygulamalar derleme'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 01b5c7056bd10a7c1f88df74b5c6b4aa78ff3fde
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417885"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Nasıl yapılır: COM bileşenlerini kullanacak yalıtılmış uygulamalar derleme

Yalıtılmış uygulamalar programa oluşturulan bildirimleri sahip uygulamalardır. COM bileşenlerini kullanacak yalıtılmış uygulamalar oluşturabilirsiniz.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>Yalıtılmış uygulama bildirimlerinin COM başvuruları eklemek için

1. Yalıtılmış bir uygulama için proje özelliği sayfalarından açın.

1. Genişletin **yapılandırma özellikleri** düğümünü ve ardından **bildirim aracında** düğümü.

1. Seçin **yalıtılmış COM** özellik sayfası ve ardından **Bileşen dosyası adı** özelliğini kullanmak için yalıtılmış bir uygulama istediğiniz COM bileşeni adı.

1. **Tamam**'ı tıklatın.

### <a name="to-build-manifests-into-isolated-applications"></a>Yalıtılmış uygulamalarınızı bildirimleri oluşturmak için

1. Yalıtılmış bir uygulama için proje özelliği sayfalarından açın.

1. Genişletin **yapılandırma özellikleri** düğümünü ve ardından **bildirim aracında** düğümü.

1. Seçin **giriş ve çıkış** özellik sayfası ve ardından **ekleme bildirimi** özelliği eşit **Evet**.

1. **Tamam**'ı tıklatın.

1. Çözümü oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications)<br/>
[Yan yana derlemeler hakkında](/windows/desktop/SbsCs/about-side-by-side-assemblies-)
